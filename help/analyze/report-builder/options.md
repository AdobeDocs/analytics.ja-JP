---
description: オプションパネルでは、日付設定、待ち時間設定（現在のデータ）およびログ情報を指定し、更新を設定できます。
title: Report Builder オプション
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Report Builder オプション

オプションパネルでは、日付設定、待ち時間設定（現在のデータ）およびログ情報を指定し、更新を設定できます。

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| 要素 | 説明 |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| 現在の日付に設定 | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| 更新時に設定 | リクエストを更新する [!UICONTROL As Of Date] 際にを設定できます。 |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>このオプションを使用しない場合は、ファイナライズされたモード（処理済み）が使用され、通常は[待ち時間](https://marketing.adobe.com/resources/help/ja_JP/reference/data_latency.html)が長くなります。<br>この設定は、「現在のデータ」機能と互換性のあるワークブック内のすべてのリクエストに適用されます。リクエストに互換性がない場合は、確定モードが適用されます。<br>モードを使用する場合は、次の状況に注意してく [!UICONTROL Include Current Data] ださい：<br>**Format Options **:表示ヘッダーの形式設定時に、この情報を表示するかど[!UICONTROL Data Recency]うかを指[定できます](/help/analyze/report-builder/layout/t-format-display-headers.md)。<br>**内訳**：サポートされません。If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. ただし、その他のリクエストでは、引き続き現在のデータモードが使用されます。<br>**リクエストマネージャー&#x200B;**：予定リクエストに設定が適用されているかどうかは、リクエストマネージャーの現在のデータ列で確認できます。<br>**スケジュールされたワークブック**：このモードは、スケジュールの処理中にワークブックレベルで保存されます。If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**権限&#x200B;**：現在のデータへのアクセス権限のないユーザーに対しては、このオプションは非表示になります。このオプションを有効にしたときに、1 つ以上のリクエストを適用できない場合は、警告が表示されます。 |
| 現在のデータとリクエストとの互換性がないことを警告するメッセージを無効にする | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| Report Builder リクエストをローカルファイルにログ (トラブルシューティング用) | リクエストをローカルファイルのログに記録できます。このログファイルはトラブルシューティングに使用します。 |
| 入力された値を変換... | フィルター制御に入力された値をフィルター表現とみなす前にセルの場所として変換します。<br>例えば、「靴」フィルターを使用してトップ 10 ページのリクエストを作成すると、リクエストには次のような内容のセルが表示されます。フィルター：トップ 1 ～ 10 ページ、ページに「靴」を含む |
| 新しいバージョンが利用可能な場合に更新 | 新しいバージョンがインストール可能な場合に通知するように指定します。 |
