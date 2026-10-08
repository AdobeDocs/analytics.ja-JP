---
title: Analytics実装用のデバッグツール
description: Analytics デバッガー、ブラウザー開発者ツール、HTTP デバッグプロキシを使用して、実装がAdobeに送信するデータを検査します。
keywords: パケットアナライザ、パケットモニター、パケットスニファ、デバッガ、チャールズ、NS_BINDING_ABORTED、sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Analytics実装用のデバッグツール

デバッグツールは、パケットアナライザやパケットスニファと呼ばれることもあり、実装がAdobeに送信するデータを調べることができます。 リクエストが正常に実行されたことを確認し、リクエストに含まれる変数とペイロードを検査し、予期しない実装動作をトラブルシューティングするのに役立ちます。

>[!NOTE]
>
>このページに記載されているツールは包括的ではありません。 Adobe Analyticsのユーザーが便利だと感じたツールを表します。 Adobeが提供するツールを除き、Adobeはこれらの製品をサポートまたはトラブルシューティングしません。 インストール、使用方法、サポート情報については、ツールのパブリッシャーに問い合わせてください。

## デバッグツールの選択

次のカテゴリは、検査する内容に基づいてツールを選択するのに役立ちます。

| ツールタイプ | 次の場合に便利 |
| --- | --- |
| **Analyticsとタグデバッガー** | Analyticsの変数、タグ、データレイヤー、収集リクエストを、人間が判読可能な形式で解釈および提示する必要があります。 |
| **ブラウザー開発者ツール** | Web実装をデバッグする場合、別のデバッグアプリケーションをインストールせずにネットワークリクエストを直接検査する必要があります。 |
| **HTTP （S） デバッグ プロキシ** | ブラウザー、モバイルアプリ、web ビュー、APIなどのクライアントからのHTTP トラフィックを調査したり、ブラウザー開発者ツール以外の機能が必要な場合。 |

## 分析とタグデバッガー

分析とタグのデバッガーは、分析テクノロジーを認識し、その要求を解釈します。 これらのツールを使用すると、ネットワークリクエストを手動でデコードすることなく、Adobe Analytics変数、Experience Platform Web SDK ペイロード、タグ、および関連する実装情報を簡単に識別できます。

