---
description: Analysis Workspaceでのプロジェクト作成の基本について説明します
title: プロジェクトの作成
feature: Workspace Basics
role: User, Admin
source-git-commit: 6d1515ee21044941b4b79d18b4438e0647471c57
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# プロジェクトの作成

[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) Analysis Workspaceでは、組織内外の関係者と共有できる、ビジネスクリティカルな分析を表示できます。

Analysis Workspaceの使用を開始する方法に関する一般的な情報については、 [Analysis Workspaceの概要](/help/analyze/analysis-workspace/home.md).

次の節では、プロジェクトを作成し、任意のAnalysis Workspaceプロジェクトの主要な構築ブロックの追加を開始する方法について説明します。パネル、ビジュアライゼーションおよびコンポーネント。

## 空のプロジェクトまたはレポートからプロジェクトを作成する

1. Adobe Analyticsで、 [!UICONTROL **Workspace**].

1. 空のプロジェクトを作成するか、レポートからプロジェクトを作成するかを選択します。

   +++空のプロジェクトを作成

   1. の [!UICONTROL **Workspace**] タブで、 [!UICONTROL **プロジェクト**] 」タブで、 [!UICONTROL **プロジェクトを作成**].

   1. 空のプロジェクトと空のモバイルスコアカードのどちらを作成するかを選択します

      * **空のプロジェクト** ブラウザーから分析を共有する予定の場合
      * [**空のモバイルスコアカード**](/help/analyze/mobile-app/curator.md) Adobe Analyticsダッシュボードモバイルアプリから分析を共有する予定がある場合。
   1. 「[!UICONTROL **作成**]」を選択します。

+++

   +++レポートからのプロジェクトの作成

   1. の [!UICONTROL **Workspace**] タブで、 [!UICONTROL **レポート**] 」タブをクリックします。

   1. 使用するレポートを検索またはナビゲートして、表示されたら選択します。

      デフォルトでは、一連の標準レポートが使用可能です。 また、お客様が選択できるカスタムレポートが組織で作成されている場合もあります。

      詳しくは、 [Adobe Analyticsランディングページ](/help/analyze/landing.md).
+++

1. 次に、パネル、ビジュアライゼーションおよびコンポーネントをプロジェクトに追加する必要があります。 まず、Analysis Workspaceで、 [プロジェクトにパネルを追加する](#add-panels-to-the-project). その後、任意のパネルにビジュアライゼーションを追加できます。 最後に、任意のパネルまたはビジュアライゼーションにコンポーネントを追加できます。

## プロジェクトにパネルを追加する {#panels}

[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja) は、Analysis Workspaceの任意のプロジェクトの基盤です。 パネルを使用して、プロジェクトのコンテンツ（ビジュアライゼーションおよびコンポーネント）を整理します。

Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。

パネルを追加するには：

1. を選択します。 [!UICONTROL **パネル**] アイコンをクリックします。

   ![](assets/build-panels.png)

1. 追加するパネルを検索します。 左側のレールに表示されたら、プロジェクトにドラッグします。

1. パネルにビジュアライゼーションを追加します ( [プロジェクトへのビジュアライゼーションの追加](#add-visualizations-to-the-project).

   または、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトへのビジュアライゼーションの追加

[ビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja) （フリーフォームテーブル、棒グラフ、折れ線グラフなど）を使用して、データを有効にします。

>[!TIP]
>
>フリーフォームテーブルは、最も一般的なタイプのビジュアライゼーションで、インタラクティブなデータ分析の基盤となります。 Analysis Workspaceでフリーフォームテーブルを使用する方法について詳しくは、 [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

ビジュアライゼーションを追加するには：

1. を選択します。 **[!UICONTROL ビジュアライゼーション]** アイコンをクリックします。

   ![](assets/build-visualizations.png)

1. 追加するビジュアライゼーションを検索します。 左側のレールに表示されたら、プロジェクト内のパネルにドラッグします。

1. ビジュアライゼーションにコンポーネントを追加します。詳しくは、 [プロジェクトにコンポーネントを追加する](#add-components-to-the-project).

## プロジェクトにコンポーネントを追加する

[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) 任意のプロジェクトの実際のデータを構成します。 コンポーネントをビジュアライゼーションまたはパネルに追加できます。

>[!TIP]
>
>各コンポーネントについて詳しくは、左側のパネルでコンポーネントの名前の横にある情報アイコンを選択するか、 [Analytics コンポーネントガイド](/help/components/home.md).

コンポーネントを追加するには：

1. を選択します。 **[!UICONTROL コンポーネント]** アイコンをクリックします。

   ![](assets/build-components.png)

1. 追加するコンポーネントを検索します。 左側のパネルに表示されたら、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （オプション） [プロジェクトを保存して共有する](#save-and-share-the-project).

## プロジェクトを保存して共有する

Analysis Workspaceで分析を作成する場合、作業内容は次のようになります。 [自動保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

プロジェクトの構築が完了し、アクションにつながるインサイトを収集すると、そのプロジェクトを他のユーザーが利用できる状態になります。 プロジェクトを組織内のユーザーやグループと共有したり、組織外のユーザーと共有したりできます。 プロジェクトの共有について詳しくは、 [プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md).

