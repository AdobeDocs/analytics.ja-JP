---
title: メディア再生滞在時間パネル
description: Analysis Workspaceのメディア再生滞在時間パネルを使用および解釈する方法を説明します。
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 90%

---

# メディア再生滞在時間パネル {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="メディア再生滞在時間"
>abstract="様々なレベルの精度でビデオ消費の推移を分析するためのパネルを作成し、分類して比較できます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="メディア再生滞在時間"
>abstract="ビデオ消費の推移を分析し、様々な精度を選択して、分類および比較します。<br/><br/>**精度**：同時視聴者数を表示する期間を選択します。<br/>**パネル概要数値（オプション）**：各行の日付または時間の詳細と共に概要の数値を表示するオプション。最大値は、ピーク時の再生に費やした時間の詳細を示します。最小値は、トラフの詳細を示します。合計には、再生に費やした合計時間の詳細が表示されます。<br/>**系列の分類（オプション）**：セグメント、ディメンション、ディメンション項目または日付範囲でビジュアライゼーションを分類できます。一度に 10 行まで表示できます。分類は 1 つのレベルに制限されます。<br/>**時間形式**：ビジュアライゼーションの時間形式を時間または分で表示するオプション。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** のメディア再生滞在時間パネルについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** バージョンについて詳しくは、[メディア再生滞在時間パネル](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)を参照してください。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>メディア分平均オーディエンスパネルは、Adobe Analytics for Streaming Media アドオンを購入したお客様のみが利用できます。
>
>詳しくは、アドビ担当営業または販売店か、アドビアカウントチームにお問い合わせください。
>

**[!UICONTROL メディア再生滞在時間]**&#x200B;パネルを使用すると、同時実行のピークの詳細と分類および比較機能を使用して、経時的に再生を分析できます。

Analysis Workspace では、再生滞在時間は、特定の時点でのメディアストリームの視聴時間です。これには、一時停止、バッファー、開始までの時間が含まれます。

Adobe Analytics for Streaming Media アドオンを購入したお客様は、再生滞在時間を分析して、コンテンツの質と閲覧者のエンゲージメントに関する貴重なinsightを得ることができます。 また、容量や規模のトラブルシューティングや計画を行う際にも役立ちます。

再生滞在時間は、次の点を理解するのに役立ちます。

* ピーク同時実行が発生した場所。

