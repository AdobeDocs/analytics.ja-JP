---
title: Analysis Workspace の概要
description: Adobe Analytics の主要な分析ツールである Analysis Workspace について説明します。プロジェクト、パネル、テーブル、ビジュアライゼーション、その他のコンポーネントを使用して、データを活用し、分析をキュレートして共有します。
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 100%

---

# Analysis Workspace の概要 {#analysis-workspace-overview}

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとの[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)の共有とスケジュールを行うことができます。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace の概要](https://video.tv.adobe.com/v/35774/?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## インターフェイス

次の画像と付属の表では、Analysis Workspace ユーザーインターフェイスの主な要素を説明します。

![インターフェイスの様々なセクションがハイライト表示された、Analysis Workspace ウィンドウ](assets/analysis-workspace-overview.png)

| 場所 | 名前と機能 |
|:---------:|----------|
| A | プロジェクトの名前、機能にアクセスするメニュー構造、プロジェクトリストに戻る「![戻るボタン](/help/assets/icons/ChevronLeft.svg)」、[Workspace プロジェクトを共有する](/help/analyze/analysis-workspace/curate-share/share-projects.md)「**[!UICONTROL 共有]**」ボタンが含まれています。<br/>いつでもプロジェクトの名前（新規プロジェクトなど）を選択して、名前を変更します。<br/>「![お気に入りから外す](/help/assets/icons/StarOutline.svg)」を選択して、プロジェクトをお気に入りのプロジェクト「![お気に入りに追加](/help/assets/icons/Star.svg)」として登録します。 |
| B | **ボタンパネル：** Analysis Workspace の主要な[機能](#features)にアクセスするボタンが含まれています。<ul><li>![Web ページ](/help/assets/icons/WebPage.svg) [[!UICONTROL パネル]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL ビジュアライゼーション]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>[[!UICONTROL コンポーネント]](/help/components/home.md)を![キュレーション](/help/assets/icons/Curate.svg)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL 目次]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![ブックマーク](/help/assets/icons/Bookmark.svg) [[!UICONTROL データ辞書]](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **左パネル：**&#x200B;この領域には、個々のパネル、ビジュアライゼーション、コンポーネントまたはリストが含まれます。コンテンツは、ボタンパネルで選択したボタンによって異なります。 |
| D | **キャンバス：**&#x200B;これは、左パネルからコンテンツをドラッグしてプロジェクトを作成する主な領域です。パネルの追加、パネルへのビジュアライゼーションの追加、ビジュアライゼーションへのコンポーネントの追加を行うと、プロジェクトは動的に更新されます。複数のパネルを作成でき、各パネル内で複数のビジュアライゼーションを作成できます。<br/>各パネルは、選択したレポートスイートに基づいています。選択したレポートスイートによって、指標やディメンションなど、使用可能なコンポーネントが決まります。詳しくは、[パネル - レポートスイート](/help/analyze/analysis-workspace/c-panels/panels.md#report-suite)を参照してください。 |

## 機能

Analysis Workspace の主な機能は、ボタンパネルから使用できます。

| アイコン | 機能 | 説明 |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL パネル]** | [パネル](/help/analyze/analysis-workspace/c-panels/panels.md)を使用すると、プロジェクト内の分析を整理し、多数のテーブルやビジュアライゼーションを含めることができます。Analysis Workspace で提供される多くのパネルは、少数のユーザー入力に基づいてフルセットの分析を生成します。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL ビジュアライゼーション]** | 棒グラフや折れ線グラフなどの[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)を使用して、データを視覚的に表示できます。左端のパネルで、中央の&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;アイコンを選択し、使用可能なビジュアライゼーションの完全なリストを表示します。 |
| ![キュレート](/help/assets/icons/Curate.svg) | **[!UICONTROL コンポーネント]** | [コンポーネント](/help/components/home.md)には、次の要素が含まれます。<ul><li>![ディメンション](/help/assets/icons/Dimensions.svg)[ディメンション](/help/components/dimensions/overview.md)</li><li>![イベント](/help/assets/icons/Event.svg)[指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md)</li><li>![セグメント化](/help/assets/icons/Segmentation.svg)[セグメント](/help/components/segmentation/seg-overview.md)</li><li>![カレンダー](/help/assets/icons/Calendar.svg)[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目次]** | [目次](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)は、プロジェクトに含まれるすべてのパネルとビジュアライゼーションを折りたたみ可能なリストに整理するので、特定のパネルやビジュアライゼーションにすばやくアクセスできます。 |
| ![ブックマーク](/help/assets/icons/Bookmark.svg) | **データ辞書** | [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)は、ユーザーと管理者の両方にとって、Analytics 環境のコンポーネントを追跡したり、理解を深めたりするのに役立ちます。 |


