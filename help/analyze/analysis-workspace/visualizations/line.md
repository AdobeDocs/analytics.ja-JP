---
description: 折れ線グラフ ビジュアライゼーションを使用すると、トレンド（時間ベース）のデータセットを視覚化できます。
title: 行
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 9035ea758a5e84812460c042685eae954303cc8a
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 94%

---

# 行 {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="行"
>abstract="一定期間にわたる値の変化を示す、折れ線グラフのビジュアライゼーションを作成します。折れ線グラフのビジュアライゼーションは、ディメンションとして時間を使用する場合にのみ使用できます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** の折れ線グラフビジュアライゼーションについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** バージョンについて詳しくは、[折れ線グラフ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/line)を参照してください。_

>[!ENDSHADEBOX]

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 折れ線グラフ]**&#x200B;ビジュアライゼーションでは、時間の経過に伴う値の変化を確認できるように、折れ線で指標が表されます。折れ線グラフビジュアライゼーションは、時間がディメンションとして使用される場合にのみ使用できます。

![行のビジュアライゼーション](assets/line-viz.png)


## 設定

[ビジュアライゼーション設定](freeform-analysis-visualizations.md#settings)の一部として、特定の折れ線グラフビジュアライゼーション設定を使用できます。

| 設定 | 説明 |
|---|---|
| **[!UICONTROL 精度]** | 精度ドロップダウンから選択して、トレンドビジュアライゼーションを日別から週別、月別などに変更できます。データソーステーブルの精度も更新されます。 |
| **[!UICONTROL 最小値を表示]** <br/>**[!UICONTROL 最大値を表示&#x200B;]** | 最小値と最大値のラベルをオーバーレイして、指標の最小値と最大値をハイライト表示できます。メモ：最小値と最大値は、ディメンション内のすべての値ではなく、ビジュアライゼーション内に表示されたデータポイントから得られます。<br/>![最小値と最大値のラベルを持つオーバーレイ。](assets/min-max-labels.png) |
| **[!UICONTROL トレンドラインを表示]** | 回帰または移動平均トレンドラインを線系列に追加できます。トレンドラインは、データのパターンをより明確に表現するのに役立ちます。選択した場合、リストからモデルを選択します。使用可能なモデルの概要および説明について詳しくは、[モデル](#models)を参照してください。<br/>![線形トレンドライン](assets/show-linear-trendline.png)。<p>**ヒント** トレンドラインは、今日（部分的なデータ）や将来の日付を含まないデータに適用することをお勧めします。 本日または未来の日付は、トレンドラインをゆがめます。ただし、未来の日付を含める必要がある場合は、データからゼロを削除して、それらの日のゆがみを防ぎます。 ビジュアライゼーションのデータソーステーブルに移動し、指標列を選択して、**[!UICONTROL 列設定]**／**[!UICONTROL ゼロを値なしで解釈]**&#x200B;を有効にします。</p> |

### モデル

すべての回帰モデルのトレンドラインは、通常の最小二乗法を使用して求めます。

| モデル | 説明 |
| --- | --- |
| **[!UICONTROL 線形]** | 単純な線形データセットに対して最適な直線を作成します。この直線は、データが一定速度で増減する場合に便利です。数式：`y = a + b * x` |
| **[!UICONTROL 対数]** | 最適な曲線を作成し、データの変化率が急速に増減し、次にレベルアウトする場合に便利です。対数近似曲線には、負の値と正の値を使用できます。数式：`y = a + b * log(x)` |
| **[!UICONTROL 指数]** | 曲線を作成します。データが一貫して加速し上昇または下降する場合に便利です。データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。数式：`y = a + e^(b * x)` |
| **[!UICONTROL 累乗]** | 曲線を作成します。これは、特定の速度で増加する測定値を比較するデータセットに便利です。データに 0 または負の値が含まれる場合は、このオプションを使用しないでください。数式：`y = a * x^b` |
| **[!UICONTROL 二次方程式]** | 放物線（上または下に凹面）のような形状のデータセットに最適なデータを検索します。数式：`y = a + b * x + c * x^2` |
| **[!UICONTROL 移動平均]** | 平均値のセットに基づいて、滑らかなトレンドラインを作成します。移動平均は、ローリング平均とも呼ばれ、特定数のデータポイント（「[!UICONTROL 精度]」セクションで決定される）を使用して、それらを平均し、その平均値を折れ線グラフのポイントとして使用します。例えば、7 日の移動平均や 4 週間の移動平均があります。 |

>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[ビジュアライゼーション設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[ビジュアライゼーションコンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

