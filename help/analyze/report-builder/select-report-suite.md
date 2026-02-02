---
title: Report Builderでのレポートスイートの選択
description: Report Builderでレポートスイートを選択する方法を説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
source-git-commit: 6f7de360ac24261eabb46c6cfce99449261706de
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# レポートスイートを選択

ドロップダウンメニューからレポートスイートを選択するか、セルからレポートスイートを選択すると、新しいレポートスイートでデータブロックが自動的に更新されます。

## セルからレポートスイートを選択

セルからレポートスイートを選択すると、様々なレポートスイートを使用してデータブロックを簡単に更新できます。 別々のデータブロックを使用して完全に新しいレポートを作成する代わりに、セルから選択したレポートスイートでデータブロックを更新できます。

次の場合は、セルからレポートスイートを選択すると役立ちます。

* 構造が互いに類似または同一である複数のレポートスイート。
* カスタマイズされたコンポーネントやレイアウトを含む複雑なデータブロック形式。

セルからレポートスイートを選択するには、まずデータブロックを作成し、データブロック外のセルに複数のレポートスイートを割り当てます。 次に、**[!UICONTROL セルからのレポートスイート]** パネルを使用して、様々なレポートスイートのデータブロックを更新します。

1. データブロックを作成します。 データブロックの作成について詳しくは、[ データブロックの作成 ](/help/analyze/report-builder/create-a-data-block.md) を参照してください。

1. ![ レポートスイート ](/help/assets/icons/DataViewSelector.svg) で **[!UICONTROL データビューセレクター]** を選択します。

1. データブロック外で ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) を使用してセルを選択します。

1. ドラッグ&amp;ドロップを使用して、**[!UICONTROL セルからレポートスイートに追加するレポートスイートを選択]** から 1 つ以上のレポートスイートを追加します。 または、レポートスイートをダブルクリックして、「含まれるレポートスイート **[!UICONTROL リストにレポートスイートを追加]** ることもできます。

   * ![ 検索 ](/help/assets/icons/Search.svg)**[!UICONTROL _レポートスイートを選択_]** を使用して、レポートスイートを検索できます。
   * ![MoreSmall](/help/assets/icons/MoreSmall.svg) を使用してコンテキストメニューを開き、「レポートスイートを含む **[!UICONTROL リストでレポートスイートを上下に移動でき]** す。
   * ![ 含まれるレポートスイート ](/help/assets/icons/CrossSize75.svg) リストからレポートスイートを削除するには、**[!UICONTROL CrossSize75]** を使用します。

   ![ セルからレポートスイートを選択 ](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 「**[!UICONTROL 適用]**」を選択して、選択したレポートスイートを選択したセルに適用します。


## セルからレポートスイートを変更

1. シートのレポートスイートのセルの場所を選択します。
1. Report Builder ハブで、「**[!UICONTROL クイック編集]**」の「セルからのレポートスイート **[!UICONTROL リンク]** を選択します。
1. **[!UICONTROL レポートスイート]** ドロップダウンメニューからレポートスイートを選択します。

   ![ セルからレポートスイートを変更 ](assets/change-data-view-from-cell.png){zoomable="yes"}
1. オプションとして、「**[!UICONTROL 変更時にデータブロックを更新]**」を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。Report Builderは、選択したレポートスイートに基づいてデータブロックを更新します。
