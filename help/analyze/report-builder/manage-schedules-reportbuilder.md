---
title: Adobe AnalyticsのReport Builderでスケジュール済みワークブックを管理する方法
description: Report Builderでスケジュール済みワークブックを管理する方法を説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 9ece9f6fcebdf308b6218aa50ab78af4f75ee8e7
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# スケジュールされたワークブックの管理

次の記事に記載されているように、メールで共有するか、クラウドの宛先に書き出すことにより、ワークブックをスケジュールできます。

* [メールでの共有によるワークブックのスケジュール設定](/help/analyze/report-builder/schedule-reportbuilder.md)

* [クラウドの宛先に書き出してワークブックをスケジュールする](/help/analyze/report-builder/report-builder-export.md)

次の節では、スケジュールされた後にワークブックを管理する方法について説明します。

## スケジュールされたワークブックの表示と管理

「**[!UICONTROL ワークブック]**」タブでは、スケジュールされたすべてのワークブックを表示および管理できます。

1. Report Builder ハブで **[!UICONTROL スケジュール]** を選択します

1. 「**[!UICONTROL ワークブック]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。

   ![ スケジュール済みワークブック ](assets/scheduled-workbooks.png){zoomable="yes"}

   アイコンの上にマウスポインターを置くと、スケジュールされたワークブックのステータスが表示されます。

   ![ 検索 ](/help/assets/icons/Search.svg) を使用して、スケジュールされた特定のワークブックを検索します。
表示する列を定義するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。

1. 1 つ以上のワークブックを選択します。

   ![ 選択したワークブックのスケジュール ](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   次のオプションがあります。

   | オプション | 説明 |
   |---|---|
   | ![編集](/help/assets/icons/Edit.svg) | 選択したブックのスケジュールを編集します。 |
   | ![ 履歴 ](/help/assets/icons/History.svg) | 選択したワークブックの履歴を表示します。 |
   | ![Pause](/help/assets/icons/Pause.svg) | 選択したワークブックのスケジュールを一時停止します。 |
   | ![ 再生 ](/help/assets/icons/Play.svg) | 選択したワークブックのスケジュールを再開します。 |
   | ![ダウンロード](/help/assets/icons/Download.svg) | 選択したワークブックを新しいワークブックにダウンロードします。 |
   | ![削除](/help/assets/icons/Delete.svg) | 選択したワークブックのスケジュールを削除します。 |


## スケジュールされたワークブックの履歴とステータス

スケジュールされたワークブックの履歴とステータスは、「**[!UICONTROL 履歴]**」タブで表示できます。

1. Report Builder ハブで **[!UICONTROL スケジュール]** を選択します。

1. 「**[!UICONTROL 履歴]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。

   ![ スケジュール済み履歴 ](assets/scheduled-workbooks-history.png){zoomable="yes"}

   リスト内の特定のワークブックを検索するには、![ 検索 ](/help/assets/icons/Search.svg) を使用します。
表示する列を定義するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。

   **[!UICONTROL 履歴]** タブでは、スケジュールされた各タスクのステータスを確認できます。 個別の行に、スケジュールされた各タスクのステータス変更が記載されます。

   * ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) は、ワークブックが正常に送信されたことを示します。
   * ![AlertRed](/help/assets/icons/AlertRed.svg) は、エラーが発生したことを示します。

または、選択した 1 つ以上のワークブックの ![ 履歴 ](/help/assets/icons/History.svg) を **[!UICONTROL ワークブック]** タブで選択できます。 このアクションは、選択によってフィルタリングされたリストを含む **[!UICONTROL 履歴]** タブを表示します。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択してフィルターを削除します。