## メニュー

Analysis Workspace のほとんどの機能は、ドラッグ＆ドロップのほか、パネル、ビジュアライゼーションおよびコンポーネント内のコンテキストメニューから利用できます。

Workspace メニューとショートカットまたはホットキーを使用して、機能を利用することもできます。ショートカットキーは、ブラウザーを実行しているオペレーティングシステムによって異なります。概要について詳しくは、以下の表を参照してください。

キーボードでは、次のシンボルが使用される場合があります。

- **[!UICONTROL *Shift キー&#x200B;*]**の代わりに**⇧**。
- **[!UICONTROL *cmd *]**（コマンド）の代わりに&#x200B;**⌘**。
- **[!UICONTROL *ctrl *]**（Control）の代わりに&#x200B;**⌃**。
- **[!UICONTROL *opt *]**（Option）の代わりに&#x200B;**⌥**。
- **[!UICONTROL *alt *]**（Alternate）の代わりに&#x200B;**⎇**。

利用できるメニューの概要について詳しくは、以下の表を参照してください。

| **[!UICONTROL プロジェクト]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL プロジェクトの作成]** | **[!UICONTROL *Shift + Cmd + P キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + P キー&#x200B;*]** | 新しいプロジェクトを作成します。 |
| **[!UICONTROL モバイルスコアカードの作成]** | | | [新しいモバイルスコアカードを作成します](/help/analyze/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 開いています...]** | **[!UICONTROL *Cmd + O キー&#x200B;*]** | **[!UICONTROL *Ctrl + O キー&#x200B;*]** | [既存のプロジェクトを開きます](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 以前のバージョンを開いています...]** | **[!UICONTROL *Opt + Cmd + O キー&#x200B;*]** | **[!UICONTROL *Alt + Ctrl + O キー&#x200B;*]** | [以前のバージョンのプロジェクトを開きます](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *Cmd + S キー&#x200B;*]** | **[!UICONTROL *Ctrl + S キー&#x200B;*]** | [プロジェクトを保存します](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects)。 |
| **[!UICONTROL メモと共に保存...]** | **[!UICONTROL *Opt + Cmd + S キー&#x200B;*]** | **[!UICONTROL *Alt + Ctrl + S キー&#x200B;*]** | [保存するプロジェクトバージョンにメモを追加します](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 名前を付けて保存...]** | **[!UICONTROL *Shift + Cmd + S キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + S キー&#x200B;*]** | [別の名前と詳細を使用してプロジェクトを保存します](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL プロジェクトを更新]** | **[!UICONTROL *Opt + R キー&#x200B;*]** | **[!UICONTROL *Alt + R キー&#x200B;*]** | プロジェクトを更新します。 |
| **[!UICONTROL CSV をダウンロード]** | **[!UICONTROL *Shift + Cmd + V キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + V キー&#x200B;*]** | プロジェクトを CSV ファイルとしてダウンロードします。 |
| **[!UICONTROL PDF をダウンロード]** | **[!UICONTROL *Shift + Cmd + B キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + B キー&#x200B;*]** | プロジェクトを PDF ドキュメントとしてダウンロードします。 |
| **[!UICONTROL プロジェクト情報および設定]** | | | 名前、タグ、カラーパレットなど、プロジェクトの設定を定義します。 |
| **[!UICONTROL ユーザー設定]** | | | [Analysis Workspace の使用に適した環境設定を行います](/help/analyze/analysis-workspace/user-preferences.md)。 |


| **[!UICONTROL 編集]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL 元に戻す]** | **[!UICONTROL *Cmd + Z キー&#x200B;*]** | **[!UICONTROL *Ctrl + Z キー&#x200B;*]** | 前のアクションを取り消します。 |
| **[!UICONTROL やり直し]** | **[!UICONTROL *Cmd + Shift + Z キー&#x200B;*]** | **[!UICONTROL *Ctrl + Shift + Z キー&#x200B;*]** | 前のアクションをやり直します。 |
| **[!UICONTROL すべてクリア]** | **[!UICONTROL *Opt + W キー&#x200B;*]** | **[!UICONTROL *Alt + W キー&#x200B;*]** | 現在のプロジェクトのすべてのパネルをクリアします。 |

| **[!UICONTROL 挿入]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL 空のパネル]** | **[!UICONTROL *Opt + B キー&#x200B;*]** | **[!UICONTROL *Alt + B キー&#x200B;*]** | [空のパネル](/help/analyze/analysis-workspace/c-panels/blank-panel.md)を挿入します。 |
| **[!UICONTROL メディア同時閲覧者数]** | **[!UICONTROL *Opt + H キー&#x200B;*]** | **[!UICONTROL *Alt + H キー&#x200B;*]** | [メディア同時視聴者](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md)パネルを挿入します。 |
| **[!UICONTROL メディア再生滞在時間]** | **[!UICONTROL *Opt + I キー&#x200B;*]** | **[!UICONTROL *Alt + I キー&#x200B;*]** | [メディア再生滞在時間](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)パネルを挿入します。 |
| **[!UICONTROL メディア分平均オーディエンス]** | **[!UICONTROL *Opt + M キー&#x200B;*]** | **[!UICONTROL *Alt + M キー&#x200B;*]** | [メディア分平均オーディエンス](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)パネルを挿入します。 |
| **[!UICONTROL アトリビューション]** | **[!UICONTROL *Opt + E キー&#x200B;*]** | **[!UICONTROL *Alt + E キー&#x200B;*]** | [アトリビューション](/help/analyze/analysis-workspace/c-panels/attribution.md)パネルを挿入します。 |
| **[!UICONTROL フリーフォーム]** | **[!UICONTROL *Opt + A キー&#x200B;*]** | **[!UICONTROL *Alt + A キー&#x200B;*]** | [フリーフォーム](/help/analyze/analysis-workspace/c-panels/freeform-panel.md)パネルを挿入します。 |
| **[!UICONTROL クイックインサイト]** | **[!UICONTROL *Opt + J キー&#x200B;*]** | **[!UICONTROL *Alt + J キー&#x200B;*]** | [クイックインサイト](/help/analyze/analysis-workspace/c-panels/quickinsight.md)パネルを挿入します。 |
| **[!UICONTROL フリーフォームテーブル]** | **[!UICONTROL *Opt + 1 キー&#x200B;*]** | **[!UICONTROL *Alt + 1 キー&#x200B;*]** | [フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 折れ線グラフ]** | **[!UICONTROL *Opt + 2 キー&#x200B;*]** | **[!UICONTROL *Alt + 2 キー&#x200B;*]** | [折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL 棒グラフ]** | **[!UICONTROL *Opt + 3 キー&#x200B;*]** | **[!UICONTROL *Alt + 3 キー&#x200B;*]** | [棒グラフ](/help/analyze/analysis-workspace/visualizations/bar.md)ビジュアライゼーションを挿入します。 |
| **[!UICONTROL コンボ]** | **[!UICONTROL *Opt + 4 キー&#x200B;*]** | **[!UICONTROL *Alt + 4 キー&#x200B;*]** | [コンボ](/help/analyze/analysis-workspace/visualizations/combo-charts.md)ビジュアライゼーションを挿入します。 |


| **[!UICONTROL コンポーネント]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL セグメントを作成…]** | **[!UICONTROL *Shift + Cmd + E キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + E キー&#x200B;*]** | 新しい[セグメント](/help/components/segmentation/segmentation-workflow/seg-create.md)を作成します。 |
| **[!UICONTROL 指標を作成…]** | **[!UICONTROL *Shift + Cmd + C キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + C キー&#x200B;*]** | 新しい[計算指標](/help/components/calculated-metrics/cm-overview.md)を作成します。 |
| **[!UICONTROL 日付範囲を作成...]** | **[!UICONTROL *Shift + Cmd + D キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + D キー&#x200B;*]** | 新しい[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)を作成します。 |
| **[!UICONTROL 注釈を作成…]** | **[!UICONTROL *Shift + Cmd + O キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + O キー&#x200B;*]** | 新しい[注釈](/help/analyze/analysis-workspace/components/annotations/overview.md)を作成します。 |
| **[!UICONTROL コンポーネントの更新]** | **[!UICONTROL *Opt + Shift + R キー&#x200B;*]** | **[!UICONTROL *Alt + Shift + R キー&#x200B;*]** | プロジェクトのコンポーネントを更新します。 |

| **[!UICONTROL 共有]** | ショートカット Mac | ショートカット Windows | 説明 |
|---|---|---|---|
| **[!UICONTROL Workspace ユーザーと共有]** | **[!UICONTROL *Cmd + H キー&#x200B;*]** | **[!UICONTROL *Ctrl + H キー&#x200B;*]** | [プロジェクトを他の Workspace ユーザーと共有します](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 任意のユーザーと共有]** | **[!UICONTROL *Opt + L キー&#x200B;*]** | **[!UICONTROL *Alt + L キー&#x200B;*]** | [プロジェクトの読み取り専用バージョンを任意のユーザーと共有します](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project)。 |
| **[!UICONTROL ファイルを送信]** | **[!UICONTROL Opt + S キー]** | **[!UICONTROL *Alt + S キー&#x200B;*]** | [プロジェクトを CSV または PDF ファイルとして他の受信者に送信します](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL ファイルの書き出しをスケジュール]** | **[!UICONTROL *Shift + Opt + S キー&#x200B;*]** | **[!UICONTROL *Shift + Alt + S キー&#x200B;*]** | [スケジュールに従って、プロジェクトを CSV または PDF ファイルとして他の受信者に送信します](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL プロジェクトデータをキュレート]** | **[!UICONTROL *Shift + Cmd + G キー&#x200B;*]** | **[!UICONTROL *Shift + Ctrl + G キー&#x200B;*]** | [プロジェクトデータをキュレートします](/help/analyze/analysis-workspace/curate-share/curate.md)。 |

| ヘルプ | 説明 |
|---|---|
| **[!UICONTROL ビデオ]** | 新しいブラウザータブで、Customer Journey Analytics の YouTube チャネルを開きます。 |
| **[!UICONTROL ヘルプドキュメント]** | 新しいブラウザータブでドキュメントを開きます（実際には今読んでいるところです）。 |
| **[!UICONTROL ヘルプフォーラム]** | 新しいブラウザータブで、Adobe Analytics Experience League コミュニティフォーラムを開きます。 |
| **[!UICONTROL ホットキー]** | Workspace で使用できるホットキー（ショートカット）の概要を示します。 |
| **[!UICONTROL デバッガーの有効化]** | デバッガーを有効にします。プロジェクトが再読み込みされます。 |
| **[!UICONTROL デバッガーの無効化]** | デバッガーを無効にします。プロジェクトが再読み込みされます。 |
| **[!UICONTROL パフォーマンス]** | **[!UICONTROL Analysis Workspace のパフォーマンス]**&#x200B;に関する指標を表示するダイアログを表示します。**[!UICONTROL CSV としてダウンロード]**&#x200B;を使用して、パフォーマンス指標の CSV ファイルをダウンロードします。 |
| **[!UICONTROL Workspace について]** | バージョン情報、機能アクセスレベル、アクティブな機能フラグを含む **[!UICONTROL Analysis Workspaceについて]**&#x200B;ダイアログを表示します。 |

## データソース

ビジュアライゼーションを同期することで、ビジュアライゼーションに対応するデータテーブルまたはデータソースを制御できます。詳しくは、[データソースの管理](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)を参照してください。

## Analysis Workspace の使用


Analysis Workspace の使用を開始するには：

1. [Adobe Experience Cloud](https://experience.adobe.com) にログインします。
1. インターフェイスの右上にあるアプリ切り替えボタン![アプリ](/help/assets/icons/Apps.svg)から「**[!UICONTROL Customer Journey Analytics]**」を選択します。
1. デフォルトでは、Analysis Workspace の&#x200B;**[!UICONTROL プロジェクト]**&#x200B;ページが表示されます。特定のプロジェクトが選択されている場合や、最近作業を行った場合は、そのプロジェクトがデフォルトで表示されます。

### プロジェクトの作成

Analysis Workspace での分析は、[プロジェクト](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)と呼ばれます。

[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)で説明したように、Analysis Workspace でプロジェクトを作成できます。

[Analysis Workspace のフォルダー](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)で説明したように、プロジェクトはフォルダーとサブフォルダーに整理できます。

### プロジェクトの保存および共有

Analysis Workspace で分析を作成すると、作業内容は[自動保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)されます。

プロジェクトの作成が完了し、実用的なインサイトを収集すると、そのプロジェクトを他のユーザーが使用できます。プロジェクトは、組織内のユーザーやグループだけでなく、組織外の人物と共有することもできます。プロジェクトの共有について詳しくは、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)を参照してください。

## その他のリソース {#resources}

- アドビでは、数百もの[Analytics ビデオトレーニングチュートリアル](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/overview)を提供しています。
- 新機能の最新情報については、 [Adobe Experience Cloud リリースノート](https://experienceleague.adobe.com/ja/docs/release-notes/experience-cloud/current) を参照してください。



<!--
# Analysis Workspace overview {#analysis-workspace-overview}

Analysis Workspace allows you to build analyses quickly to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule [projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) with anyone you choose.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis workspace overview](https://video.tv.adobe.com/v/35774/?captions=jpn&quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Interface

The following image and accompanying table explain the main elements in the Analysis Workspace user interface:

![Analysis Workspace window highlighting the various sections of the interface](assets/analysis-workspace-overview.png)

| Location | Name and function |
|:---------:|----------|
| A | Contains the name of the project, a menu structure to access functionality, a button ![Back button](/help/assets/icons/ChevronLeft.svg) to return back to your Project list, and a **[!UICONTROL Share]** button to [share your Workspace project](/help/analyze/analysis-workspace/curate-share/share-projects.md). <br/>Select the name of your project (for example: New project) at any time to change the name. <br/>Select ![Unfavor](/help/assets/icons/StarOutline.svg) to mark your project as a favorite project ![Favor](/help/assets/icons/Star.svg). |
| B | **Button panel:** Contains buttons for accessing the key [features](#features) of Analysis Workspace:<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL Panels]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL Guided Analysis]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizations]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Curate](/help/assets/icons/Curate.svg) [[!UICONTROL Components]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Table of contents]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Bookmark](/help/assets/icons/Bookmark.svg) [[!UICONTROL Data Dictionary]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Left panel:** This area contains individual panels, visualizations, components, or lists. The content depends on the button selected in the button panel.  |
| D | **Canvas:** The main area where you drag content from the left panel to build your project. The project dynamically updates as you add panels, add visualizations to panels, and add components to visualizations. You can create multiple panels, and within each panel you can create multiple visualizations.<br/>Each panel is based on a selected data view. The selected data view determines available components like metrics and dimensions. See [Panels - Data view](/help/analyze/analysis-workspace/c-panels/panels.md#data-view) for more information. |

## Features

The key features of Analysis Workspace are available through the button panel:

| Icon | Feature | Description |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Panels]** | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. |
| ![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL Guided Analysis]** | [Guided analysis](../guided-analysis/overview.md) allows you to self-serve high quality data and insights about the customer journey through guided workflows. You can create an analysis for inclusion in your Workspace project, or include an existing analysis previously saved. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizations]** | [Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md), such as a bar or line chart, can be used to bring data visually to life. On the far left panel, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. |
| ![Curate](/help/assets/icons/Curate.svg) | **[!UICONTROL Components]** | [Components](/help/components/overview.md) include the following elements:<ul><li>![Dimensions](/help/assets/icons/Dimensions.svg) [Dimensions](/help/components/dimensions/overview.md)</li><li>![Event](/help/assets/icons/Event.svg) [Metrics](/help/components/apply-create-metrics.md)</li><li>![Segmentation](/help/assets/icons/Segmentation.svg) [Segments](/help/components/segments/seg-overview.md)</li><li>![Calendar](/help/assets/icons/Calendar.svg) [Date ranges](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Table of contents]** | The table of contents organizes all panels and visualizations included in the project into a collapsible list, allowing you to access a specific panel or visualization quickly. |
|![Bookmark](/help/assets/icons/Bookmark.svg) | **Data dictionary** | The [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md) helps both users and administrators keep track of and better understand the components in their Analytics environment. |


## Menu

Most of the functionality of Analysis Workspace is available through drag and drop, and trough context menus within panels, visualizations and components.

Functionality is also available through the Workspace menu and shortcuts or hotkeys. Shortcut keys differ depending on the operating system that your browser is running on. See the tables below for an overview.  

Note that on your keyboard the following symbols might be used:

- **⇧** for **[!UICONTROL *shift*]**.
- **⌘** for **[!UICONTROL *cmd*]** (command).
- **⌃** for **[!UICONTROL *ctrl*]** (control).
- **⌥** for **[!UICONTROL *opt*]** (option).
- **⎇** for **[!UICONTROL *alt*]** (alternate).

See the tables below for an overview of the available menus.  

| **[!UICONTROL Project]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create project]** | **[!UICONTROL *shift+cmd+p*]** | **[!UICONTROL *shift+ctrl+p*]** | Create a new project. |
| **[!UICONTROL Create a mobile scorecard]** | | | [Create a new mobile scorecard](/help/mobile-app/create-scorecard.md). |
| **[!UICONTROL Open...]** | **[!UICONTROL *cmd+o*]** | **[!UICONTROL *ctrl+o*]** | [Open an existing project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Open previous version...]** | **[!UICONTROL *opt+cmd+o*]** | **[!UICONTROL *alt+ctrl+o*]** | [Open earlier versions of your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Save]** | **[!UICONTROL *cmd+s*]** | **[!UICONTROL *ctrl+s*]** | [Save your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Save with notes...]** | **[!UICONTROL *opt+cmd+s*]** | **[!UICONTROL *alt+ctrl+s*]** | [Add notes to the project version that you save](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Save as...]** | **[!UICONTROL *shift+cmd+s*]** | **[!UICONTROL *shift+ctrl+s*]** | [Save the project using a different name and details](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Refresh project]** | **[!UICONTROL *opt+r*]** | **[!UICONTROL *alt+r*]** | Refresh the project. |
| **[!UICONTROL Download CSV]** | **[!UICONTROL *shift+cmd+v*]** | **[!UICONTROL *shift+ctrl+v*]** | Download the project as a CSV file. |
| **[!UICONTROL Download PDF]**| **[!UICONTROL *shift+cmd+b*]** | **[!UICONTROL *shift+ctrl+b*]** | Download the project as a PDF document. |
| **[!UICONTROL Project info & settings]** | | | Define settings for your projects, such as name, tags, color palette, and more. |
| **[!UICONTROL User settings]** | | | [Configure preferences for using Analysis Workspace](/help/analyze/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Edit]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Undo]** | **[!UICONTROL *cmd+z*]** | **[!UICONTROL *ctrl+z*]** | Undo the previous action. |
| **[!UICONTROL Redo]** | **[!UICONTROL *cmd+shift+z*]** | **[!UICONTROL *ctrl+shift+z*]** | Redo the previous action. |
| **[!UICONTROL Clear all]** | **[!UICONTROL *opt+w*]** | **[!UICONTROL *alt+w*]** | Clear all panels in the current project. |

| **[!UICONTROL Insert]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Blank panel]** | **[!UICONTROL *opt+b*]** | **[!UICONTROL *alt+b*]** |  Insert a [Blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Media concurrent viewers]** | **[!UICONTROL *opt+h*]** | **[!UICONTROL *alt-h*]** |  Insert a [Media concurrent viewers](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md) panel. |
| **[!UICONTROL Media playback time spent]** | **[!UICONTROL *opt+i*]** | **[!UICONTROL *alt+i*]** |  Insert a [Media playback time spent](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) panel. |
| **[!UICONTROL Media average minute audience]** | **[!UICONTROL *opt+m*]** | **[!UICONTROL *alt+m*]** |  Insert a [Media average minute audience](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) panel. |
| **[!UICONTROL Attribution]** | **[!UICONTROL *opt+e*]** | **[!UICONTROL *alt+e*]** |  Insert an [Attribution](/help/analyze/analysis-workspace/c-panels/attribution.md) panel. |
| **[!UICONTROL Freeform]** | **[!UICONTROL *opt+a*]** | **[!UICONTROL *alt+a*]** |  Insert a [Freeform](/help/analyze/analysis-workspace/c-panels/freeform-panel.md) panel. |
| **[!UICONTROL Quick insights]** | **[!UICONTROL *opt+j*]** | **[!UICONTROL *alt+j*]** |  Insert a [Quick insights](/help/analyze/analysis-workspace/c-panels/quickinsight.md) panel. |
| **[!UICONTROL Experimentation]** |**[!UICONTROL *opt+x*]** | **[!UICONTROL *alt+x*]** |  Insert an [Experimentation](/help/analyze/analysis-workspace/c-panels/experimentation.md) panel. |
| **[!UICONTROL Freeform table]** | **[!UICONTROL *opt+1*]** | **[!UICONTROL *alt+1*]**|  Insert a [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualization. |
| **[!UICONTROL Line]** | **[!UICONTROL *opt+2*]** | **[!UICONTROL *alt+2*]** |  Insert a [Line](/help/analyze/analysis-workspace/visualizations/line.md) visualization. |
| **[!UICONTROL Bar]** | **[!UICONTROL *opt+3*]** | **[!UICONTROL *alt+3*]** |  Insert a [Bar](/help/analyze/analysis-workspace/visualizations/bar.md) visualization. |
| **[!UICONTROL Combo]** | **[!UICONTROL *opt+4*]**| **[!UICONTROL *alt+4*]** |  Insert a [Combo](/help/analyze/analysis-workspace/visualizations/combo-charts.md) visualization. |


| **[!UICONTROL Components]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create segment...]** | **[!UICONTROL *shift+cmd+e*]** | **[!UICONTROL *shift+ctrl+e*]** | Create a new [segment](/help/components/segments/seg-create.md). |
| **[!UICONTROL Create metric...]** | **[!UICONTROL *shift+cmd+c*]** | **[!UICONTROL *shift+ctrl+c*]** | Create a new [calculated metric](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Create date range...]** | **[!UICONTROL *shift+cmd+d*]** | **[!UICONTROL *shift+ctrl+d*]** | Create a new [date range](/help/components/date-ranges/overview.md). |
| **[!UICONTROL Create annotation...]** | **[!UICONTROL *shift+cmd+o*]** | **[!UICONTROL *shift+ctrl+o*]** | Create a new [annotation](/help/components/annotations/overview.md). |
| **[!UICONTROL Create audience...]** | **[!UICONTROL *shift+cmd+u*]** | **[!UICONTROL *shift+ctrl+u*]** | Create a new [audience](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Refewsh components]** | **[!UICONTROL *opt+shift+r*]** | **[!UICONTROL *alt+shift+r*]** | Refresh the components in the project. |

| **[!UICONTROL Share]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Share with Workspace users]** | **[!UICONTROL *cmd+h*]** | **[!UICONTROL *ctrl+h*]** | [Share the project with other Workspace users](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Share with anyone]** | **[!UICONTROL *opt+l*]** | **[!UICONTROL *alt+l*]**| [Share a read-only version of the project with anyone](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Send file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s*]** | [Send the project as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Schedule file export]** | **[!UICONTROL *shift+opt+s*]** | **[!UICONTROL *shift+alt+s*]** | [Send the project on a schedule as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Curate project data]** | **[!UICONTROL *shift+cmd+g*]** | **[!UICONTROL *shift+ctrl+g*]** | [Curate the project data](/help/analyze/analysis-workspace/curate-share/curate.md). |

| Help | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Videos]** | | | Open the Customer Journey Analytics YouTube channel in a new browser tab. |
| **[!UICONTROL Help documentation]** | | | Open the documentation (you are actually reading just now...) in a new browser tab. |
| **[!UICONTROL Help forum]** | | | Open the Adobe Analytics Experience League communities forum in a new browser tab. |
| **[!UICONTROL Hotkeys]** | | | Show an overview of the hotkeys (shortcuts) you can use in Workspace. |
| **[!UICONTROL Enable debugger]** |  | | Enable the debugger. Your project will reload. |
| **[!UICONTROL Disable debugger]** | | | Disable the debugger. Your project will reload. |
| **[!UICONTROL Performance]** | | | Show a dialog displaying metrics on the **[!UICONTROL Analysis Workspace performance]**. Use **[!UICONTROL Download as CSV]** to download a CSV file of the performance metrics. |
| **[!UICONTROL About Workspace]** | | | Show an **[!UICONTROL About Analysis Workspace]** dialog with version information, feature access levels and active feature flags. |

## Data sources

You synchronize visualizations to control which data table or data source corresponds to a visualization. See [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) for more information.

## Use Analysis Workspace


To start using Analysis Workspace: 

1. Log in to [Adobe Experience Cloud](https://experience.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** from the app switcher ![App](/help/assets/icons/Apps.svg) at the top right of the interface.
1. The **[!UICONTROL Projects]** page of Analysis Workspace is shown by default. If a specific project has been selected for you or you have been working on recently, then that project is shown by default.

### Create a project

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md). 

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, others might want to consume the project. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

- The [Learning landing](/help/getting-started/landing.md#learning) page in Customer Journey Analytics. This page is  great way to become acquainted with Analysis Workspace. Especially the Learning Workspace Fundamental. This template walks you through common terminology and steps for building your first analysis in Workspace
- Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/overview).
- See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/ja/docs/release-notes/experience-cloud/current) for updates about new features.



<!--
# Analysis Workspace overview

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

The following video provides a brief overview with examples of what is possible.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace overview](https://video.tv.adobe.com/v/35774/?captions=jpn&quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Areas of Analysis Workspace

The following image and accompanying table explain some of the main areas in Analysis Workspace:

![Analysis Workspace overview](assets/analysis-workspace-overvew.png)

| Location in image | Name and function |
|---------|----------|
| A | **Far left rail:** Contains tabs for adding panels, visualizations, and components to Analysis Workspace. Also contains the Data Dictionary icon that is used to open the Data Dictionary. |
| B | **Left rail:** Depending on which tab is selected in the far left rail, this area contains individual panels, visualizations, or components. |
| C | **Canvas:** This is the main area where you drag content from the left rails to build your project. The project dynamically updates as you add panels, visualizations, and components to the canvas. |
| D | **Report suite drop-down menu:** For each panel in Analysis Workspace, the report suite drop-down menu allows you to choose the report suite that you want to use as your data source. |

## Features in Analysis Workspace {#analysis}

Following are some of the key features available in Analysis Workspace: 

### Panels

**Panels** are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. On the far left rail, select the top **[!UICONTROL Panels]** icon to see a full list of panels available.

To learn more about panels, see [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

![](assets/build-panels.png)

### Visualizations

**Visualizations**, such as a bar or line chart, can be used to visually bring data to life. On the far left rail, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. 

To learn more about visualizations, see [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

![](assets/build-visualizations.png)

### Components

Components in Analysis Workspace consist of the following:

* Dimensions

* Metrics

* Segments

* Date ranges

To learn more about each of these component types, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). 

Each of these component types can be added to a visualization (such as a Freeform table) to start answering your business questions. 

After you understand component terminology, you can drag components into visualizations (including Freeform tables) to [build your analysis](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

![](assets/build-components.png)

### Data Dictionary

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.

To learn more about the Data Dictionary, see [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

### Data Sources

Synchronizing visualizations lets you control which data table or data source corresponds to a visualization. Here is more information on how you can [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md).

## Start using Analysis Workspace

### Log in to Adobe Analytics {#login}

To start using Analysis Workspace, log in to Adobe Analytics by going to [experience.adobe.com/analytics](https://experience.adobe.com/analytics). The Projects page of Analysis Workspace is shown by default. If a specific project has been selected for you, that project is shown by default.

### Create a project {#new-project}

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).  

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

* Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=ja).
* See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja#analytics) for updates about new features.
* A great way to become acquainted with Analysis Workspace is through the Analysis Workspace Training Tutorial template. This template walks you through common terminology and steps for building your first analysis in Workspace. To begin the tutorial:
  1. On the [!UICONTROL **Workspace**] tab in Adobe Analytics, select **[!UICONTROL Learning]** on the left.
  1. Select **[!UICONTROL Open Tutorial]**.
     ![](assets/training-tutorial.png)

-->