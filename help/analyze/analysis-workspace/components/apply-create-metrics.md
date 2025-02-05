---
description: Analysis Workspace には、指標の使用方法が 2 つあります。
title: Analysis Workspace の指標
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 50%

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

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Use metrics](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]



## 計算指標の作成

計算指標を使用すると、単純な演算子や統計関数を使用して、指標が相互にどのように関連しているかを簡単に確認できます。

計算指標を作成する方法はいくつかあります。 選択した方法によって、計算指標をすべてのプロジェクトのコンポーネントリストから使用できるか、計算指標が作成されたプロジェクトでのみ使用できるかが決まります。

### すべてのプロジェクトの計算指標を作成

計算指標ビルダーを使用して、計算指標を作成できます。 この方法で作成した場合、計算指標はコンポーネントリストで使用できるので、組織全体のプロジェクトで使用できます。

計算指標ビルダーへのアクセス方法について詳しくは、[ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) を参照してください。

### 単一プロジェクトの計算指標の作成

作成したプロジェクトでのみ使用できるクイック計算指標を作成できます。

単一プロジェクトの計算指標を作成するには：

1. Analysis Workspaceで、計算指標を作成するプロジェクトを開きます。

1. フリーフォームテーブルで、1 つ以上のヘッダー列のセルを右クリックし、「**[!UICONTROL 選択から指標を作成]**」を選択します。

   ![ 選択範囲から作成を強調表示したWorkspace パネル ](assets/create-metric-from-selection.png)

1. このプロジェクトにのみ計算指標を作成するには、次のオプションから選択します。

   * [!UICONTROL **除算**]

   * [!UICONTROL **減算**]

   * [!UICONTROL **追加**]

   * [!UICONTROL **Multiply**]

   計算指標ビルダーを開いて、すべてのプロジェクトの計算指標を作成するには、「[!UICONTROL **計算指標ビルダーで開く**]」を選択して [ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) を続行します。

[計算指標： 実装なしの指標](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ja)（3:42）

## 様々なアトリビューションモデルとの指標の比較

アトリビューションモデルを別のアトリビューションモデルと素早く簡単に比較したい場合は、指標を右クリックし、「**[!UICONTROL アトリビューションモデルを比較]**」を選択します。

![アトリビューションの比較](assets/compare-attribution.png)

これにより、指標にドラッグして設定を 2 回おこなわなくても、アトリビューションモデルをすばやく簡単に相互比較できます。

## [!UICONTROL 累積平均] 関数を使用した指標スムージングの適用

以下は、このトピックに関するビデオです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ 累積平均 ](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

