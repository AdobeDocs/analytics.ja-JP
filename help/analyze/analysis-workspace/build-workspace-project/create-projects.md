---
description: Analysis Workspaceでのプロジェクト作成の基本について説明します
title: プロジェクトの作成
feature: Workspace Basics
role: User, Admin
source-git-commit: 98cffce26edc02b74747e05c35ff6625081e0cc6
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 6%

---

# プロジェクトの作成

[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) Analysis Workspaceでは、組織内外の関係者と共有できる、ビジネスクリティカルなデータを表示できます。

Analysis Workspaceの使用を開始する方法に関する一般的な情報については、 [Analysis Workspaceの概要](/help/analyze/analysis-workspace/home.md).

次の節では、プロジェクトを作成し、任意のAnalysis Workspaceプロジェクトの主要な構築ブロックの追加を開始する方法について説明します。パネル、ビジュアライゼーションおよびコンポーネント。

## 空のプロジェクトまたはテンプレートからプロジェクトを作成する

1. Adobe Analyticsで、 [!UICONTROL **Workspace**].

1. 空のプロジェクトを作成するか、テンプレートからプロジェクトを作成するかを選択します。

   +++空のプロジェクトを作成

   1. を選択します。 [!UICONTROL **プロジェクト**] 「 」タブで、「 [!UICONTROL **プロジェクトを作成**].

   1. 空のプロジェクトと空のモバイルスコアカードのどちらを作成するかを選択します

      * **空のプロジェクト** ブラウザーから分析を共有する予定の場合
      * [**空のモバイルスコアカード**](/help/analyze/mobile-app/curator.md) Adobe Analyticsダッシュボードモバイルアプリから分析を共有する予定がある場合。
   1. 「[!UICONTROL **作成**]」を選択します。

+++

   +++テンプレートからプロジェクトを作成する

   1. を選択します。 [!UICONTROL **レポート**] タブをクリックします。

   1. 使用するテンプレートを検索または移動して、表示されたら選択します。

      デフォルトでは、一連の標準テンプレートを使用できます。 さらに、組織でカスタムテンプレートを作成している場合は、その中から選択できます。

      詳しくは、 [Reports &amp; Analytics の概要](/help/analyze/reports-analytics/getting-started.md).
+++

1. 次に、パネル、ビジュアライゼーションおよびコンポーネントをプロジェクトに追加する必要があります。 まず、Analysis Workspaceで、 [プロジェクトにパネルを追加する](#add-panels-to-the-project). その後、任意のパネルにビジュアライゼーションを追加できます。 最後に、任意のパネルまたはビジュアライゼーションにコンポーネントを追加できます。

## プロジェクトにパネルを追加する {#panels}

[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja) は、Analysis Workspaceの任意のプロジェクトの基盤です。 プロジェクトのコンテンツ（ビジュアライゼーションおよびコンポーネント）を整理するために使用されます。 コンポーネントやビジュアライゼーションをプロジェクトに追加する前に、パネルを追加する必要があります。

Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。

パネルを追加するには：

1. を選択します。 [!UICONTROL **パネル**] アイコンをクリックします。

   ![](assets/build-panels.png)

1. 追加するパネルを検索します。 左側のレールに表示されたら、プロジェクトにドラッグします。

1. パネルにビジュアライゼーションを追加します ( [プロジェクトへのビジュアライゼーションの追加](#add-visualizations-to-the-project).

   または、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトへのビジュアライゼーションの追加

[ビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja) （フリーフォームテーブル、棒グラフ、折れ線グラフなど）を使用して、データを有効にします。

1. を選択します。 **[!UICONTROL ビジュアライゼーション]** アイコンをクリックします。

   ![](assets/build-visualizations.png)

1. 追加するビジュアライゼーションを検索します。 左側のレールに表示されたら、プロジェクト内のパネルにドラッグします。

1. ビジュアライゼーションにコンポーネントを追加します。詳しくは、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトにコンポーネントを追加する

[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) 任意のプロジェクトの実際のデータを構成します。 コンポーネントをビジュアライゼーションまたはパネルに追加できます。

1. を選択します。 **[!UICONTROL コンポーネント]** アイコンをクリックします。

   ![](assets/build-components.png)

1. 追加するコンポーネントを検索します。 左側のパネルに表示されたら、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

>[!TIP]
>
>   各コンポーネントについて詳しくは、左側のパネルでコンポーネントの名前の横にある情報アイコンを選択するか、 [Analytics コンポーネントガイド](/help/components/home.md).

