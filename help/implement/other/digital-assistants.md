---
title: デジタルアシスタント向け Analytics の実装
description: Amazon Alexa や Google Home などのデジタルアシスタントに Adobe Analytics を実装します。
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
TQID: 'https://experienceleague.adobe.com/QKlchx0r3ZDourRQaQAJaMn9Fh3bXiEWHprCkLVALsk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: f801835bb65be97db52dfccd217ecba268230eea
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 9%
---
# デジタルアシスタント向け Analytics の実装

クラウドコンピューティング、マシンラーニング、自然言語処理の進歩により、デジタルアシスタントは日常生活の一部になっています。 消費者はデバイスとやり取りし、人間のような反応を期待します。企業は、そうした体験を通じてサービスを提供できます。 例えば、消費者は次のように問い合わせることができます。

* 「アレクサ、車にオイル交換が必要な時に聞いてくれ」
* 「Google、当座預金残高は？」
* “ Siri、Johnに昨晩の夕食に20 ドルを私の銀行アプリから送ってください”。

ここでは、Adobe Analyticsを使用して、これらのタイプのエクスペリエンスを測定し、最適化する方法の概要を説明します。

## デジタルエクスペリエンスのアーキテクチャの概要

![デジタルアシスタントのワークフロー](assets/Digital-Assitants.png)

ほとんどのデジタルアシスタントは、同様の高レベルのアーキテクチャに従っています。

1. **デバイス**：ユーザーが質問できるマイクを備えたデバイス（スマートスピーカーや電話など）。
1. **デジタルアシスタント**: アシスタントを強化するサービス。 音声を機械が理解できるインテントに変換し、リクエストの詳細を解析します。 インテントが理解されると、アシスタントはリクエストを処理するアプリにインテントと詳細を渡します。
1. **「アプリ」**：電話のアプリ、またはリクエストに応答する音声アプリ。 デジタルアシスタントに応答し、ユーザーに応答します。

## Adobe Analyticsへのデータの送信方法

