---
description: Analysis Workspaceでプロジェクトにコンポーネントを追加する方法を説明します
title: Analysis Workspace でのコンポーネントの使用
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 16%

---

# Analysis Workspace でのコンポーネントの使用

コンポーネントは、Analysis Workspaceの任意のプロジェクトの実際のデータを構成します。 コンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成されています。 コンポーネントをビジュアライゼーションまたはパネルにドラッグすることで、プロジェクトに追加できます。

追加できるコンポーネントのタイプについて詳しくは、[ コンポーネントの概要 ](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) を参照してください。

>[!TIP]
>
>各コンポーネントについて詳しくは、Analytics の左側のパネルでコンポーネント名の横にある情報アイコンをクリックするか、『 [Analysis Workspace コンポーネントガイド ](/help/components/home.md) を参照してください。

## プロジェクトへのコンポーネントの追加の開始

1. [Analysis Workspaceでプロジェクトを作成します ](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) まだ作成していない場合は。

1. Analysis Workspaceのプロジェクトに [ パネルを追加 ](/help/analyze/analysis-workspace/c-panels/panels.md) または [ ビジュアライゼーションを追加 ](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) します。

   空のプロジェクトにコンポーネントを追加すると、フリーフォームテーブル ビジュアライゼーションが自動的に作成されます。

1. 左側のパネルにある&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンを選択します。

   ![](assets/build-components.png)

1. 追加するコンポーネントまでスクロールまたは検索し、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （任意）コンポーネントをパネルヘッダーのセグメントドロップゾーンにドラッグします。

   セグメントは、パネル内のすべてのコンテンツに適用されます。

   パネル上のセグメントドロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analyze/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

   ![ドロップゾーンへのセグメントのドロップ](assets/segment-dropzone.png)

1. 詳しくは、追加するコンポーネントのタイプに応じて、次のいずれかの節に進みます。

   * [プロジェクトへのディメンションの追加](#add-dimensions-to-a-project)

   * [プロジェクトへの指標の追加](#add-metrics-to-a-project)

   * [プロジェクトへのセグメントの追加](#add-segments-to-a-project)

   * [プロジェクトへの日付範囲の追加](#add-date-ranges-to-a-project)

## プロジェクトへのディメンションの追加

[Dimension](/help/components/dimensions/overview.md) は、通常、文字列値を含むAdobe Analyticsの変数です。 一般的なディメンションには、[ページ](/help/components/dimensions/page.md)、[参照ドメイン](/help/components/dimensions/referring-domain.md)、[eVar](/help/components/dimensions/evar.md) があります。一方、[指標](/help/components/metrics/overview.md)には、ディメンションに結び付く数値が含まれます。基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトへのディメンションの追加を開始します。

1. 次のいずれかの方法を選択して、ディメンションを追加し、分析するデータのタイプを決定します。

   * ディメンションをAnalysis Workspaceのビジュアライゼーション（フリーフォームテーブルなど）にドラッグします。

     ![ プロジェクトへのディメンションの追加 ](assets/add-dimensions.png)

   * [ プロジェクトへのセグメントの追加 ](#add-segments-to-a-project) の説明に従って、左側のパネルから 1 つ以上のディメンションをセグメントドロップゾーンにドラッグして、アドホックセグメントを作成します。

     ![ドロップゾーンへのセグメントのドロップ](assets/segment-dropzone.png)

1. （任意）Analysis Workspace内のディメンションおよびディメンション項目を、他のコンポーネントで分類できます。

   詳しくは、[ ディメンションの分類 ](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) を参照してください。

Analysis Workspaceでのディメンションの使用方法について詳しくは、[ ディメンションのプレビュー ](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md)、[ ディメンションの分類 ](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) および [ 時間分割ディメンション ](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) を参照してください。

## プロジェクトへの指標の追加

[ 指標 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md) を使用すると、Analysis Workspaceでデータポイントを数量化できます。 これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

Analysis Workspaceでプロジェクトに指標を追加するには：

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトに指標を追加し始めます。

1. Analysis Workspaceに指標を追加するには、次のいずれかの方法を選択します。

   * 空のフリーフォームテーブルの指標ドロップゾーンに指標をドラッグすると、プロジェクトの日付期間中のその指標のトレンドを確認できます。

     ![ プロジェクトへの指標の追加 ](assets/add-metrics.png)

   * ディメンションが存在する場合に指標をドラッグすると、その指標を各ディメンション項目と比較して確認できます。

   * 指標を既存の指標ヘッダーの上にドラッグすると、指標を置き換えることができます。

   * 指標をヘッダーの横にドラッグすると、両方の指標を並べて確認できます。

Analysis Workspaceでの指標の使用方法について詳しくは、[ 指標 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md) を参照してください。

## プロジェクトへのセグメントの追加

[ セグメント ](/help/components/segmentation/seg-overview.md) を使用すると、特性や特定のインタラクションに基づいて訪問者のサブセットを識別できます。

Analysis Workspaceでは、次のいずれかの方法でセグメントを使用できます。

### パネルへのセグメントの追加

パネルにセグメントを追加すると、そのセグメントはパネル内のすべてのコンテンツに適用されます。

パネル上のセグメントドロップゾーンを使用してパネルをフィルタリングする方法について詳しくは、「[ パネルの概要 ](/help/analyze/analysis-workspace/c-panels/panels.md)」の [ ドロップゾーン ](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) を参照してください。

### フリーフォームテーブルの列へのセグメントの追加

フリーフォームテーブルの列にセグメントを追加すると、そのセグメントはテーブルの列内のすべてのコンテンツに適用されます。

### 計算指標の作成時にセグメントを使用

計算指標ビルダーでは、指標の定義内にセグメントを適用できます。

詳しくは、[ セグメント化指標 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) を参照してください。

## プロジェクトへの日付範囲の追加

[ 日付範囲 ](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) は、Analysis Workspaceでのレポート時間枠を決定します。プロジェクト内の 1 つ以上のパネルに適用できます。

各パネルには、デフォルトで日付範囲が含まれています。 パネルの日付範囲を更新する方法はいくつかあります。 Analysis Workspaceのパネルの日付範囲を更新する 1 つの方法は、日付範囲コンポーネントを左パネルからドラッグすることです。

1. [ プロジェクトへのコンポーネントの追加を開始 ](#begin-adding-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトへの日付範囲の追加を開始します。

1. 日付範囲を左側のパネルから、パネルの右上部分の現在の日付範囲にドラッグします。

   ![ 日付範囲をドロップ ](assets/daterange-drop.png)

Analysis Workspaceでのカレンダーと日付範囲の使用方法について詳しくは、[ カレンダーと日付範囲の概要 ](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) を参照してください。
