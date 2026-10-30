---
title: Analytics データ収集のデバッグ
description: Adobe Analyticsが、AppMeasurement、Analytics拡張機能、Web SDK、Mobile SDK、Data Insertion APIから必要なデータを受け取ることを確認します。
keywords: デバッグ、検証、パケットアナライザー、パケットモニター、/b/ss/、Edge Trace、Assurance、hitdebugger、レポートスイート
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# Analytics データ収集のデバッグ

この記事では、Adobe Analyticsに送信されたデータをデバッグする際に確認すべき内容について説明します。 次の表で実装方法を見つけ、その節に従います。 予期しないレポートデータを調査する場合は、[&#x200B; リクエストとレポートの比較](#reports)から始めます。

ネットワーク要求のキャプチャ、デバッグログの有効化、キャンセルされた要求の調査など、すべてのAdobe データ収集に適用される手順とツールについては、[&#x200B; データ収集のデバッグとトラブルシューティング &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview)を参照してください。

| 実装方法 | Analyticsが受け取るデータを表示する場所 | ガイダンス |
| --- | --- | --- |
| AppMeasurementまたはAnalytics タグ拡張機能 | ブラウザーからAnalytics データ収集サーバーへのリクエスト | [AppMeasurement](#appmeasurement) |
| Web SDK | Edge Traceを実行すると、Edge NetworkがイベントをAnalytics ヒットに変換します | [Web SDK](#web-sdk) |
| Mobile SDK | AssuranceのAnalytics イベントビュー。 Edge NetworkまたはEdge Bridge拡張機能を使用している場合は、**[!UICONTROL Analytics Edge View]**&#x200B;をオンにします。 | [AssuranceのAdobe Analytics イベントビュー](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/adobe-analytics) |
| データ挿入 API | サーバーの送信リクエストとその応答 | [Data Insertion API リクエストのトラブルシューティング &#x200B;](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurementとAnalytics拡張機能 {#appmeasurement}

### リクエストを見つける {#appmeasurement-find}

[&#x200B; ネットワーク要求をキャプチャ &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web)し、`/b/ss/`に対してフィルターを実行します。 Adobe Experience Platform Debuggerなどのタグデバッガーを使用して、これらのリクエストを識別およびデコードできます。

`/b/ss/` リクエストが表示されない場合：

* ブラウザーコンソールでJavaScript エラーを確認します。
* Analytics タグ拡張機能を使用する場合は、タグ埋め込みコードがページの`<head>`要素の中にあり、ライブラリがテスト対象の環境に公開されていることを確認します。 [&#x200B; タグのデバッグモード &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging)は、ヒットを送信するルールが実行されたかどうかを示します。
* AppMeasurementを自分でホストしている場合は、ライブラリのURLを直接開いて、ファイルが読み込まれ、コードが含まれていることを確認します。
* リクエストの送信を妨げる可能性のある、広告ブロッカーなどのブラウザー拡張機能を無効にします。
* デバッガーは、iframe内から送信されたリクエストを認識しません。 代わりに、ブラウザー開発者ツールを使用してください。 [iFramesでのAppMeasurementの使用](../use-cases/iframe.md)を参照してください。

### Analyticsが受け取った内容を確認 {#appmeasurement-contents}

* **レポートスイート**: `/b/ss/`の後のパスセグメントには、ヒットを受け取ったレポートスイート IDが一覧表示されます。 開発ページの開発レポートスイートなど、期待するレポートスイートであることを確認します。
* **変数**:Raw リクエストでは、変数名ではなくクエリパラメーター名が使用されます。例えば、eVar1は`v1`として表示され、prop1は`c1`として表示されます。 [変数参照](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)を参照してください。 リクエストが長すぎると、AppMeasurementはHTTP `POST`でリクエストを送信するので、変数はURLではなくリクエスト本文に表示されます。
* **ヒットの種類**: [`tl()`](../vars/functions/tl-method.md)が送信したリクエストには`pe` パラメーターが含まれており、ページビューを増分しません。 [`t()`](../vars/functions/t-method.md)様が送信したリクエストには`pe`が含まれていません。

値が存在するが間違っている場合は、引用符、大文字/小文字、空白などの一般的な原因については、[JavaScript実装のトラブルシューティング &#x200B;](../js/troubleshooting.md)を参照してください。

### 応答を確認 {#appmeasurement-response}

`2xx`応答は、データ収集サーバーがリクエストを受信したことを確認するだけで、ヒットが記録されたことを確認するものではありません。 デフォルトの応答タイプでは、ヒットがドロップされた場合でも、リクエストは成功を返すことができます。 新規訪問者の最初のリクエストに対する`302`応答が必要です。 [HTTP応答コード &#x200B;](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)を参照してください。

AppMeasurementは、[`useBeacon`](../vars/config-vars/usebeacon.md)が有効になっているときに、終了リンクリクエストとすべてのリクエストを`navigator.sendBeacon()`とともに送信します。 開発者ツールは、ブラウザーがリクエストを送信した場合でも、リクエストにキャンセルとしてラベル付けすることができます。 [中断されたリクエスト &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests)を参照してください。

## Web SDK {#web-sdk}

### リクエストを見つける {#web-sdk-find}

Web SDKでは、ブラウザーはAnalyticsに直接ではなくEdge Networkにイベントを送信するため、`/b/ss/` リクエストは表示されません。 [Edge Network リクエスト &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests)を確認し、次の点を確認します。

* `configId` パラメーターは、[Adobe Analytics サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure#analytics)が有効になっているデータストリームと、想定されるレポートスイートが一致しています。
* ペイロードは、ページビューまたはリンクイベントとして認定されます。 Analyticsは、ページの詳細もweb インタラクションタイプも含まないペイロードを無視します。 Adobe Analytics[&#128279;](../aep-edge/hit-types.md)のEdge Network イベントタイプを参照してください。

### Analyticsが受け取った内容を確認 {#web-sdk-contents}

[Edge トレース &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace)を開始し、アクションを再現します。 **[!UICONTROL Analytics自動マッピング]**&#x200B;で始まる行を見つけ、その下の`mappedQueryParams`とレポートスイート IDを展開します。

* **変数**: マッピングされた値は、AppMeasurement リクエストと同じクエリパラメーター名を使用します。ページ名には`gn`、商品には`pl`などの短縮形を使用する場合があります。 [XDM オブジェクトフィールドマッピング &#x200B;](../aep-edge/xdm-var-mapping.md)および[&#x200B; データオブジェクトフィールドマッピング &#x200B;](../aep-edge/data-var-mapping.md)を参照してください。
* **コンテキストデータ**:Analytics変数にマッピングされないXDM フィールドは、`c.a.x.`接頭辞を持つコンテキストデータとして表示されます。 [処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を使用して、変数に割り当てます。
* **レポートスイート**: レポートスイートの上書きを使用すると、Edge Network Traceのデータストリーム設定行に、Edgeが使用したレポートスイートが表示されます。

### 処理を確認 {#web-sdk-processing}

Edge トレースが開くAssurance セッションで、`hitdebugger`のイベントを検索します。 これらのイベントはベンダー`com.adobe.analytics.hitdebugger`を使用し、それらのペイロードは、Experience Cloud ID （`mcvisId`）や`pageName`などのAnalytics処理後の値を示します。

ガイド付きチュートリアルについては、[Adobe Experience Platform Web SDKを使用したAdobe Analyticsの設定](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics)を参照してください。

## リクエストとレポートの比較 {#reports}

Analyticsに到達したヒットは、レポートにすぐに表示されず、レポート値がリクエストの値と異なる場合があります。

* **待ち時間**：完全なデータは、通常、収集から約2時間後にレポートに表示されます。 タイムスタンプ付きヒットなどの一部のデータには、時間がかかる場合があります。 [&#x200B; データの可用性と待ち時間](/help/technotes/latency.md)を参照してください。
* **処理**：処理ルール、VISTA ルール、ボットルール、およびその他の処理ステップは、収集後に値を変更または除外できます。 Adobe Analytics[&#128279;](/help/technotes/processing-order.md)でのデータの処理順序を参照してください。 Assuranceの後処理データは、個々のヒットに対する処理の結果を示します。
* **レポートスイート**：リクエストまたはデータストリームがターゲットとしたのと同じレポートスイートを表示していることを確認します。
* **予期しない値**: ディメンションに予期しないスパイクまたは値が表示される場合は、[&#x200B; ハッシュの衝突](hash-collisions.md)を参照してください。

より広範なトラフィックの変更については、[&#x200B; データのスパイクとドロップのトラブルシューティング &#x200B;](/help/technotes/event/spikes-drops.md)を参照してください。