* 下降が発生した場所。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [メディア再生滞在時間パネル](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/media-analytics/measuring-media-analytics/media-playback-time-spent-panel){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## 使用

**[!UICONTROL メディア再生滞在時間]**&#x200B;パネルを使用するには：

1. **[!UICONTROL メディア再生滞在時間]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. Adobe Analytics for Streaming Media アドオンから設定されたコンポーネントを含むパネルのレポートスイートを選択していることを確認してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。


### パネル入力

次の入力設定を使用して、メディア再生滞在時間パネルを設定できます。

| 設定 | 説明 |
|---|---|
| パネルの日付範囲 | パネルの日付範囲のデフォルトは「今日」です。一度に 1 日または複数の月を表示するように編集できます。<br>この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
| 精度 | 精度のデフォルトは「分」です。<br>この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
| パネルの要約数値 | 再生滞在時間の日時の詳細を表示するには、概要番号を使用できます。最大値は、ピーク同時実行性の詳細を示します。最小値は、トラフの詳細を示します。 合計値は、選択範囲に費やした合計再生滞在時間を加算したものです。パネルのデフォルトでは、最大値のみが表示されますが、最小値、合計値、またはこれら 3 つの組み合わせを表示するように変更できます。<br>分類を使用している場合は、それぞれの概要番号が表示されます。 |
| シリーズの分類 | オプションとして、フィルター、ディメンション、ディメンション項目または日付範囲でビジュアライゼーションを分類できます。<p> - 一度に 10 行まで表示できます。分類は 1 つのレベルに制限されます。</p><p>- ディメンションをドラッグすると、選択したパネルの日付範囲に基づいて、上位のディメンション項目が自動的に選択されます。</p> - 日付範囲を比較するには、2 つ以上の日付範囲をシリーズ分類フィルターにドラッグします。 |
| 時刻の形式 | 再生滞在時間は、`Hours:Minutes:Seconds`（デフォルト）または `Minutes`（整数で表示され、四捨五入されます）で表示できます。 |
| 日付順の表示 | 少なくとも 2 つの日付範囲フィルターをシリーズ分類として配置した場合は、オーバーレイ（デフォルト）または順次を選択するオプションが表示されます。オーバーレイでは、共通の X 軸の開始を持つ線が並行して表示され、順次では、特定の X 軸の開始を持つ線が表示されます。データが上に並ぶ場合（例えば、フィルター 1 が午後 8:44 で終わり、フィルター 2 が午後 8:45 で始まる場合）、行が順に表示されます。 |


![メディア再生滞在時間のデフォルトビュー。](assets/mpts_default_view.png)

### パネル出力

メディア再生滞在時間パネルは、折れ線グラフと概要番号を返し、再生滞在時間の最大値、最小値および合計（あるいはその両方）の詳細が含まれます。パネルの上部に、選択したパネル設定を示すサマリー行が表示されます。

![メディア再生滞在時間パネルを編集](/help/assets/icons/Edit.svg) を選択すると、いつでもパネルを編集および再作成できます。

シリーズの分類を選択した場合は、折れ線グラフに線と次の各項目の概要番号が表示されます。

![折れ線グラフと概要を示すメディア再生滞在時間の出力。](assets/mpts_outputs1.png)

### データソース

このパネルで使用できる唯一の指標は「再生滞在時間」です。

| 指標 | 説明 |
|---|---|
| 再生滞在時間 | 視聴されたコンテンツの合計 `hours:minutes:seconds`（または `minutes`）。選択した精度で、一時停止、バッファー、開始のための時間を含みます。 |

## よくある質問（FAQ）

| 質問 | 回答 |
|---|---|
| フリーフォームテーブルはどこにありますか？ データソースの確認方法を教えてください。 | <p></p><p>このビューでは、フリーフォームテーブルは使用できません。 データソースをダウンロードするには、折れ線グラフのコンテキストメニューで、CSV ファイルをダウンロードするためのオプションを選択します。</p> |
| <p>精度が変更されたのはなぜですか？</p> | <p>この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。</p><p></p><p>大きい日付範囲から小さい日付範囲に変更する場合、日付範囲が変更されると、精度は許容できる最小の詳細に更新されます。 より高い精度を表示するには、パネルを編集して再作成します。</p> |
| <p></p><p>ビデオ名、フィルター、コンテンツタイプなどを比較するにはどうすればよいですか？</p> | <p>単一のビジュアライゼーション内でこれらを比較するには、フィルター、ディメンションまたはシリーズ分類フィルター内の特定のディメンション項目をドラッグします。</p><p></p><p>ビューの分類は 10 個に制限されています。 10 を超える表示を行うには、複数のパネルを使用する必要があります。</p> |
| 日付範囲の比較方法を教えてください。 | 単一のビジュアライゼーション内の日付範囲を比較するには、2 つ以上の日付範囲をドラッグして、シリーズの分類を使用します。 これらの日付範囲は、パネルの日付範囲より優先されます。 |
| ビジュアライゼーションのタイプを変更する方法を教えてください。 | <p></p><p>このパネルでは、時系列の線のビジュアライゼーションのみが可能です。</p> |
| 異常値検出を実行できますか？ | <p></p><p>いいえ。このパネルでは異常値検出は利用できません。</p> |


>[!MORELIKETHIS]
>
>[パネルの作成](/help//analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>[メディア分平均オーディエンスパネル](average-minute-audience-panel.md)
>[メディア同時視聴者数パネル](media-concurrent-viewers.md)
>

<!--
# Media Playback Time Spent panel

In Analysis Workspace, Playback Time Spent is the amount of time spent viewing your media streams at a specific point in time. It includes pause, buffer, and time to start.

The Media Playback Time Spent panel enables analysis of playback over time, with details on peak concurrency and the ability to break down and compare. 

Customers who have purchased the Streaming Media Collection Add-on can analyze playback time spent to gain valuable insight into the quality of content and viewer engagement, and to help when troubleshooting or planning for volume or scale.

Playback Time Spent can help you understand:

* Where peak concurrency occurred

* Where drop-offs occurred 

Following is a video overview of this panel:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/media-analytics/measuring-media-analytics/media-playback-time-spent-panel)

## Use the Media Playback Time Spent panel

1. Go to a report suite with streaming media components enabled. 
1. Select the panel icon on the far-left, then drag the panel into your Analysis Workspace project.
1. Continue with the following sections to customize the Media Playback Time Spent panel

   * [Panel Inputs](#panel-inputs)
   * [Panel Output](#panel-output)

## Panel Inputs {#Input}

You can configure the Media Playback Time Spent panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today. You may edit it to view a single day or many months at a time.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers|To see date or time details for playback time spent, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough. Sum adds up the total playback time spent for the selection. The panel default shows Maximum only, but you can change it to show Minimum, Sum, or any combination of the three.<br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown|Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges.<p>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.</p><p>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.</p>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|
|Time format|You can view the playback time spent in either `Hours:Minutes:Seconds` (default) or in `Minutes` (which is displayed in whole numbers, rounded up at .5). |
|Date sequence display|If you've placed at least two date range segments as series breakdowns you'll see the option to select either overlay (default) or sequential. Overlay will display the lines with a common x-axis start so that they run in parallel, while sequential will display the lines with their specific x-axis start. If the data lines up (for example, segment 1 ends at 8:44 pm and segment 2 starts at 8:45 pm), then the lines will show in sequence. |

## Default view

![Default view](assets/mpts_default_view.png)

## Panel Output {#Output}

The Media Playback Time Spent panel returns a line chart and summary numbers to include details for the maximum, minimum, and/or sum of playback time spent. At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![media playback time spent output](assets/mpts_outputs1.png)

### Data Source

The only metric that can be used in this panel is Playback Time Spent.

|Metric|Description|
|---|---|
|Playback Time Spent|Total `hours:minutes:seconds` (or `minutes`) of content viewed during the selected granularity including pause, buffer, and time to start.|

## FAQs

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?|The Freeform table is not available in this view. You can download the data source by right-clicking on the line chart and downloading the CSV ﬁle.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range. <p>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.</p>|
| How do I compare video names, segments, content types, etc?| To compare these in a single visualization, drag segments, dimensions, or speciﬁc dimension items in the series breakdown ﬁlter.The view is limited to 10 breakdowns. To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges. These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No. Anomaly detection is not available for this panel.|

-->
