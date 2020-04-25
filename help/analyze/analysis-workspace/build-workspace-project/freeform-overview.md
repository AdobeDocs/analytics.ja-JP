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

**[!UICONTROL Analytics]**／**[!UICONTROL Workspace]**

ビジュアライゼーション、レポートコンポーネントおよびデータテーブルを任意に組み合わせて、堅牢な Analytics プロジェクトを作成できます。Analytics で Ad Hoc Analysis の数多くのテーブル作成機能を使用できます。

Analysis Workspace では、新たな方法でデータの比較および詳細分析を実行できます。例えば、ランクレポートを設定して、すぐにデータクエリを繰り返し変更した後、レポート作成レベルで値にアクセスして操作することができます。

クエリは、直接レポーティングエンジンに渡されます。分析を作成するために他のレポートを表示することなく、インラインで変更できます。結果は即座に返され、ブラウザーを更新する必要もありません。

## Workspace のプロジェクト一覧ページ {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. （下のスクリーンショットのように、このオプションが表示されない場合、既にランディングページに設定されています）。

![](assets/sample-project.png)

Workspace のプロジェクト一覧ページには、次の情報が表示されます。

| 要素 | 説明 |
|---|---|
| プロジェクト[テンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | これらの事前設定されたプロジェクトテンプレートをそのまま、またはニーズに応じて変更して（例えば指標やビジュアライゼーションを追加または置き換えることで）使用して、新しい名前で保存できます。 |
| [新規プロジェクトを作成](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | このリンクをクリックすると、新しいプロジェクトを最初から作成できます。 |
| プロジェクトの管理 | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| チュートリアルを表示 | [YouTube の Analysis Workspace 関連ビデオ](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)に移動します。 |
| 名前 | Workspace プロジェクトの名前。 |
| 作成者 | このプロジェクトを作成したユーザー（ユーザー自身、またはユーザー自身とそのプロジェクトを共有した他のユーザー）。 |
| タグ | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| 最終変更日 | プロジェクトが最後に変更された日付。 |

## プロジェクト情報および設定 {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]**／**[!UICONTROL Project]**／**[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** 現在アクティブなプロジェクトに関するプロジェクトレベルの情報を提供します。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに設定された名前。名前をダブルクリックすると編集できます。 |
| 作成者 | プロジェクト所有者名。 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | 分類を簡単にするためにプロジェクトに適用されたタグのリスト。プロジェクトは保存する際にもタグ付けできます。View a project&#39;s tags on the Workspace Landing Page in the [!UICONTROL Tags] column. |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。説明をダブルクリックすると編集できます。 |
| プロジェクトで繰り返しのインスタンスをカウントします | レポート内でレポートインスタンスがカウントされるかどうかを指定します。同じ変数に対して複数の連続する値が存在する場合に、それらの値を変数の 1 つのインスタンスとしてカウントすることも、複数のインスタンスとしてカウントすることもできます。 |
| ビジュアライゼーションのカラースキーマ | 異なるカラーパレットを選択するか、独自のパレットを指定することにより、Workspace で使用されるカラースキーマを変更できるようになりました。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| 表示密度 | 左側のパネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |

## プロジェクトメニュー {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

トッププロジェクトメニューは、次のように表示されます。

![](assets/new-project-menus.png)

サブメニューには次のオプションが含まれます。

>[!NOTE]アスタリスク（*）が付いているオプションは、**保存済みプロジェクト**&#x200B;でのみ表示されます。

| プロジェクト | 編集 | 挿入 | コンポーネント | 共有 | ヘルプ |
|---|---|---|---|---|---|
| 新規 | 元に戻す | 新しいパネル | 新しいセグメント | プロジェクトを共有 | ビデオ |
| Open | クリア | 新しいフリーフォームパネル | 新しい指標 | プロジェクトリンクを取得* | ホットキー |
| 保存 | すべてクリア | 新しいセグメント比較パネル | 新しい日付範囲 | ファイルを今すぐ送信* | ヘルプフォーラム |
| 名前を付けて保存* |  | 新しいフリーフォームテーブル | 新しいアラート | ファイルをスケジュールに従って送信* |  |
| ランディングページとして設定* |  | 改行 | コンポーネントを更新 | プロジェクトデータをキュレート |  |
| プロジェクトを更新 |  | 新しいバー |  |  |  |
| CSV をダウンロード |  |  |  |  |  |
| PDF をダウンロード* |  |  |  |  |  |
| プロジェクト情報および設定 |  |  |  |  |  |

## 左側のパネル {#section_271295C26EC840ABB2A8E7EC0498B60E}

左側のパネルに、パネル、[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)および[コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)（ディメンション、指標、セグメント、データ範囲）に 1 クリックでアクセスできる 3 つのアイコンがあります。

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. **新しいコホートパネル**&#x200B;を作成するには、空のパネルにドラッグし、コホートテーブルのビジュアライゼーションにドラッグします。