| ツール | 対象 | 次に役立つ | 注意点 |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/ja/docs/experience-platform/debugger/home)** | ブラウザー拡張機能 | Adobe Analytics、タグ、データレイヤー、Experience Platform Web SDKなどのAdobe Experience PlatformおよびCX Enterpriseの実装のデバッグ | Adobeが提供するツール（Adobeテクノロジーに重点） |
| **[Omnibug](https://omnibug.io)** | Chromium ベースのブラウザーとFirefox | Adobe Analytics、Experience Platform Web SDK、Adobeのタグ、その他の多くの分析およびマーケティングベンダーからのリクエストのデコード | 複数のベンダーのテクノロジーを含む実装に便利です |
| **[ObservePoint デバッガー](https://www.observepoint.com/solutions/observepoint-debugger/)** | ChromeとEdge | Adobe Analyticsのリクエストを含む、分析、マーケティング、測定タグの調査とデコード | ブラウザーベースのデバッガー。ObservePointでは、実装検証の自動化製品も個別に提供しています。 |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/home)** | CX Enterpriseのweb アプリケーション | Mobile SDK実装からのイベントの検査と検証、およびEdge Networkがイベントをどのように処理したかを確認する | Adobeが提供するツール。アプリをAssurance セッションに接続して、イベントを表示します |

## ブラウザー開発者向けツール

モダンなブラウザーには、ネットワークリクエストを検査できる開発者ツールが含まれているため、web実装をデバッグするために個別のツールが必要ないことが多くあります。 **F12**&#x200B;または&#x200B;**Ctrl+Shift+I** （WindowsおよびLinux）または&#x200B;**Cmd+Option+I** （macOS）を押してから、**Network** タブを選択します。 Safariでは、最初にSafariの&#x200B;**詳細**&#x200B;設定で開発者機能を有効にします。

## HTTP （S） デバッグ プロキシ

HTTP デバッグプロキシは、クライアントとサーバー間のHTTPおよびHTTPS トラフィックを傍受します。 ブラウザー開発者ツールで十分な可視性が得られない場合や、実装が従来のweb ブラウザーの外部で実行される場合に役立ちます。

HTTPS インスペクションでは、通常、デバッグプロキシから提供された証明書を信頼するようにクライアントを設定する必要があります。 証明書をインストールする場合や、暗号化されたトラフィックを傍受する場合は、組織のセキュリティポリシーに従ってください。

| ツール | 次に役立つ |
| --- | --- |
| **[チャールズ &#x200B;](https://www.charlesproxy.com/)** | ブラウザー、アプリケーション、モバイルデバイス、その他のHTTP （S）トラフィックの調査 |
| **[Fiddler Everywhere](https://www.telerik.com/fiddler/fiddler-everywhere)** | アプリケーションやデバイスをまたいだHTTP （S） トラフィックの取得と検査。 古いFiddler Classic製品とは異なります。 |
| **[Proxyman](https://proxyman.com/)** | ブラウザー、アプリケーション、モバイルデバイスからのHTTP （S） トラフィックの調査と修正 |
| **[HTTP Toolkit](https://httptoolkit.com/)** | アプリケーションとAPIのデバッグに特化したワークフローにより、アプリケーション、API、開発環境、モバイルデバイスからのトラフィックを調査 |
| **[mitmproxy](https://www.mitmproxy.org/)** | スクリプト可能なHTTP （S）のインターセプト、インスペクション、およびコマンドラインおよびweb インターフェイスを介した変更。 コマンドラインワークフローに慣れているユーザーに最適です。 |

## Adobe Analytics リクエストを探す

AppMeasurementなどのAdobe Analyticsに直接データを送信する実装では、次のネットワークリクエストをフィルタリングします。

```text
/ss/
```

Adobe Analytics コレクションリクエストには、リクエスト URLまたはペイロードにAnalytics変数が含まれます。 Raw リクエストでは、変数名ではなくクエリパラメーター名が使用されます。例えば、eVar1は`v1`として表示され、prop1は`c1`として表示されます。 Adobe Analyticsのデバッガーを使用すれば、これらの名前を容易にデコードできます。 自分でデコードするには、Data Insertion API ドキュメントの[変数参照](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)を参照してください。

Analytics データ収集サーバーが返すHTTP ステータスコードについては、Data Insertion API ドキュメントの[HTTP応答コード &#x200B;](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)を参照してください。

Adobe Experience Platform Web SDKを使用する実装の場合、次のネットワークリクエストをフィルタリングします。

```text
/ee/
```

リクエストを選択し、そのペイロードを調べて、Adobe Experience Platform Edge Networkに送信されたデータを表示します。 Web SDKは、Edge Networkにデータを送信し、Adobe Analyticsやその他の設定済みサービスにデータを転送できます。 クライアントのリクエストを調べると、ブラウザーがEdge Networkに送信した内容が確認されます。それ自体では、データがすべてのダウンストリームサービスで正常に処理されたことが確認されるわけではありません。 Edge Networkがイベントをどのように処理したかを確認するには、[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/home)を使用します。

## 中断された要求

ページが移動すると、ブラウザーは処理中のリクエストをキャンセルできます。 Firefoxはこれらのリクエストに`NS_BINDING_ABORTED`というラベルを付けます。ChromeとEdgeはそれらを`(canceled)`というラベルを付けます。 ナビゲーション後にリクエストを表示するには、**ログを保持** （ChromeとEdge）または&#x200B;**ログを保持** （Firefox）を有効にします。

キャンセルされたリクエストは、必ずしもデータが失われたわけではありません。 ブラウザーは完全なリクエストを送信し、応答の待ち時間のみを停止した可能性があります。 ブラウザー開発者ツールは通常、違いを示すことはできませんが、HTTP デバッグプロキシは違いを示すことができます。

`navigator.sendBeacon()`で送信されたリクエストは、ナビゲーション時にキャンセルされません。 AppMeasurementは、終了リンクに`sendBeacon`を使用し、[`useBeacon`](/help/implement/vars/config-vars/usebeacon.md)が有効になっている場合は常にを使用します。 Web SDKでは、[`documentUnloading`](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/commands/sendevent/documentunloading)で送信されたイベントに使用されます。 リンクトラッキングリクエストが頻繁にキャンセルされる場合は、これらのオプションを使用します。