デジタルアシスタントアプリは通常、Adobe クライアントサイドライブラリ（AppMeasurementまたはWeb SDK）を持たないサーバーまたはプラットフォーム上で実行されます。 [ データ挿入API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)**を使用して、ヒットを** サーバーサイドで送信します。 測定する各インタラクションは、クエリ文字列（またはXML本文）がこのページで説明されている変数を含むData Insertion API リクエストになります。ほとんどの場合、[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)は、[処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を使用してeVar、prop、イベントにマッピングされます。

このページでは、*何*&#x200B;を測定し、Analyticsでモデル化する方法に焦点を当てます。 エンドポイント、クエリ文字列およびXML エンコーディング、必要なコンポーネント、応答タイプについては、[Data Insertion API ドキュメント ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)を参照してください。 以下の名前の各変数は、[変数参照](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)のクエリ文字列パラメーターとXML タグにマッピングされます。

## 分析の導入場所

Adobe Analyticsを導入する最適な場所のひとつは、アプリです。アプリは、デジタルアシスタントから意図と詳細を受け取り、どのように対応するかを決定します。 Adobe Analyticsにデータを送信するのに役立つリクエストには、次の2つの瞬間があります。

1. アプリに要求が送信されたとき。
1. アプリから応答が送られたとき。

今後の最適化のために何が起こったかを記録したい場合は、応答が返された後にヒットを送信します。その後、リクエストの完全なコンテキストとシステムがどのように応答したかを確認できます。

## 測定対象

### 新規インストール

誰かがスキルをインストールしたときに通知するアシスタントの場合（特に認証が関係する場合）、コンテキストデータ変数`a.InstallEvent=1`と`a.InstallDate`およびアプリ ID （`a.AppID`）を設定して、インストールイベントを送信します。 これは、あらゆるプラットフォームで利用できるわけではありませんが、既存の顧客維持分析で役立ちます。

### 複数のアシスタントやアプリ

多くの企業は、複数のプラットフォームに対応するアプリを構築しています。 `a.AppID` コンテキストデータ変数のすべてのリクエストに、形式`[AppName] [BundleVersion]` （例：`Spoofify 1.0`）を使用してアプリ IDを含めます。 プラットフォームまたはOS コンテキストデータ変数（`OSType`など）を追加して、レポートでAlexa、Google Assistant、その他のプラットフォームを区別できるようにします。

### 訪問者の識別

Adobe Analyticsは[Adobe Visitor ID サービス ](https://experienceleague.adobe.com/ja/docs/id-service/using/home)を使用して、インタラクションを時間をかけて同じユーザーに関連付けます。 ほとんどのデジタルアシスタントは、一意のIDとして使用できる`userID`を返します。これを訪問者IDの上書き（`vid`）として渡します。 一部のプラットフォームでは、許可されている100文字よりも長い識別子が返されます。この場合、MD5やSHA-1などの標準アルゴリズムを使用して、固定長の値にハッシュ化します。

訪問者ID サービスを使用すると、デバイス（webからデジタルアシスタントなど）間でECIDをマッピングする際に最も価値を提供します。 アプリがモバイルアプリの場合は、Experience Platform Mobile SDKを使用し、`setCustomerID`方式でユーザーIDを送信します。 アプリがサービスの場合は、サービスが提供するユーザーIDを訪問者IDとして使用し、`setCustomerID`と設定します。 サーバーサイドのリクエストで識別子を設定する方法については、[Data Insertion APIを使用した訪問者の識別](../id/data-insertion.md)を参照してください。

### セッション数

デジタルアシスタントは会話型であるため、セッション（複数回のやり取り）という概念を持つことがよくあります。 新しいセッションが始まると、Adobeは次の2つのことを推奨します。

1. **Audience Manager**&#x200B;に連絡して、ユーザーが属するセグメントを取得します。これにより、レスポンスをカスタマイズできます。
1. **コンテキストデータ変数`a.LaunchEvent=1`を設定して、最初の応答を含むローンチイベント**&#x200B;を送信します。

### 目的

各アシスタントはインテントを検出し、アプリに渡します。 意図とは、リクエストの簡潔な表現です。例えば、「Siri、Johnに銀行アプリから昨晩の夕食に$20を送る」は、意図&#x200B;*sendMoney*&#x200B;に解決する可能性があります。 各インテントをeVarにマッピングするコンテキストデータ変数に送信し、インテント間でパスレポートを実行できるようにします。 アプリでも意図せずにリクエストを処理できることを確認してください。Adobeでは、変数を省略するのではなく`No Intent Specified`を送信することをお勧めします。

### パラメータ、スロット、およびエンティティ

インテントに加えて、アシスタントはリクエストのキー/値の詳細（スロット、エンティティ、パラメーターと呼ばれます）を提供することがよくあります。 &quot;Siri, send John $20 for dinner last night&quot;の場合、パラメーターは次のようになります。

* 誰が=ジョン
* 金額= 20
* Why = Dinner

通常、アプリごとに有限のデータセットが存在します。 コンテキストデータ変数に送り、それぞれをeVarにマッピングします。

### エラー状態

アシスタントがアプリで処理できない入力を渡すことがあります（例：「Siri、Johnに銀行アプリから20袋の石炭を送る」）。 このような場合は、アプリで説明を求め、エラーの状態を示すデータを送信します。エラーの種類を指定するeVarと共に`a.Error=1`を設定します。 入力が無効なエラーと、アプリ自体に問題があったエラーの両方を含めます。

### デバイスの機能

ほとんどのプラットフォームはデバイスを正確に公開しませんが、その機能（オーディオ、スクリーン、ビデオなど）は公開されており、使用できるコンテンツタイプが定義されています。 デバイスの機能を測定する場合は、先頭と末尾のコロン（例：`":Audio:Camera:Screen:Video:"`）でアルファベット順に連結して、「すべてのヒット数`:Audio:`」などのセグメントを作成できるようにします。

* [Amazon Alexa インターフェイスリファレンス](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)
* [Googleアシスタントなら](https://developers.google.com/actions/assistant/surface-capabilities)

## リクエストの例

次のData Insertion API GET リクエストは、銀行アプリの&#x200B;*SendPayment* インテントを記録し、アプリ ID、起動イベント、インテント、およびスロット値をコンテキストデータとして設定します。

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo%201.0&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&pageName=SendPayment HTTP/1.1
Host: example.data.adobedc.net
```

完全なリクエスト形式、エンドポイントおよび応答タイプについては、[Data Insertion API ドキュメント ](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/request)を参照してください。

## 測定モデルの例

次の表は、音楽アプリの一般的なアクションをAnalytics変数にマッピングする方法を示しています。 これらは、各Data Insertion API リクエストでコンテキストデータ変数として設定し、処理ルールを使用してeVarおよびイベントにマッピングします。

| 顧客アクション | インテント/イベント | 設定するコンテキストデータ |
| --- | --- | --- |
| アプリのインストール | Install | `a.InstallEvent=1`, `a.InstallDate`, `a.AppID`, `OSType` |
| アプリを起動 | Launch | `a.LaunchEvent=1`, `a.AppID`, `Intent=Play` |
| 曲の変更を依頼 | ChangeSong | `a.AppID`, `Intent=ChangeSong` |
| 特定の曲を再生する | ChangeSong | `a.AppID`, `Intent=ChangeSong`, `SongID` |
| プレイリストを変更 | ChangePlaylist | `a.AppID`, `Intent=ChangePlaylist`, `Playlist` |
| 無効な入力が検出されました | （エラー） | `a.Error=1`, `ErrorName` |
