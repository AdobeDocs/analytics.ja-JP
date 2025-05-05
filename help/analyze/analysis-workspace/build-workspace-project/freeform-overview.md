---
description: Workspace プロジェクトでの作業の基本について説明します。
keywords: Analysis Workspace
title: プロジェクトの概要
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 43%

---

# プロジェクトの概要

Workspace プロジェクトでは、データコンポーネント、テーブル、およびビジュアライゼーションを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。最初のプロジェクトを開始する前に、プロジェクトへのアクセス方法、プロジェクト間の移動方法、およびプロジェクトの管理方法について説明します。

以下は、Workspace プロジェクトの構築方法に関するビデオです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Workspace プロジェクトの構築 ](https://video.tv.adobe.com/v/3416041?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## プロジェクトリスト {#project-list}

最初に **[!UICONTROL Analytics]**／**[!UICONTROL Workspace]** に移動すると、自分が所有するプロジェクトまたは自分と共有されているプロジェクトがすべて一覧表示されます。事前にランディングページをカスタム設定してある場合を除き、このページもAdobe Analyticsのランディングページになります。

プロジェクト ページには、次の情報が含まれます。

| 要素 | 説明 |
|---|---|
| [ 環境設定を編集 ](/help/analyze/analysis-workspace/user-preferences.md) | 作成するすべての新規プロジェクトまたはパネルについて、Analysis Workspaceおよびその関連コンポーネントの設定を管理します。 |
| [ フォルダーを作成 ](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | プロジェクトとフォルダーのリストに新しいフォルダーまたはサブフォルダーを追加します。 |
| [プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | ゼロから、またはレポートから新しいプロジェクトを開始します。 |
| さらに表示 | この選択により、空のプロジェクトまたはモバイルスコアカードの作成、[ トレーニングチュートリアルの表示 ](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction) または [ リリースノートの表示 ](/help/release-notes/latest.md) のオプションが表示されます。 |
| ![ フィルターを表示 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | フィルターを表示または非表示にするには： タグ、レポートスイート、所有者、タイプ（プロジェクト、フォルダー、モバイルスコアカード）およびその他のフィルターでフィルタリングできます。 |
| ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | 検索フィールドを使用して、フォルダー、Workspace プロジェクト、モバイルスコアカードを検索します。 |
| フォルダーとプロジェクトを表示 | プロジェクトのフォルダー構造を表示するかどうかを選択します。 詳しくは、[Analytics のフォルダーについて](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)を参照してください。 |
| ![ テーブルをカスタマイズ ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | このアイコンを使用すると、プロジェクトリストにプロジェクトごとに表示される列をカスタマイズできます。 |

プロジェクトのリストには、次の列が表示されます。

| 列 | 説明 |
|---|---|
| [!UICONTROL 名前] | Workspace プロジェクトの名前。 「![ 情報 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」を選択すると、プロジェクトまたはフォルダーの詳細を示すポップアップが表示されます。 ![ 詳細 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) を選択して、使用可能なアクションを表示します。 詳しくは、[ プロジェクトの管理 ](#manage-projects) を参照してください。 |
| [!UICONTROL タイプ] | このエントリがWorkspace プロジェクト、フォルダーまたは [ モバイルスコアカード ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/mobapp/home) のいずれであるかを示します。 |
| [!UICONTROL タグ] | プロジェクトに適用されたタグです。 |
| [!UICONTROL スケジュール済み] | プロジェクトが受信者にメールで送信されるようにスケジュールされているかどうかを示します。 [ プロジェクトのスケジュール ](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) を参照してください。 |
| 共有リンク (任意のユーザー) | プロジェクトは、Analysis Workspaceへのアクセス権を持たないユーザーでも任意のユーザーと共有できます。 この列には、プロジェクトがこのようにして共有されたかどうかが表示されます。 詳しくは、[ プロジェクトを共有 ](/help/analyze/analysis-workspace/curate-share/share-projects.md) の「プロジェクトを任意のユーザーと共有する [ ログインは不要） ](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) を参照してください。 |
| [プロジェクトの役割](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/curate-share/share-projects) | プロジェクトの役割（所有者、編集、重複、表示）を示します。 |
| [!UICONTROL レポートスイート] | プロジェクトが関連付けられているレポートスイート。 |
| [!UICONTROL 所有者] | このプロジェクトを作成したユーザー（ユーザー自身、またはユーザー自身とそのプロジェクトを共有した他のユーザー）。 |
| [!UICONTROL 共有先] | プロジェクトが共有されているユーザー。 |
| [!UICONTROL 最終変更日時] | プロジェクトが最後に変更された日付。 |
| [!UICONTROL 前回開いた日時] | プロジェクトが最後に開かれた日時。 |
| [!UICONTROL 前回の使用] | プロジェクトが最後に使用された日時。 |
| [!UICONTROL プロジェクト ID] | プロジェクトの ID。 |
| [!UICONTROL 最長の日付範囲] | プロジェクトの最長の日付範囲。 |
| [!UICONTROL クエリ数] | プロジェクトに含まれるクエリの合計数。 |
| [!UICONTROL 場所] | プロジェクトが存在するフォルダー。 |

### プロジェクトの管理

プロジェクトを管理するには、プロジェクトリストから 1 つ以上のプロジェクトを選択します。

青いアクションバーから、次のアクションを選択できます。

| アクション | 説明 |
|---|---|
| ![ 削除 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) 削除 | 選択すると、Workspace プロジェクトまたはモバイルスコアカードが削除されたことを確認するダイアログが表示されます。 「**[!UICONTROL OK]**」を選択して確定します。 |
| ![ 共有 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) 共有 | このアクションを使用すると、プロジェクトを共有できます。 詳しくは、[ プロジェクトを共有 ](../curate-share/share-projects.md) を参照してください。 |
| ![ 名前変更 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) 名前変更 | プロジェクトの名前を変更するための **[!UICONTROL 名前の変更：*名前&#x200B;*]**&#x200B;ダイアログが開きます。 「**[!UICONTROL 保存&#x200B;]**」を選択して、プロジェクトの新しい名前を保存します。 |
| ![ コピー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) コピー | 選択したプロジェクトを *元の名前* という名前の新しいプロジェクトに直ちにコピーします（コピー）。 |
| ![ ピン留め ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) ピン | プロジェクトを直ちにリストの先頭にピン留めします。 ![ ピン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) インジケーターを追加します。 |
| ![Tag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) Tag | **[!UICONTROL プロジェクトをタグ付け]** ダイアログを開きます。 既存のタグを選択することも、新しいタグを追加することもできます。 「**[!UICONTROL 保存]**」を選択して、プロジェクトのタグを保存します。 |
| 承認 ![ 承認 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) 承認または未承認 | プロジェクトを承認または未承認します。 |
| ![CSV を書き出し ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg)CSV を書き出し | コンマ区切りのプロジェクトリストを含むファイルをすぐにダウンロードします。 |
| ![ 移動先 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) 移動先 | このアクションを使用すると、プロジェクトをフォルダーに移動できます。 **[!UICONTROL フォルダーを選択]** ダイアログで、「**[!UICONTROL フォルダー]** リストからフォルダーを選択し、「**[!UICONTROL 移動]**」を選択します。 |


## メニューバー {#menu-bar}

プロジェクト内のメニューには、プロジェクトの管理、コンポーネントの追加、ヘルプの検索などを行うためのオプションが表示されます。また、キーボード [ ショートカット ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys) を使用して各メニューオプションにアクセスすることもできます。


| メニュー項目 | 説明 |
|---|---|
| プロジェクト | このメニューには、新規、開く、保存、名前を付けて保存、「会社レポートとして保存 [ など、プロジェクト管理の一般的なアクションが含まれ ](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) す。 また、「プロジェクトを更新」をクリックして、プロジェクト全体を更新し、最新のデータと定義を取得することもできます。「[CSV と PDF をダウンロード](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/curate-share/download-send)」オプションを使用すると、Workspace からデータをエクスポートできます。「[プロジェクト情報および設定](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview)」には、プロジェクトを管理するための多くのオプションが用意されています。 |
| テンプレートを | 前回の操作を元に戻すか、やり直します。すべてクリア プロジェクトを空白の開始点にリセットします。 |
| 前に | このメニューから、新しいパネルまたはビジュアライゼーションを挿入します。また、左側のパネルから新しいパネルやビジュアライゼーションを挿入することもできます。 |
| [コンポーネント](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) | プロジェクトから、新しいセグメント、計算指標、日付範囲またはアラートの各コンポーネントを作成します。また、左側のパネルから新しいコンポーネントを作成することもできます。コンポーネント定義が最近変更された場合、「コンポーネントを更新」は最新の定義を取得します。 |
| [共有](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files) | 組織の受信者に対して PDF／CSV プロジェクトのキュレーション、共有およびスケジュール設定を行います。 |
| ヘルプ | ヘルプドキュメント、ビデオおよび Analytics [Experience League コミュニティ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja)にアクセスします。Workspace のヒントの表示と[デバッガー](https://developer.adobe.com/analytics-apis/docs/2.0/)の表示を管理します。Workspace の詳細と、プロジェクトの[パフォーマンス](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance)に影響を与える要因を確認します。 |
| 「共有」ボタンまたは「所有者」 | プロジェクトを所有または編集している場合は、右上の「共有」ボタンからワンクリックでアクセスして、プロジェクト受信者を管理できます。プロジェクトの重複または表示の役割を担っている場合は、プロジェクト所有者の名前が表示されます。 |

### プロジェクト情報および設定 {#info-settings}

**[!UICONTROL Workspace]**/**[!UICONTROL プロジェクト]**/**[!UICONTROL プロジェクト情報および設定]** では、現在アクティブなプロジェクトに関するプロジェクトレベルの情報が提供されます。

![ プロジェクト情報 ](assets/projectinfo.png)

「設定」には次の項目が含まれます。

| 設定 | 説明 |
|---|---|
| プロジェクト名 | プロジェクトに設定された名前。名前をダブルクリックすると編集できます。 |
| 所有者 | プロジェクト所有者名 |
| 最終変更日 | プロジェクトの最終変更日。 |
| タグ | 分類を簡単にするためにプロジェクトに適用されたタグのリスト。 |
| 説明 | 説明は、プロジェクトの目的を明確にするのに役立ちます。説明をダブルクリックすると編集できます。 |
| 繰り返しインスタンスをカウント | レポート内でレポートインスタンスがカウントされるかどうかを指定します。例えば、この設定（有効にした場合）は、複数の連続するページビューを複数のページビューと同じページに対して処理します。オフにすると、単一ページビューとしてカウントされます（この設定は、単一ページ訪問数などの特定の指標にのみ影響します）。 **メモ**：この設定は、フローまたはフォールアウトのビジュアライゼーションには適用されません。 |
| [注釈を表示](/help/analyze/analysis-workspace/components/annotations/overview.md) | 注釈をプロジェクトに表示するかどうかを指定します。 |
| [プロジェクトカラーパレット](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | Workspace で使用する分類カラーパレットを変更するには、色弱のユーザー向け用に最適化されている既定のパレットを選択するか、カスタムパレットを指定します。この機能は、ほとんどのビジュアライゼーションを含む Workspace の多くの機能に影響します。 |
| [表示密度](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | 左側のパネル、フリーフォームテーブル、コホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。 |

## 左側のパネル {#left-rail}

プロジェクト内の左側のパネルには様々なアイコンが表示され、それぞれがプロジェクトを構築するための重要なツールを表しています。

| アイコン | 機能 |
|---|---|
| ![ パネルアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [パネル](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![ ビジュアライゼーションアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) | [ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![ コンポーネントアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![ データ要素アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![ 目次アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [目次](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

左側のパネルのコンポーネント（ディメンション、指標、セグメント、日付範囲）は、アクティブなパネルデータビューに関連しています。 アクティブなパネルは青い境界線で示され、アクティブなレポートスイートはコンポーネントパネルの上部にリストされます。


## 右クリックメニュー

以下は、Analysis Workspace での右クリックメニューの使用に関するビデオです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ コンテキストメニューの使用 ](https://video.tv.adobe.com/v/327456?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

## プロジェクトキャンバス {#canvas}

プロジェクトキャンバスでは、パネル、テーブル、ビジュアライゼーションおよびコンポーネントをまとめ、分析を作成できます。プロジェクトには多数のパネルを含めることができます。また、各パネルには多数のテーブルやビジュアライゼーションを含めることができます。

パネルは、期間、レポートスイートまたは分析のユースケースに従ってプロジェクトを整理する場合に役立ちます。アクティブパネルの周囲に色付きの境界線があり、左パネルで使用できるコンポーネントを決定します。

プロジェクトの開始点を選択した内容に応じて、キャンバスに [ フリーフォームテーブル ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) または [ 空白のパネル ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/panels/blank-panel) が最初に表示されます。 分析を最も簡単に開始するには、1 つまたは複数のコンポーネントを選択し、それらをプロジェクトキャンバスにドラッグ＆ドロップします。データのテーブルは自動的にレンダリングされます。 テーブルを作成するための様々なオプションについて [ 詳細 ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) を参照するか、利用可能な [ トレーニングチュートリアル ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/home) を活用して、最初のプロジェクトを作成する際の詳細なガイダンスを確認します。

![](assets/canvas.png)
