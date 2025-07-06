---
description: パーティシペーション指標の作成方法を説明します。
title: パーティシペーション指標
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# パーティシペーション指標


パーティシペーション指標は、ディメンション（ページビューなど）の個々の値が、特定の指標（注文など）を含む訪問にどのように貢献し、またはどのように参加するかを定量化するために使用されます。

次の手順では、パーティシペーション指標の作成方法を示します。

1. [ 計算指標を作成 ](../cm-workflow.md) し、[ 計算指標ビルダー ](cm-build-metrics.md) で、指標に `Orders (Visit Participation)` などの名前を付けます。
1. 成功イベントを含む指標（例：[!DNL Online Orders]）を [!UICONTROL **[!UICONTROL &#x200B; 定義 &#x200B;]**] 領域にドラッグします。
1. 指標の ![ 歯車 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) を選択します。
1. 表示されるポップアップで、**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を選択して [ パーティシペーション ](m-metric-type-alloc.md#attribution-models) に対するそのイベントの **[!UICONTROL アトリビューションモデル]** を定義し、**[!UICONTROL コンテナ]** に対して [!UICONTROL &#x200B; 訪問 &#x200B;] を選択します。 「**[!UICONTROL 適用]**」を選択して確定します。


   ![ モデルとしてパーティシペーションが選択され、コンテナに対して訪問が選択されていることを示す列アトリビューションモデルのポップアップ ](assets/participation-setup.png)

   **（分割|訪問回数|30 日間）** 指標コンポーネント名に追加されます。



1. 「[!UICONTROL **保存**]」を選択して、指標を保存します。
1. レポートで計算指標を使用します。 例えば、レポート内の計算 [!DNL Orders (Session Participation)] 指標を使用して、どの顧客層が注文を含むセッションに貢献（または参加）したかを示します。

   ![ 顧客の階層と注文を示すフリーフォームテーブル。](assets/participation-pages-customer-tier.png)


<!--

The following information explains how to create a metric that shows which pages contributed to (or participated in) visits that contained an order.

This type of information could be useful for any content owner.

>[!NOTE]
>
>You can enable participation metrics in the Admin Tools, but only for custom events 1 - 100.

1. Begin creating a calculated metric, as described in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. In the Calculated metrics builder, name the metric "Participation".

1. Drag the success event "Orders" into the Definition canvas.

1. Change the [attribution model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. Select **[!UICONTROL Visit]** lookback. The definition should look similar to this:

   ![](assets/participation.png)

1. Select [!UICONTROL **Save**] to save the metric.

1. Use the calculated metric in a **[!UICONTROL Pages]** report.

    ![](assets/participation-pages.png)

1. (Optional) Share the metric with other users in your organization, as described in [Share calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
-->