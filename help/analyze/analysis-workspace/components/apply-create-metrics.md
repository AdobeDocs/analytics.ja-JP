---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: Analysis Workspace の指標
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: eb2b5e078fdb299ed7d82fed54e98e5a40059624
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 30%

---

# 指標

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

## 指標のタイプ

アドビでは、Analysis Workspace で使用するためのいくつかのタイプの指標を提供しています。

* **標準指標**：プロジェクトで使用するほとんどの指標は標準指標です。例には、[ページビュー数](/help/components/metrics/page-views.md)、[収益](/help/components/metrics/revenue.md)または[カスタムイベント](/help/components/metrics/custom-events.md)が含まれます。詳しくは、コンポーネントユーザーガイドの[指標の概要](/help/components/metrics/overview.md)を参照してください。

  ![標準指標](assets/standard-metric.png)

* **計算指標**：標準指標、静的数値、アルゴリズム関数に基づくユーザー定義の指標です。ユーザー定義の計算指標では、使用可能なコンポーネントのリストに電卓アイコンが表示されます。詳しくは、コンポーネントユーザーガイドの[計算指標の概要](/help/components/c-calcmetrics/cm-overview.md)を参照してください。

  ![計算指標](assets/calculated-metric.png)

* **計算指標テンプレート**：計算指標と同様に動作するアドビ定義の指標です。これらを Workspace プロジェクトでそのまま使用することも、コピーを保存してロジックをカスタマイズすることもできます。計算指標テンプレートでは、使用可能なコンポーネントのリストに Adobe アイコンが表示されます。

  ![計算指標テンプレート](assets/calculated-metric-template.png)

## Analysis Workspace での指標の使用

指標は、Analysis Workspace 内で様々な方法で使用できます。 Analysis Workspaceに指標やその他のタイプのコンポーネントを追加する方法について詳しくは、[Analysis Workspaceでのコンポーネントの使用 ](/help/analyze/analysis-workspace/components/use-components-in-workspace.md) を参照してください。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Use metrics](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

## 計算指標の作成

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。

計算指標を作成する方法はいくつかあります。 選択した方法によって、計算指標をすべてのプロジェクトのコンポーネントリストから使用できるか、計算指標が作成されたプロジェクトでのみ使用できるかが決まります。

### すべてのプロジェクトの計算指標を作成

計算指標ビルダーを使用して、計算指標を作成できます。 この方法で作成した場合、計算指標はコンポーネントリストで使用できるので、組織全体のプロジェクトで使用できます。

計算指標ビルダーへのアクセス方法について詳しくは、[ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) を参照してください。

### 単一プロジェクトの計算指標の作成

計算指標を作成したプロジェクトでのみ使用できる計算指標をすばやく作成できます。

単一プロジェクトの計算指標を作成するには：

1. Analysis Workspaceで、計算指標を作成するプロジェクトを開きます。

1. フリーフォームテーブルで、1 つの列の列ヘッダーを右クリックします。

   または

   Shift キーを押しながら 2 つの列を選択し、選択した列の 1 つを右クリックします。

1. 「**[!UICONTROL 選択から指標を作成]**」を選択します

   ![ 選択範囲から作成を強調表示したWorkspace パネル ](assets/create-metric-from-selection.png)

1. このプロジェクトにのみ計算指標を作成するには、使用可能なオプションから選択します。

   1 つの列を選択した場合、次のオプションを使用できます。

   * [!UICONTROL **平均**]：列のディメンション要素のセットの平均値を表示する新しい列を作成します。 これは [Mean](/help/components/c-calcmetrics/cm-reference/cm-functions.md#mean) 関数を使用します。

   * [!UICONTROL **中央値**]：列のディメンション要素セットの中央値を表示する新しい列を作成します。 [Median](/help/components/c-calcmetrics/cm-reference/cm-functions.md#median) 関数を使用します。

   * [!UICONTROL **列の最大値**]：列のディメンション要素のセットの中の最大値を表示する新しい列を作成します。 これは [Column Maximum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-maximum) 関数を使用します。

   * [!UICONTROL **列の最小値**]：列のディメンション要素のセットの最小値を表示する新しい列を作成します。 これは [Column Minimum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-minimum) 関数を使用します。

   * [!UICONTROL **列の合計**]：列内の（1 つのディメンションのすべての要素の）指標の数値をすべて加算する新しい列を作成します。 [Column Sum](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-sum) 関数を使用します。

   2 つの列を選択した場合は、次のオプションを使用できます。

   * [!UICONTROL **除算**]：選択した 2 つの列の値を除算する新しい列を作成します。

   * [!UICONTROL **減算**]：選択した 2 つの列の値を減算する新しい列を作成します。

   * [!UICONTROL **追加**]：選択した 2 つの列の値を追加する新しい列を作成します。

   * [!UICONTROL **乗算**]：選択した 2 つの列の値を乗算する新しい列を作成します。

   * [!UICONTROL **変化率**]：選択した 2 つの列の間の変化率を示す新しい列を作成します。

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルとすばやく比較するには、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![アトリビューションの比較](assets/compare-attribution.png)

このショートカットを使用すると、指標をドラッグして 2 回設定することなく、1 つのアトリビューションモデルを別のアトリビューションモデルと比較できます。

## [!UICONTROL 累積平均] 関数を使用した指標スムージングの適用

以下は、このトピックに関するビデオです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 累積平均 ](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

