---
title: Adobe Analytics でのデータの処理順序
description: Adobe Analytics でデータを処理するコンポーネントとサービスの順序について説明します。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
TQID: https://experienceleague.adobe.com/ypuneLG7mM63J7ag12IqSmizbCENs-akL-QfF-P9nVM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 1106
ht-degree: 37%

---

# Adobe Analytics でのデータの処理順序

アドビでは、レポートに表示される前にデータを変更または操作する方法を多数提供しています。 このページでは、様々な Adobe Analytics 機能によるデータの処理順序を示します。 このリストを使用すると、データの不整合をトラブルシューティングしたり、データの調整が必要な場合に使用する最適な機能を決定したりできます。

![注文画像](assets/processing-order.png)を処理しています

## アドビに送信する前のデータ

データをアドビに送信する前に、次のいずれかのメソッドを使用すると、通常はクライアント側でコンパイルされます。

* **AppMeasurement**：サイトでホストされ、各ページで参照される JavaScript ファイル。 データは Adobe Analytics に直接送信されます。
* **Adobe Experience Platform Web SDK**：サイトでホストされ、各ページで参照される JavaScript ファイル。 データはAdobe Experience Platform Edge Networkに送信されます。
* **Adobe Experience Platform Data Collectionのタグ**：各ページで参照され、Data Collection UI内で作成されたルールを含むJavaScript ファイル。 Adobe Analytics 拡張機能を使用すると、AppMeasurement の実装が容易になります。 Web SDK 拡張機能を使用すると、Web SDK をより簡単に実装できます。
* **API**: AppMeasurementとEdge Networkの両方で、Adobeにデータを送信するためのプログラム方式が用意されています。 AppMeasurementでは、[Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/)と[Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)を提供しています。Edge Networkでは、[Data Collection API](https://developer.adobe.com/data-collection-apis/docs/)を提供しています。

Edge Networkにデータを送信する場合は、データをAdobe Analytics（および他の多くのAdobe CX Enterprise ソリューション）に転送するように設定できます。 実装方法にかかわらず、収集されたヒットデータは、最終的に解析可能なフォーマットでAdobe Analytics処理サーバーに届きます。

## Adobe Analytics コレクションの前処理

データがAdobe Analyticsに到着すると、前処理フェーズに入ります。

1. [**動的変数**](/help/implement/vars/page-vars/dynamic-variables.md)：イメージリクエストのいずれかの部分に動的変数が検出された場合、その値はコピーされ、独立した値として処理されます。
1. [**IP難読化（最後のオクテット）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): レポートスイートが最後のオクテットのみを難読化するように設定されている場合、その難読化はここに適用されます。 IPの難読化（IPの削除）は、処理パイプラインの後半で発生します。
1. **参照テーブル**: Adobe内部の参照テーブルに依存するディメンション （例：[Browser](/help/components/dimensions/browser.md) ディメンション）は、対応する値と一致します。
1. [**IP除外**](/help/admin/tools/exclude-ip.md)：レポートから明示的に除外したIP アドレスは、この手順でフラグ付けされます。
1. [**ボットルール**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)：標準またはカスタムのボットフィルタリングを適用すると、そのデータをレポートから除外できます。
1. **ジオロケーションデータ**：IP アドレスのルックアップに依存するディメンション（[国](/help/components/dimensions/countries.md)ディメンションなど）が入力されます。
1. [**処理ルール**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)：組織がデータに適用したカスタムルール。 [ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)をそれぞれのAnalytics変数にマッピングします。
1. [**VISTA ルール**](vista.md)：アドビのコンサルタントがお客様のデータに適用する柔軟なカスタムルール。 VISTA ルールは、組織のニーズに応じて、処理ルールの前または後に実行できます。 通常、ほとんどの VISTA ルールは処理ルールの後に実行されますが、設定は組織ごとに異なります。 既存のVISTA ルールについて詳しくは、Adobe アカウントチームにお問い合わせください。
1. **通貨換算**: ヒットにレポートスイートの通貨とは異なる[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)が含まれている場合、該当する通貨変数は現在の為替レートを使用して換算されます。
1. [**郵便番号**](/help/components/dimensions/zip-code.md): 「郵便番号」ディメンションは、レポートスイートの設定に基づいて入力されます。

## データ収集パイプラインの「中程度の価値」ステージ

前処理が終了すると、いくつかの機能では、この部分的に処理されたデータ形式（「中間値」と呼ばれます）が使用されます。 そのデータが任意の場所に送信される前に、中値固有の処理が適用されます。

1. [**ヒットレベルのマーケティングチャネル処理ルール**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：これらの処理ルールは、Analytics Source コネクタに対して実行されます。 まだ訪問レベルや訪問者レベルのコンテキストはないため、これらの処理ルールでは、ヒットが訪問の最初のヒットでないことを前提としています。 ヒットの処理ルールを実行した結果は、`channel.typeAtSource`および`channel._id`で利用できます。
1. [**IP難読化（IPを削除）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：レポートスイートがIP アドレスを完全に難読化するように設定されている場合、その難読化はここで適用されます（中値の場合のみ）。

この時点で、中程度の値のデータがそれぞれの機能に送信されます。

* [**Livestream API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)：収集されたデータのフローについて、Adobeのライブストリームサービスにアプリケーションを接続します。
* [**Analytics Source Connector**](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics): Adobe Experience Platform データセットにAdobe Analytics レポートスイートデータを取り込みます。
* [**リアルタイムレポート**](/help/components/c-real-time-reporting/realtime.md):Analysis Workspaceで設定可能なリアルタイムレポートを最大3つ提供します。

## 訪問レベルおよび訪問者レベルの処理

この時点まで、あるヒットには、その前後に収集されたヒットに関する知識やコンテキストがありません。 この処理の段階では、訪問レベルと訪問者レベルのフィールドが設定されます。

1. [**訪問+訪問者の定義**](/help/implement/id/overview.md): ヒットは、含まれている訪問者変数に基づいて識別されます。
1. [**訪問数**](/help/components/dimensions/visit-number.md)：特定された訪問者の他の訪問に基づいて、訪問数が計算されます。
1. **イベント重複排除**: ヒットに重複した[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)または[ イベントのシリアル化](/help/implement/vars/page-vars/events/event-serialization.md)が含まれている場合、それらのIDはチェックされ、それぞれフラグが立てられます。
1. [**訪問レベルのマーケティングチャネル処理ルール**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：すべてのヒットはマーケティングチャネル処理ルールを通して実行され、ヒットが任意のルールと一致するかどうかをチャネルとチャネルの詳細が決定されます。 これらのルールは、Analysis Workspaceで使用可能な[ マーケティングチャネル ](/help/components/dimensions/marketing-channel.md)および[ マーケティングチャネルの詳細](/help/components/dimensions/marketing-detail.md) ディメンションに入力されます。
1. **変数の永続性**：永続性を持つディメンション（[eVars](/help/components/dimensions/evar.md)など）の場合、この手順でその値が決定されます。 一般的に、ほとんどの`post`値はここで設定されます。
1. **トランザクション ID**: ヒットに新しい[`transactionID`](/help/implement/vars/page-vars/transactionid.md)値が含まれている場合、サポートされているすべての値の「スナップショット」が保存されます。 データソースのアップロードに一致するトランザクション IDが含まれている場合、このスナップショットでサポートされているすべての値がそのデータソース行に含まれます。
1. [**IP難読化（IPを削除）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：レポートスイートがIP アドレスを完全に難読化するように設定されている場合、その難読化は、他のすべての処理が終了した後にここに適用されます。

この時点で、個々のヒットがレポートスイートのデータテーブルに記録されます。 標準の[待ち時間](latency.md)間隔の後、レポートで使用できます。

## 処理後のデータの変更

Adobe Analytics のデータは、ほとんどが永続的です。ただし、一部の機能では、選択的なデータの調整や削除が可能です。

* [**Data repair API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：特定の列を編集するか、目的のデータ行を削除します。
* [**データガバナンス**](/help/technotes/privacy/privacy-overview.md): データを完全に削除するためのプライバシー要求に対応します。
* [**分類**](/help/components/classifications/classifications-overview.md)：ルールまたはアップロードされたデータに基づいてディメンションを作成し、異なる方法でデータを整理できるようにします。 基になるレポートスイートのデータは変更されないので、自由に分類データを編集または上書きできます。
* [**仮想レポートスイート**](/help/components/vrs/vrs-about.md)：訪問タイムアウトを変更できる代替レポートスイートビューを作成します。
