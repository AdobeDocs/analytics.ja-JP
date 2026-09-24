---
title: Data Insertion APIを使用した訪問者の識別
description: Data Insertion APIを使用して、サーバーサイドおよびダイレクトAdobe Analyticsデータ収集用の訪問者を特定します。
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7fcd738b7eb13c13d5f9f23d625287988c803220
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# Data Insertion APIを使用した訪問者の識別

[Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)は、AppMeasurementやWeb SDKなどのクライアント側ライブラリを使用せずに、Adobe Analytics コレクション サーバーにヒットを送信します。 IDを管理するライブラリは存在しないため、ユーザーはユーザー自身で訪問者IDを設定できます。ユーザーはブラウザーで直接画像リクエストを行ったり、サーバー側で収集したりできます。

>[!NOTE]
>
>このページでは、訪問者IDについて説明します。 リクエスト自体の構築と送信については、Adobe Developerの[Data Insertion API ドキュメント ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)を参照してください。

Adobeは、標準的な[操作の順序](overview.md) （`vid`）、次に`aid`、`mid`、`fid`、最後にIP アドレスとユーザーエージェント）を使用して訪問者を識別します。 Data Insertion APIでは、通常、ECID （`mid`）、Analytics訪問者ID （`aid`）、カスタム訪問者ID （`vid`）の3つの識別子のいずれかを直接設定します。

## ECIDの使用（推奨）

ECID （`mid`として送信）は、Adobe Analytics、Adobe Target、Adobe Audience Managerで共有される、最新のクロスソリューションの訪問者識別子です。 Adobeでは、可能な限り使用することをお勧めします。

[訪問者ID サービス ](https://experienceleague.adobe.com/ja/docs/id-service/using/home) （`VisitorAPI.js`）でECIDを取得します。 ブラウザーで、[`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance)を使用してIMS組織IDでサービスを初期化し、[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)のECIDを読み取ります。

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

各ヒットにその値を`mid` クエリパラメーターとして送信し、IMS組織IDを`mcorgid` パラメーターとして送信して、ECIDが正しく解決されるようにします。 データをAudience Managerに転送する場合は、リージョンを[`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint)から`aamlh` パラメーターとして送信します。 独自の顧客識別子を訪問者に関連付けるには、[`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids)を使用します。

サーバーサイドの収集の場合は、クライアントでECIDを取得し、各ヒットで送信するためにサーバーに転送します。 クライアントなしで完全にサーバーサイドでECIDを生成するには、ID サービスの[直接統合](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration)を使用します。

## Analytics訪問者IDの使用

Analytics訪問者ID （`aid`）は[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieに保存されています。 ヒットが識別子なしで到着すると、収集サーバーは`aid`を割り当て、その識別子を含むCookieの設定を試みます。 一部の[応答タイプ ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)では、この識別子も応答本文に含まれています。

* **クライアントサイド （ダイレクトイメージリクエスト）。** ブラウザーは、サーバーが返す`s_vi` Cookieを保存し、後でリクエストされるたびに同じコレクションドメインに送信します。 その後、訪問者は自動的に認識され、自分を設定する`aid`はありません。 このモデルはCookieに依存するため、Cookie ベースのIDと同じ耐久性制限を持ちます。 ファーストパーティとサードパーティのCookieの動作について、[AppMeasurementを使用した訪問者の識別](appmeasurement.md)、およびAdobeが使用する識別子を選択する方法について[操作の順序](overview.md)を参照してください。 Adobeでは、耐久性のあるIDにECIDを使用することをお勧めします。

  >[!NOTE]
  >
  >`s_vi` cookieから訪問者IDを直接読み取ると、cookieはIDを追加データ （例：`[CS]v1|<id>[CE]`）でラップし、`<id>`部分のみを抽出します。 訪問者の応答からIDを読み取ると、解析なしで直接返されます。

* **サーバーサイド。** サーバーにCookie瓶がないので、ユーザーにキーを設定して`aid`を自分で保存して再送信します。

  1. ユーザーの保存されている`aid`を検索します。
  1. お持ちの場合は、`aid` クエリパラメーターとして送信します。
  1. そうでない場合は、識別子なしでヒットを送信し、割り当てられた`aid`を返す応答タイプを要求して、次回のために保存します。

  最初の識別子なしのヒットは、サーバーが返す`aid`に既に起因しているため、IDを取得する前に送信してデータを失うことはありません。 ID （`3` for JavaScript、`11` for XML、`10` for JSON）およびリクエスト形式を返す応答タイプについては、Data Insertion API ドキュメントの[応答タイプ ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)を参照してください。

  サーバーサイドのリクエストには訪問者のCookieは含まれず、独自のIP アドレスとユーザーエージェントは送信者に属しています。 ヒットを正しく関連付けるには、訪問者の実際のIP アドレス（`X-Forwarded-For` ヘッダー）とユーザーエージェント（`User-Agent` ヘッダー）も転送します。

## カスタム訪問者IDの使用

完全に制御できる耐久性のあるIDが既に存在する場合は、すべてのヒットと独自のIDに[`visitorID`](/help/implement/vars/config-vars/visitorid.md) （`vid`）としてエンドツーエンドで送信できます。 これは、安定したデバイス識別子を提供するブラウザー以外のプラットフォームに適しています。 例えば、Unity アプリケーションは、デバイス IDを`vid`として送信できます。

>[!IMPORTANT]
>
>すべてのヒットで安定した値を保証できる場合にのみ`vid`を使用してください：
>
>* **ブラウザーの適合性が低いです。** ブラウザーには、確実に入力できる永続的な識別子がありません。そのため、ブラウザーセット `vid`は断片化または衝突する傾向があります。 代わりに、Cookie ベースのクライアントサイドモデルを使用します。
>* **認証識別子に注意してください。** ユーザーがログインする前に識別子がなく、ユーザーがログアウトした場合、後のヒットは別の訪問者に起因します。 これらのアクションにより、1人のアクティビティが複数の訪問者に分割されます。

カスタム訪問者IDの形式と制約については、[`visitorID`](/help/implement/vars/config-vars/visitorid.md)を参照してください。
