---
description: 指標タイプとアトリビューションについて説明します。
title: 指標タイプとアトリビューション
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 100%

---

# 指標タイプとアトリビューション {#metric-type-attribution}

計算指標定義で指標の指標タイプと[アトリビューションモデル](#attribution-models)を設定できます。

1. 指標コンポーネントで「![設定](/help/assets/icons/Setting.svg)」を選択します。
1. ポップアップダイアログで以下を行います。

   ![指標タイプとアトリビューション](assets/cm-type-alloc.png)

   * 「**[!UICONTROL 指標タイプ]**」を指定します。

     | 指標タイプ | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 1 つの標準指標で構成される数式は、その標準指標に対応する計算指標以外の指標と同じデータを表示します。標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。 <p>例えば、![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 注文件数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 訪問回数]**&#x200B;は、その特定の行項目の注文件数をその特定の行項目の訪問回数で除算します。 |
     | **[!UICONTROL 総計]** | 各行項目のレポート期間の&#x200B;**[!UICONTROL 総計]**&#x200B;を使用します。数式が 1 つの総計指標で構成される場合、計算指標は行項目ごとに同じ総計数を表示します。総計指標は、合計データと比較する計算指標を作成する場合に役立ちます。 <p>例えば、![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 注文件数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計訪問回数]**&#x200B;は、特定の行項目に対する訪問回数だけでなく、すべての訪問回数に対する注文件数の割合を示します。この例では、計算指標で![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 訪問回数]**&#x200B;指標の&#x200B;**[!UICONTROL 総計]**&#x200B;を指定し、それが自動的に![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計訪問回数]**&#x200B;に変わります。 |

   * 「**[!UICONTROL アトリビューション]**」を指定します。

      1. 以下のいずれかを実行できます。

         * 30 日間のルックバックウィンドウを持つデフォルトの列アトリビューションモデル（ラストタッチ）を使用する場合は、「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を無効にします。
         * 「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を有効にします。**[!UICONTROL 列アトリビューションモデル]**&#x200B;ダイアログで以下を行います。

            * [アトリビューションモデル](#attribution-models)から&#x200B;**[!UICONTROL モデル]**&#x200B;を選択します。
            * 「**[!UICONTROL コンテナ]**」オプションから「[コンテナ](#container)」を選択します。
            * 「**[!UICONTROL ルックバックウィンドウ]**」オプションから「[ルックバックウィンドウ](#lookback-window)」を選択します。「**[!UICONTROL カスタム時間]**」を選択した場合は、期間を「**[!UICONTROL 分]**」から「**[!UICONTROL 四半期]**」までの単位で定義できます。

      1. デフォルト以外のアトリビューションモデルを適用するには、「**[!UICONTROL 適用]**」を選択します。キャンセルするには、「キャンセル」を選択します。

     デフォルト以外のアトリビューションモデルを既に定義してある場合は、「**[!UICONTROL 編集]**」を選択して、選択項目を変更します。

アトリビューションモデル、コンテナ、ルックバックウィンドウの使用例については、[例](#example)を参照してください。


## アトリビューションモデル {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="デフォルト以外のアトリビューションモデルを使用"
>abstract="選択した指標に対してデフォルト以外のアトリビューションモデルを有効にします。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="モデル"
>abstract="指標のアトリビューションモデルを選択します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="ラストタッチ"
>abstract="訪問者が閲覧した最後のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="ファーストタッチ"
>abstract="訪問者が閲覧した最初のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="線形"
>abstract="クレジットはすべてのディメンション値に均等に配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="パーティシペーション"
>abstract="訪問者が閲覧したすべてのディメンション値に 100%クレジットされます。<br/>列の合計は誇張されています。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 字型"
>abstract="最初のディメンション値に 40%、最後のディメンション値に 40%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="タイムディケイ"
>abstract="コンバージョンに最も近いディメンション値に、最も多くのクレジットを付与します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="アルゴリズム"
>abstract="クレジットは、統計的アルゴリズムに基づいて動的に決定されます。"

{{attribution-models-details}}


## コンテナ {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="コンテナ"
>abstract="コンテナを選択して、アトリビューションに必要な範囲を設定します。"

{{attribution-container}}


## ルックバックウィンドウ {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="ルックバックウィンドウ"
>abstract="この設定により、各コンバージョンに適用されるデータアトリビューションの期間が決まります。"

{{attribution-lookback-window}}

## 例

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->