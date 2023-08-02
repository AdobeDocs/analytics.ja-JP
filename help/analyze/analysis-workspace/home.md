---
title: Analysis Workspace の概要
description: Analysis Workspace は Adobe Analytics の主要な分析ツールです。パネル、テーブル、ビジュアライゼーション、その他のコンポーネントを使用して、データを有効に活用したり、データセットをキュレーションしたり、プロジェクトを他のユーザーとの間で共有およびスケジュールしたりできます。
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 100%

---

# Analysis Workspace の概要

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するためのビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとのプロジェクトの共有とスケジュールを行うことができます。

次のビデオでは、短い概要と可能な例を示します。

>[!VIDEO](https://video.tv.adobe.com/v/26266/?quality=12)

## Analysis Workspace の領域

次の画像と付属の表では、Analysis Workspace の主な領域の一部を説明します。

![Analysis Workspace の概要](assets/analysis-workspace-overvew.png)

| 画像内の場所 | 名前と機能 |
|---------|----------|
| A | **左端のパネル：** Analysis Workspace にパネル、ビジュアライゼーションおよびコンポーネントを追加するためのタブが含まれます。また、データ要素を開くために使用する「データ要素」アイコンも含まれます。 |
| B | **左パネル：**&#x200B;左端のパネルで選択したタブに応じて、この領域には個々のパネル、ビジュアライゼーションまたはコンポーネントが含まれます。 |
| C | **キャンバス：**&#x200B;これは、左パネルからコンテンツをドラッグしてプロジェクトを作成する主な領域です。パネル、ビジュアライゼーションおよびコンポーネントをキャンバスに追加すると、プロジェクトは動的に更新されます。 |
| D | **レポートスイートのドロップダウンメニュー：** Analysis Workspace の各パネルでは、レポートスイートのドロップダウンメニューを使用して、データソースとして使用するレポートスイートを選択できます。 |

## Analysis Workspace の機能 {#analysis}

Analysis Workspace で使用できる主な機能の一部を次に示します。

### パネル

**パネル** を使用すると、プロジェクト内の分析を整理し、多数のテーブルやビジュアライゼーションを含めることができます。Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。左端のパネルで上部の&#x200B;**[!UICONTROL パネル]**&#x200B;アイコンを選択し、使用可能な パネルの完全なリストを表示します。

パネルについて詳しくは、[パネルの概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)を参照してください。

![](assets/build-panels.png)

### ビジュアライゼーション

棒グラフや折れ線グラフなどの&#x200B;**ビジュアライゼーション**&#x200B;を使用して、データを視覚的に活用することができます。左端のパネルで、中央の&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;アイコンを選択し、使用可能なビジュアライゼーションの完全なリストを表示します。

ビジュアライゼーションについて詳しくは、[ビジュアライゼーションの概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja)を参照してください。

![](assets/build-visualizations.png)

### コンポーネント

Analysis Workspace のコンポーネントは、以下で構成されます。

* ディメンション

* 指標

* セグメント

* 日付範囲

これらの各コンポーネントタイプについて詳しくは、[コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)を参照してください。

これらの各コンポーネントタイプをビジュアライゼーション（フリーフォームテーブルなど）に追加して、ビジネスの質問への回答を開始できます。

コンポーネントの用語を理解したら、コンポーネントをビジュアライゼーション（フリーフォーム テーブルを含む）にドラッグして[分析を作成](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)できます。

![](assets/build-components.png)

### データ要素

Analysis Workspace のデータ要素は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。

データ要素について詳しくは、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)を参照してください。

### データソース

ビジュアライゼーションを同期することで、ビジュアライゼーションに対応するデータテーブルまたはデータソースを制御できます。データソースを管理する方法について詳しくは、[こちら](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)を参照してください。

## Analysis Workspace の使用を開始

### Adobe Analytics へのログイン {#login}

Analysis Workspace の使用を開始するには、[experience.adobe.com/analytics](https://experience.adobe.com/analytics) に移動して Adobe Analytics にログインします。デフォルトでは、Analysis Workspace のプロジェクトページが表示されます。特定のプロジェクトを選択している場合は、そのプロジェクトがデフォルトで表示されます。

### プロジェクトの作成 {#new-project}

Analysis Workspace での分析は、[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)と呼ばれます。

[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)で説明したように、Analysis Workspace でプロジェクトを作成できます。

[Analysis Workspace のフォルダー](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)で説明したように、プロジェクトはフォルダーとサブフォルダーに整理できます。

### プロジェクトの保存および共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できる準備が整います。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)を参照してください。

## その他のリソース {#resources}

* アドビでは、数百もの[Analytics ビデオトレーニングチュートリアル](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=ja)を提供しています。
* 新機能の最新情報については、 [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja#analytics) を参照してください。
* Analysis Workspace について詳しく知るには、Analysis Workspace トレーニングチュートリアルテンプレートを使用するのが最適な方法です。このテンプレートでは、Workspace で初めての分析を作成するための一般的な用語と手順について説明します。チュートリアルを開始するには：
   1. Adobe Analytics の「[!UICONTROL **Workspace**]」タブで、左側の「**[!UICONTROL 学習]**」を選択します。
   1. 「**[!UICONTROL チュートリアルを開く]**」を選択します。
      ![](assets/training-tutorial.png)

