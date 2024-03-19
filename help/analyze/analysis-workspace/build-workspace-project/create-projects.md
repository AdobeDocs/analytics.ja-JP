---
description: Analysis Workspace でのプロジェクト作成の基本について説明します。
title: プロジェクトの作成
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: ht
source-wordcount: '691'
ht-degree: 100%

---

# Analysis Workspace でのプロジェクトの作成

Analysis Workspace の[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)では、組織内外の関係者と共有できる、ビジネスクリティカルな分析を表示できます。

Analysis Workspace の使用を開始する方法について詳しくは、[Analysis Workspace の概要](/help/analyze/analysis-workspace/home.md)を参照してください。

次の節では、プロジェクトを作成し、任意の Analysis Workspace プロジェクトの主要な構成要素（パネル、ビジュアライゼーション、コンポーネント）の追加を開始する方法について説明します。

## 空のプロジェクトまたはレポートからプロジェクトの作成

1. Adobe Analytics で、「[!UICONTROL **ワークスペース**]」を選択します。

1. 空のプロジェクトを作成するか、レポートからプロジェクトを作成するかを選択します。

   +++空のプロジェクトを作成

   1. 「[!UICONTROL **ワークスペース**]」タブで、ページの左側にある「[!UICONTROL **プロジェクト**]」タブを選択し、「[!UICONTROL **プロジェクトを作成**]」を選択します。

   1. 空のプロジェクトまたは空のモバイルスコアカードのどちらを作成するかを選択します。

      * **空のプロジェクト**：ブラウザーから分析を共有する予定がある場合。
      * [**空のモバイルスコアカード**](/help/analyze/mobile-app/curator.md)：Adobe Analytics ダッシュボードモバイルアプリから分析を共有する予定がある場合。

   1. 「[!UICONTROL **作成**]」を選択します。

+++

   +++レポートからプロジェクトを作成

   1. 「[!UICONTROL **ワークスペース**]」タブで、ページの左側にある「[!UICONTROL **レポート**]」タブを選択します。

   1. 使用するレポートを検索または使用するレポートに移動して、表示されたら選択します。

      デフォルトでは、一連の標準レポートが使用できます。また、お客様が選択できるカスタムレポートが組織で作成されている場合もあります。

   1. [!UICONTROL **プロジェクト**]／[!UICONTROL **保存**]&#x200B;を選択して、レポートを新しいプロジェクトとして保存します。

      レポートについて詳しくは、[Adobe Analytics ランディングページ](/help/analyze/landing.md)の「レポートタブのナビゲート」を参照してください。

+++

1. 次に、パネル、ビジュアライゼーションおよびコンポーネントをプロジェクトに追加する必要があります。まず、Analysis Workspace のプロジェクトにパネルを追加します。詳しくは、[プロジェクトへのパネルの追加](#add-panels-to-the-project)を参照してください。その後、任意のパネルにビジュアライゼーションを追加できます。最後に、任意のパネルまたはビジュアライゼーションにコンポーネントを追加できます。

## プロジェクトへのパネルの追加 {#panels}

[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)は、Analysis Workspace のあらゆるプロジェクトの基盤となります。パネルを使用して、プロジェクトのコンテンツ（ビジュアライゼーションとコンポーネント）を整理します。

Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。

パネルを追加するには、次の手順に従います。

1. 左側のパネルから&#x200B;[!UICONTROL **パネル**]&#x200B;アイコンを選択します。

   ![](assets/build-panels.png)

1. 追加するパネルを検索します。左側のパネルに表示されたら、プロジェクトにドラッグします。

1. パネルにビジュアライゼーションを追加します。詳しくは、[プロジェクトへのビジュアライゼーションの追加](#add-visualizations-to-the-project)を参照してください。

   または、パネルにコンポーネントを直接追加することもできます。詳しくは、[プロジェクトへのコンポーネントの追加](#add-components-to-the-project)を参照してください。

## プロジェクトへのビジュアライゼーションの追加

[ビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja)（フリーフォームテーブル、棒グラフ、折れ線グラフなど）を使用して、データを視覚的に活用できます。

>[!TIP]
>
>フリーフォームテーブルは、最も一般的なタイプのビジュアライゼーションで、インタラクティブなデータ分析の基盤となります。Analysis Workspace でフリーフォームテーブルを使用する方法について詳しくは、[フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)を参照してください。

ビジュアライゼーションを追加するには、次の手順に従います。

1. 左側のパネルで&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;アイコンを選択します。

   ![](assets/build-visualizations.png)

1. 追加するビジュアライゼーションを検索します。左側のパネルに表示されたら、プロジェクト内のパネルにドラッグします。

1. ビジュアライゼーションにコンポーネントを追加します。詳しくは、[プロジェクトへのコンポーネントの追加](#add-components-to-the-project)を参照してください。

## プロジェクトへのコンポーネントの追加

[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)は、プロジェクトの実際のデータを構成します。コンポーネントをビジュアライゼーションまたはパネルに追加できます。

>[!TIP]
>
>各コンポーネントについて詳しくは、左側のパネルでコンポーネントの名前の横にある情報アイコンを選択するか、[Analytics コンポーネントガイド](/help/components/home.md)を参照してください。

コンポーネントを追加するには、次の手順に従います。

1. 左側のパネルにある&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンを選択します。

   ![](assets/build-components.png)

1. 追加するコンポーネントを検索します。左側のパネルに表示されたら、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. （オプション）[プロジェクトの保存と共有](#save-and-share-the-project)の説明に従って、プロジェクトを共有します。

## プロジェクトの保存と共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できる準備が整います。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)を参照してください。
