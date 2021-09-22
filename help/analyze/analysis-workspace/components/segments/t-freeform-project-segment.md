---
description: Analysis Workspace でセグメントを使用します。
title: セグメント
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
feature: Workspace Basics
role: User, Admin
exl-id: 67112e13-4d0a-4d77-be50-496c3d28779c
source-git-commit: 31507092e659fa08a50e00f91bd36411e354cb21
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 42%

---


# セグメント {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

Workspaceでは、複雑さの程度や、このプロジェクトにのみ適用する必要があるかどうかなどに応じて、様々なタイプのセグメントを作成できます。 セグメントタイプの概要を次に示します。

| セグメントタイプ | どこで？ | 適用可能な場所 | 使用するタイミング |
| --- | --- | --- | --- |
| コンポーネントリストセグメント | 「+」をクリックすると、[セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)が表示されます。 | すべてのWorkspaceプロジェクト | より複雑なセグメントでは、順次セグメント |
| クイックセグメント | [クイックセグメントビルダー](/help/analyze/analysis-workspace/components/segments/quick-segments.md) | プロジェクトレベルで使用できますが、セグメントリストに保存して追加できます。 | 1つ以上のルールを柔軟に追加/編集 |
| アドホックセグメント： |  |  |  |
|  — アドホックワークスペースプロジェクトセグメント | [プロジェクトのセグメントドロップゾーンにドラッグ&amp;ドロップします](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md) | プロジェクトレベルで使用できますが、セグメントリストに保存して追加できます。 | デフォルトの単一ルールセグメント（制限なし） |
|  — 計算指標ベースのセグメント | [計算指標ビルダー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html) | 個々の計算指標を追加するには | 指標定義内でのセグメントの適用 |
| - VRSベースのセグメント | [仮想レポートスイートビルダー](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) | 個々の仮想レポートスイートへ | VRS定義内でのセグメントの適用 |

Analysis Workspaceでのセグメントの使用に関するビデオを紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/23977/?quality=12)

## セグメントの作成 {#section_693CFADA668B4542B982446C2B4CF0F5}

Analysis Workspaceでは、様々なタイプのセグメントを作成できます。

* [クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md)
* [アドホックセグメント](/help/analyze/analysis-workspace/components/segments/ad-hoc-segments.md)
* セグメントライブラリで終わる通常のコンポーネントリストセグメント（以下を参照）

### コンポーネントリストセグメントの作成 {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

コンポーネントメニューの下のセグメントレールにが表示されます。
* 自分または自分の会社が作成したセグメント
* セグメントテンプレート(Adobeアイコンで示されます)

![](assets/segment_icons.png)

このタイプのセグメントを作成するには、2つのオプションがあります。 どちらも、Adobe Analyticsの[セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)に移動します。

* 左側のレールで、「[!UICONTROL セグメント]」の横のプラス記号(+)をクリックします。

![](assets/create-seg.png)

 または

* [!UICONTROL コンポーネント] > [!UICONTROL セグメント]に移動し、[!UICONTROL +追加]をクリックします。


### セグメントを適用するその他の方法 {#section_10FF2E309BA84618990EA5B473015894}

>[!VIDEO](https://video.tv.adobe.com/v/30994/?quality=12)

フリーフォームプロジェクトにセグメントを適用するには、他にもいくつかの方法があります。

| アクション | 説明 |
|--- |--- |
| 選択からセグメントを作成 | インラインセグメントを作成します。このセグメントは、オープンプロジェクトにのみ適用し、Analytics セグメントとして保存されません。1. 行を選択します。2. 選択範囲を右クリックします。3. 「*選択からセグメントを作成*」をクリックします。 |
| コンポーネント／新しいセグメント | セグメントビルダーを表示します。セグメント化について詳しくは、[セグメントビルダー](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=ja)を参照してください。 |
| 共有／プロジェクトを共有または共有／プロジェクトデータをキュレート | [キュレーションおよび共有](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=ja#concept_4A9726927E7C44AFA260E2BB2721AFC6)では、プロジェクトに適用するセグメントを、受信者に共有された分析で使用する方法について学習します。 |
| ディメンションとしてセグメントを使用 | ビデオ：[Analysis Workspace でセグメントをディメンションとして使用する](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/using-segments-as-dimensions-in-analysis-workspace.html?lang=ja) |

## Segment IQ

セグメントIQ（セグメント比較とも呼ばれます）は、次の機能で構成されます。

* [ セグメント比較パネル：](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)Segment IQ のコア機能。2 つのセグメントをパネルにドラッグし、統計的に有意な違いと 2 つのオーディエンス間の重複を示す包括的なレポートを表示します。
* [フォールアウトでのセグメントの比較：](/help/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md)フォールアウトビジュアライゼーションのコンテキストで、異なるオーディエンスを相互に比較する方法を確認します。

## 詳細情報

Adobe Analyticsでのセグメント化の詳細な説明については、[こちら](/help/components/segmentation/seg-overview.md)を参照してください。