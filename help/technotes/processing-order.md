---
title: Adobe Analytics でのデータの処理順序
description: Adobe Analytics でデータを処理するコンポーネントとサービスの順序について説明します。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Adobe Analytics でのデータの処理順序

アドビでは、レポートに表示される前にデータを変更または操作する方法を多数提供しています。このページでは、様々な Adobe Analytics 機能によるデータの処理順序を示します。このリストを使用すると、データの不整合をトラブルシューティングしたり、データの調整が必要な場合に使用する最適な機能を決定したりできます。

![&#x200B; 処理順序の画像 &#x200B;](assets/processing-order.png)

## アドビに送信する前のデータ

データをアドビに送信する前に、次のいずれかのメソッドを使用すると、通常はクライアント側でコンパイルされます。

* **AppMeasurement**：サイトでホストされ、各ページで参照される JavaScript ファイル。データは Adobe Analytics に直接送信されます。
* **Adobe Experience Platform Web SDK**：サイトでホストされ、各ページで参照される JavaScript ファイル。データはAdobe Experience Platform Edge Networkに送信されます。
* **Adobe Experience Platform Data Collection のタグ**：データ収集 UI 内で作成されたルールを含む、各ページで参照されるJavaScript ファイル。 Adobe Analytics 拡張機能を使用すると、AppMeasurement の実装が容易になります。Web SDK 拡張機能を使用すると、Web SDK をより簡単に実装できます。
* **API**: AppMeasurementとEdge Networkの両方が、Adobeにデータを送信するプログラム方式を提供します。 AppMeasurementには [Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) と [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) が用意されており、Edge Networkには [Data Collection API](https://developer.adobe.com/data-collection-apis/docs/) が用意されています。

Edge Networkにデータを送信する場合、Adobe Analytics（および他の多くのAdobe Experience Cloud ソリューション）にデータを転送するように設定できます。 実装方法に関係なく、収集されたヒットデータは、最終的に、解析可能な形式でAdobe Analytics処理サーバーに到達します。

## Adobe Analytics コレクションの前処理

データがAdobe Analyticsに到達すると、前処理フェーズに入ります。

1. [**動的変数**](/help/implement/vars/page-vars/dynamic-variables.md)：イメージリクエストのいずれかの部分に動的変数が検出された場合、その値はコピーされ、独立した値として処理されます。
1. [**IP の不明化（最後のオクテット）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：レポートスイートが最後のオクテットのみを不明化するように設定されている場合、その不明化はここで適用されます。 なお、IP の不明化（IP の削除）は、処理パイプラインの後半で行われます。
1. **ルックアップテーブル**:Adobe内部のルックアップテーブルに依存するディメンション（[&#x200B; ブラウザー &#x200B;](/help/components/dimensions/browser.md) ディメンションなど）は、対応する値に一致します。
1. [**IP 除外**](/help/admin/tools/exclude-ip.md)：この手順では、レポートから明示的に除外する IP アドレスにフラグを立てます。
1. [**ボットルール**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)：標準またはカスタムのボットフィルタリングを適用すると、そのデータをレポートから除外できます。
1. **ジオロケーションデータ**：IP アドレスのルックアップに依存するディメンション（[国](/help/components/dimensions/countries.md)ディメンションなど）が入力されます。
1. [**処理ルール**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)：組織がデータに適用したカスタムルール。[&#x200B; コンテキストデータ変数 &#x200B;](/help/implement/vars/page-vars/contextdata.md) のそれぞれの Analytics 変数へのマッピングが含まれます。
1. [**VISTA ルール**](vista.md)：アドビのコンサルタントがお客様のデータに適用する柔軟なカスタムルール。VISTA ルールは、組織のニーズに応じて、処理ルールの前または後に実行できます。通常、ほとんどの VISTA ルールは処理ルールの後に実行されますが、設定は組織ごとに異なります。既存の VISTA ルールについて詳しくは、Adobe アカウントチームにお問い合わせください。
1. **通貨換算**：ヒットにレポートスイートの通貨とは異なる [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) が含まれている場合、該当する通貨変数は現在の日の為替レートを使用して変換されます。
1. [**郵便番号**](/help/components/dimensions/zip-code.md):「郵便番号」ディメンションは、レポートスイートの設定に基づいて入力されます。

## データ収集パイプラインの「中間値」ステージ

前処理が完了すると、この部分的に処理された形式のデータ（「中間値」と呼ばれます）が複数の機能で使用されます。 そのデータをどこかに送信する前に、値が中程度の処理が適用されます。

1. [**ヒットレベルのマーケティングチャネルの処理ルール**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：これらの処理ルールは、特に Analytics Source Connector に対して実行されます。 訪問または訪問者レベルのコンテキストはまだないので、これらの処理ルールは、ヒットが訪問の最初のヒットではないと仮定します。 ヒットの処理ルールの実行結果は、`channel.typeAtSource` と `channel._id` で入手できます。
1. [**IP の不明化（IP を削除）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md):IP アドレスを完全に不明化するようにレポートスイートが設定されている場合、その不明化はここで適用されます（中間値の場合のみ）。

この時点で、値が中程度のデータがそれぞれの機能に送信されます。

* [**Livestream API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)：収集されたデータフロー用に、Adobeを使用してアプリケーションを Livestream サービスに接続します。
* [**Analytics Source コネクタ**](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics):Adobe Experience Platform データセットにAdobe Analytics レポートスイートデータを取り込みます。
* [**リアルタイムレポート**](/help/components/c-real-time-reporting/realtime.md):Analysis Workspaceで最大 3 つの設定可能なリアルタイムレポートを提供します。

## 訪問および訪問者レベルの処理

これまでの時点では、特定のヒットには、その前または後に収集されたヒットの知識やコンテキストはありません。 この処理ステージでは、訪問および訪問者レベルのフィールドが設定されます。

1. [**訪問+訪問者定義**](/help/implement/id/overview.md)：含まれている訪問者変数に基づいてヒットが識別されます。
1. [**訪問回数**](/help/components/dimensions/visit-number.md)：特定された訪問者の他の訪問に基づいて、訪問回数が計算されます。
1. **イベントの重複排除**：ヒットに重複した [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) または [&#x200B; イベントのシリアル化 &#x200B;](/help/implement/vars/page-vars/events/event-serialization.md) が含まれる場合、これらの ID がチェックされ、それぞれフラグが付けられます。
1. [**訪問レベルのマーケティングチャネル処理ルール**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：すべてのヒットがマーケティングチャネル処理ルールを介して実行され、ヒットが任意のルールに一致するかどうかに応じて、チャネル +チャネルの詳細が決定されます。 これらのルールによって、Analysis Workspaceで使用可能な [&#x200B; マーケティングチャネル &#x200B;](/help/components/dimensions/marketing-channel.md) および [&#x200B; マーケティングチャネルの詳細 &#x200B;](/help/components/dimensions/marketing-detail.md) ディメンションが設定されます。
1. **変数の永続性**：永続性を持つディメンション（[eVars](/help/components/dimensions/evar.md) など）の場合、その値はこの手順で決定されます。 一般的に、ほとんどの `post` 値はここに設定されます。
1. **トランザクション ID**：ヒットに新しい [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 値が含まれる場合、サポートされているすべての値の「スナップショット」が保存されます。 データソースのアップロードに一致するトランザクション ID が含まれている場合、このスナップショットでサポートされているすべての値がそのデータソースの行に含まれます。
1. [**IP の不明化（IP を削除）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md):IP アドレスを完全に不明化するようにレポートスイートが設定されている場合、その不明化は他のすべての処理が完了した後にここに適用されます。

この時点で、個々のヒットがレポートスイートのデータテーブルに記録されます。標準の[待ち時間](latency.md)間隔の後、レポートで使用できます。

## 処理後のデータの変更

Adobe Analytics のデータは、ほとんどが永続的です。ただし、一部の機能では、選択的なデータの調整や削除が可能です。

* [**Data repair API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：特定の列を編集するか、目的のデータ行を削除します。
* [**データガバナンス**](/help/technotes/privacy/privacy-overview.md)：データを永続的に削除するプライバシーリクエストに対応します。
* [**分類**](/help/components/classifications/classifications-overview.md)：ルールまたはアップロードされたデータに基づいてディメンションを作成し、異なる方法でデータを整理できるようにします。基になるレポートスイートのデータは変更されないので、自由に分類データを編集または上書きできます。
* [**仮想レポートスイート**](/help/components/vrs/vrs-about.md)：訪問のタイムアウトを変更できる別のレポートスイートビューを作成します。
