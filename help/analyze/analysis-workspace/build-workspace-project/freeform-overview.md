---
description: 'null'
keywords: Analysis Workspace
title: プロジェクトの作成 - 概要
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# プロジェクトの作成 - 概要

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

ビジュアライゼーション、レポートコンポーネントおよびデータテーブルの任意の組み合わせに基づいて、堅牢なAnalyticsプロジェクトを作成できます。 Ad Hoc分析の多くの表ビルダー機能をAnalyticsに導入します。

分析ワークスペースでは、以前は不可能だった方法でデータを比較および分析できます。 例えば、ランクレポートを設定して、すぐにデータクエリを繰り返し変更した後、レポート作成レベルで値にアクセスして操作することができます。

クエリはレポートエンジンに直接移動します。他のレポートを表示せずにインラインで変更を行い、分析を作成できます。 結果は即座に返され、ブラウザーの更新は行われません。

## Workspaceプロジェクトリストページ {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (下のスクリーンショットのように、このオプションが表示されない場合は、既にランディングページです)。

![](assets/sample-project.png)

Workspaceプロジェクトのリストページには、次の情報が含まれます。

| 要素 | 説明 |
|---|---|
| プロジェクトテン [プレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | これらの事前入力されたプロジェクトテンプレートは、そのまま使用したり、ニーズに合わせて（例えば、指標やビジュアライゼーションを追加または置き換えて）使用したり、新しい名前で保存したりできます。 |
| [新規プロジェクトを作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | 新しいプロジェクトを新規開始するには、このリンクをクリックします。 |
| プロジェクト管理 | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| 表示チュートリアル | YouTubeビデオの [分析ワークスペースに移動します](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)。 |
| 名前 | Workspaceプロジェクトの名前。 |
| 作成者 | このプロジェクトを作成した人（自分または自分とプロジェクトを共有した人）。 |
| タグ | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| 最終変更日 | プロジェクトが最後に変更された日時。 |

## プロジェクト情報および設定 {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]**／**[!UICONTROL Project]**／**[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** 現在アクティブなプロジェクトに関するプロジェクトレベルの情報を提供します。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに与えられた名前。 名前を重複クリックして編集できます。 |
| 作成者 | プロジェクト所有者名 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | リスト化を容易にするために、プロジェクトに適用された任意のタグ。 保存時にプロジェクトにタグを付けることもできます。 表示列のWorkspaceランディングページ上のプロジェクトのタグ [!UICONTROL Tags] 。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。 説明を重複クリックして編集できます。 |
| プロジェクト内の繰り返しインスタンスをカウント | 繰り返しインスタンスをレポートでカウントするかどうかを指定します。同じ変数に対して複数の連続する値がある場合は、それらを1つの変数として、または複数の変数のインスタンスとしてカウントできます。 |
| ビジュアライゼーションのカラースキーム | 異なるカラーパレットを選択するか、独自のパレットを指定することにより、Workspace で使用されるカラースキーマを変更できるようになりました。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| 表示密度 | 左側のパネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |

## プロジェクトメニュー {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

トップのプロジェクトメニューは次のようになります。

![](assets/new-project-menus.png)

サブメニューには次のオプションが含まれます。

>[!NOTE]アスタリスク（*）が付いているオプションは、**保存済みプロジェクト**&#x200B;でのみ表示されます。

| プロジェクト | 編集 | 挿入 | コンポーネント | 共有 | ヘルプ |
|---|---|---|---|---|---|
| 新規 | 元に戻す | 新しいパネル | 新規セグメント | プロジェクトを共有 | ビデオ |
| Open | クリア | 新しいフリーフォームパネル | 新しい指標 | プロジェクトリンクの取得* | ホットキー |
| 保存 | すべてクリア | 新しいセグメント比較パネル | 新しい日付範囲 | ファイルを今すぐ送信* | ヘルプフォーラム |
| 名前を付けて保存* |  | 新しいフリーフォームテーブル | 新しいアラート | ファイルをスケジュールに従って送信* |  |
| ランディングページとして設定* |  | 改行 | コンポーネントの更新 | プロジェクトデータをキュレート |  |
| プロジェクトの更新 |  | 新しいバー |  |  |  |
| CSVのダウンロード |  |  |  |  |  |
| PDF のダウンロード* |  |  |  |  |  |
| プロジェクト情報および設定 |  |  |  |  |  |

## 左側のパネル {#section_271295C26EC840ABB2A8E7EC0498B60E}

左側のパネルに、パネル、[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)および[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)（ディメンション、指標、セグメント、データ範囲）に 1 クリックでアクセスできる 3 つのアイコンがあります。

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. **新しいコホートパネル**&#x200B;を作成するには、空のパネルにドラッグし、コホートテーブルのビジュアライゼーションにドラッグします。
