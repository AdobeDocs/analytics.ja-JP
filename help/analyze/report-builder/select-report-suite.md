---
title: Report Builderでレポートスイートを選択する
description: Report Builderでレポートスイートを選択する方法について説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
TQID: https://experienceleague.adobe.com/eqAH1gQYgJ05VVa7THd7taOB7S3mhzyOk-29zQHoIxM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 1%

---

# レポートスイートを選択

ドロップダウンメニューからレポートスイートを選択するか、セルからレポートスイートを選択して、新しいレポートスイートでデータブロックを自動的に更新できます。

## セルからレポートスイートを選択

セルからレポートスイートを選択すると、異なるレポートスイートを使用してデータブロックを簡単に更新できます。 データブロックを個別に使用して完全に新しいレポートを作成する代わりに、セルから選択したレポートスイートでデータブロックを更新できます。

セルからレポートスイートを選択すると、次のような場合に役立ちます。

* 構造内の類似または同一の複数のレポートスイート。
* カスタマイズされたコンポーネントやレイアウトを含む複雑なデータブロック形式。

セルからレポートスイートを選択するには、まずデータブロックを作成し、複数のレポートスイートをデータブロック外のセルに割り当てます。 次に、セル ]**の**[!UICONTROL  レポートスイートを使用して、異なるレポートスイートからデータブロックを更新します。

1. データブロックを作成します。 データブロックの作成について詳しくは、[ データブロックの作成](/help/analyze/report-builder/create-a-data-block.md)を参照してください。

1. **[!UICONTROL レポートスイート]**&#x200B;の![DataViewSelector](/help/assets/icons/DataViewSelector.svg)を選択します。

1. データブロック外の![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)を使用してセルを選択します。

1. ドラッグ&amp;ドロップを使用して、**[!UICONTROL レポートスイートから1つ以上のレポートスイートを追加し、セル]**&#x200B;からレポートスイートに追加します。 または、レポートスイートをダブルクリックして、レポートスイートを含む&#x200B;**[!UICONTROL レポートスイート]** リストに追加することもできます。

   * ![検索](/help/assets/icons/Search.svg) **[!UICONTROL _レポートスイートを選択_]**&#x200B;して、レポートスイートを検索できます。
   * ![MoreSmall](/help/assets/icons/MoreSmall.svg)を使用してコンテキストメニューを開き、**[!UICONTROL レポートスイートが含まれる]** リストでレポートスイートを上下に移動できます。
   * ![CrossSize75](/help/assets/icons/CrossSize75.svg)を使用して、含まれる&#x200B;**[!UICONTROL レポートスイート]**&#x200B;のリストからレポートスイートを削除します。

   ![ セルからレポートスイートを選択](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 選択したレポートスイートを選択したセルに適用するには、**[!UICONTROL 適用]**&#x200B;を選択します。


## セルからレポートスイートを変更する

1. シート内のレポートスイートのセルの場所を選択します。
1. Report Builder ハブで、**[!UICONTROL クイック編集]**&#x200B;で「**[!UICONTROL セルからのレポートスイート]**」リンクを選択します。
1. **[!UICONTROL レポートスイート]** ドロップダウンメニューからレポートスイートを選択します。

   ![ セルからレポートスイートを変更](assets/change-data-view-from-cell.png){zoomable="yes"}
1. オプションで、**[!UICONTROL 変更時にデータブロックを更新]**&#x200B;を選択します。

1. 「**[!UICONTROL 適用]**」を選択します。 Report Builderは、選択したレポートスイートに基づいてデータブロックを更新します。
