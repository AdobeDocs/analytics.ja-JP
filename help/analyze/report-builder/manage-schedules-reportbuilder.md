---
title: スケジュールされたブックをReport Builderで管理する
description: スケジュールされたブックをReport Builderで管理する方法を説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fc0357f7-1762-47e4-9691-5fbdb177d45b
source-git-commit: 6f55f750fa7243a445057dfb47d31d7cdeaed5dc
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 5%

---

# スケジュールされたワークブックの管理

次の記事の説明に従って、電子メールまたはクラウドの宛先にエクスポートして共有するブックをスケジュールできます。

* [メールでの共有によるワークブックのスケジュール設定](/help/analyze/report-builder/schedule-reportbuilder.md)

* [クラウドの宛先に書き出してワークブックをスケジュールする](/help/analyze/report-builder/report-builder-export.md)

次の節では、スケジュールされた後にワークブックを管理する方法について説明します。

## スケジュールされたワークブックの表示と管理

「**[!UICONTROL ワークブック]**」タブでは、スケジュールされたすべてのワークブックを表示および管理できます。

1. Report Builder ハブで **[!UICONTROL スケジュール]** を選択します

1. 「**[!UICONTROL ワークブック]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。 （または、[**[!UICONTROL 従来]**]タブを選択して、新しいReport Builderに移行する必要がある従来のブックの一覧を表示することもできます）。

   ![スケジュールされたブック](assets/scheduled-workbooks.png){zoomable="yes"}

1. 次のいずれかの操作を行います。

   * アイコンにカーソルを合わせると、スケジュールされたブックのステータスが表示されます。

   * 検索フィールド ![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg) で、スケジュールされた特定のワークブックを検索します。

   * 列アイコン ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択して、表示する列を定義します。

   * フィルターアイコン ![&#x200B; フィルターアイコン &#x200B;](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択し、「[!UICONTROL **すべて表示**] を選択して、特定の組織でスケジュールされたすべてのワークブックを表示します。

1. 1 つ以上のワークブックを選択します。

   ![&#x200B; 選択したワークブックのスケジュール &#x200B;](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   次のオプションがあります。

   | オプション | 説明 |
   |---|---|
   | ![編集](/help/assets/icons/Edit.svg) | 選択したブックのスケジュールを編集します。 |
   | ![履歴](/help/assets/icons/History.svg) | 選択したワークブックの履歴を表示します。 |
   | ![一時停止](/help/assets/icons/Pause.svg) | 選択したワークブックのスケジュールを一時停止します。 |
   | ![&#x200B; 再生 &#x200B;](/help/assets/icons/Play.svg) | 選択したワークブックのスケジュールを再開します。 |
   | ![ダウンロード](/help/assets/icons/Download.svg) | 選択したブックを新しいブックにダウンロードします。 |
   | ![削除](/help/assets/icons/Delete.svg) | 選択したブックのスケジュールを削除します。 |


## スケジュールされたブックの履歴と状態

スケジュールされたブックの履歴と状態は、[**[!UICONTROL 履歴]**]タブで確認できます。

1. Report Builder ハブで **[!UICONTROL スケジュール]** を選択します。

1. 「**[!UICONTROL 履歴]**」タブを選択します。 スケジュールされたすべてのワークブックのリストが表示されます。

   ![&#x200B; スケジュール済み履歴 &#x200B;](assets/scheduled-workbooks-history.png){zoomable="yes"}

   リスト内の特定のワークブックを検索するには、![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg) を使用します。
表示する列を定義するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用します。

   **[!UICONTROL 履歴]** タブでは、スケジュールされた各タスクのステータスを確認できます。 個別の行に、スケジュールされた各タスクのステータス変更が記載されます。

   * ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)は、ブックが正常に送信されたことを示します。
   * ![AlertRed](/help/assets/icons/AlertRed.svg)は、エラーが発生したことを示します。

または、[![ブック](/help/assets/icons/History.svg)]タブで選択した1つ以上のブックの&#x200B;**[!UICONTROL 履歴]**&#x200B;を選択できます。 このアクションにより、選択でフィルターされたリストを含む&#x200B;**[!UICONTROL 履歴]**&#x200B;タブが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg)を選択してフィルターを削除します。
