---
title: メディアの同時視聴者数パネル
description: Analysis Workspaceのメディア同時閲覧者パネルを使用および解釈する方法を説明します。
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 95%

---


# メディア同時視聴者数パネル {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="メディア同時視聴者数"
>abstract="パネルを作成して、特定のコンテンツまたは特定の期間の分平均オーディエンスを分析します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="メディア同時視聴者数"
>abstract="同時視聴者数の推移を分析、ピーク時の同時実行を表示、または分類して比較します。<br/><br>**精度**：同時視聴者数を表示する期間を選択します。<br/>**パネルの概要数値**：<br/>各行の日付または時刻の詳細と共に概要数値を表示するオプション。最大値は、ピーク時の同時実行の詳細を示します。最小値は、トラフの詳細を示します。<br/>**系列の分類（オプション）**：セグメント、ディメンション、ディメンション項目または日付範囲でビジュアライゼーションを分類できます。一度に 10 行まで表示できます。分類は 1 つのレベルに制限されます。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** のメディア同時視聴者数パネルについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** バージョンについて詳しくは、[メディア同時視聴者数パネル](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md)を参照してください。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>メディア分平均オーディエンスパネルは、Adobe Analytics for Streaming Media アドオンを購入したお客様のみが利用できます。
>
>詳しくは、アドビ担当営業または販売店か、アドビアカウントチームにお問い合わせください。
>

**[!UICONTROL メディア同時視聴者数]**&#x200B;パネルを使用すると、同時実行のピークの詳細と分類および比較機能を使用して、経時的に同時視聴者を分析できます。

同時視聴者数を分析して、ピーク同時実行が発生した場所や離脱が発生した場所を把握し、コンテンツと視聴者関与の質に関する貴重なインサイトを得ることができます。また、容量や規模のトラブルシューティングや計画にも役立ちます。

Analysis Workspace では、同時視聴者数指標は、セッション数にかかわらず、特定の時点におけるメディアストリームを視聴しているユニークユーザー数です。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [メディア同時視聴者数パネル](https://video.tv.adobe.com/v/330177?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]



## 使用

**[!UICONTROL メディア同時視聴者数]**&#x200B;パネルを使用するには：

1. **[!UICONTROL メディア同時視聴者数]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. ストリーミングメディア用 Adobe Analytics アドオンから設定されたコンポーネントを含むパネルのデータビューを選択していることを確認してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

次の入力設定を使用して、メディア同時視聴者数パネルを設定できます。

| 設定 | 説明 |
|---|---|
| **[!UICONTROL パネルの日付範囲]** | パネルの日付範囲のデフォルトは「今日」です。 一度に 1 日または複数の月を表示するように編集できます。<br> <br>この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
| **[!UICONTROL 精度]** | 精度のデフォルトは「分」です。<br>この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
| **[!UICONTROL パネルの概要番号]** | 同時視聴者数の日時の詳細を表示するには、概要番号を使用できます。最大値は、ピーク同時実行性の詳細を示します。**[!UICONTROL 最小値]**&#x200B;は、トラフの詳細を示します。  パネルのデフォルトでは「最大値」のみが表示されますが、「最小値」に変更するか、「最大値」と「最小値」の両方を表示するように変更できます。<br><br>分類を使用している場合は、それぞれの概要番号が表示されます。 |
| **[!UICONTROL シリーズの分類]** | オプションとして、フィルター、ディメンション、ディメンション項目または日付範囲でビジュアライゼーションを分類できます。<br>一度に 10 行まで表示できます。分類は 1 つのレベルに制限されます。<br>ディメンションをドラッグすると、選択したパネルの日付範囲に基づいて、上位のディメンション項目が自動的に選択されます。<br>日付範囲を比較するには、2 つ以上の日付範囲をシリーズ分類フィルターにドラッグします。 |

次に、**[!UICONTROL 最大のみ]**&#x200B;の概要番号を使用して、**[!UICONTROL 分]**&#x200B;の精度に設定されたパネルの例を示します。**[!UICONTROL その他]**、**[!UICONTROL テーブル]**、**[!UICONTROL 携帯電話]**、**[!UICONTROL ゲームコンソール]**、**[!UICONTROL メディアプレーヤー]**、**[!UICONTROL セットトップボックス]**、**[!UICONTROL テレビ]**&#x200B;に分類されます。

![10 個のディメンション、セグメントまたは日付範囲のうち 7 個を示すメディア同時視聴者数シリーズの分類表示。](assets/concurrent-viewers-series-breakdown.png)

### パネル出力

メディアの同時視聴者数パネルは、最大および／または最小の同時視聴者数の詳細を含む折れ線グラフと概要番号を返します。 パネルの上部に、選択したパネル設定を示すサマリー行が表示されます。

「![メディア同時視聴者数パネルを編集](/help/assets/icons/Edit.svg)」を選択すると、いつでもパネルを編集および再作成できます。

シリーズの分類を選択した場合は、折れ線グラフに線と以下の各項目の概要番号が表示されます。

![メディア同時視聴者数の出力。](assets/concurrent-viewers-output.png)

### データソース

このパネルで使用できる指標は&#x200B;**[!UICONTROL 同時視聴者数]**&#x200B;のみです。

| 指標 | 説明 |
|---|---|
| **[!UICONTROL 同時視聴者数]** | セッション数にかかわらず、特定の時点におけるメディアストリームを視聴しているユニークユーザー数です。 |

このビューでは、フリーフォームテーブルは使用できません。 データソースを表示するには、折れ線グラフビジュアライゼーションのコンテキストメニューからデータソースをダウンロードし、「**[!UICONTROL データを CSV としてダウンロード]**」を選択します。シリーズの分類が含まれています。

![「データを CSV としてダウンロード」がハイライト表示された同時視聴者数の出力オプション。](assets/concurrent-viewers-download-csv.png)

## よくある質問（FAQ）

| 質問 | 回答 |
|---|---|
| フリーフォームテーブルはどこにありますか？ データソースの確認方法を教えてください。 | このビューでは、フリーフォームテーブルは使用できません。 折れ線グラフのコンテキストメニューからデータソースをダウンロードし、「**[!UICONTROL データを CSV としてダウンロード]**」を選択します。 |
| 精度が変更されたのはなぜですか？ | この視覚化は、1440 行のデータに制限されています（例えば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。<br><br>広い日付範囲から狭い日付範囲に変更する場合、日付範囲が変更されると、精度は許容できる最小の詳細度に更新されます。より高い精度を表示するには、パネルを編集して再作成します。 |
| ビデオ名、フィルター、コンテンツタイプなどを比較するにはどうすればよいですか？ | 単一のビジュアライゼーション内でこれらの項目を比較するには、フィルター、ディメンションまたはシリーズ分類フィルター内の特定のディメンション項目をドラッグします。<br><br>ビューの分類は 10 個に制限されています。 10 を超える表示を行うには、複数のパネルを使用する必要があります。 |
| 日付範囲の比較方法を教えてください。 | 単一のビジュアライゼーション内の日付範囲を比較するには、2 つ以上の日付範囲をドラッグして、シリーズの分類を使用します。 これらの日付範囲がパネルの日付範囲より優先されます。 |
| ビジュアライゼーションのタイプを変更する方法を教えてください。 | このパネルでは、時系列の線のビジュアライゼーションのみが可能です。 |
| 異常値検出を実行できますか？ | いいえ。このパネルでは異常値検出は利用できません。 |
| アクティブセッションではなく、ユニークユーザーを使用するのはなぜですか？ | ユニークユーザーを使用すると、（セッションの終了と開始が同時に行われる）番組の境界で不要なスパイクを削除できます。 |
| 同時視聴者数の精度を分単位よりも細かくするとはどういう意味ですか？ | 精度が 1 分を超える場合、同時視聴者数はその時間範囲内のすべての分におけるユニーク同時視聴者数の合計です。 例えば、時間レベルの精度の同時視聴者数は、その時間内のすべての分のユニーク同時視聴者数の合計です。 |
| ワークスペースパネルには、同時視聴者数レポートと同じ情報が表示されますか？ | いいえ。Analysis Workspace では、同時視聴者数指標は、特定の時点におけるメディアストリームを視聴しているユニークユーザー数として定義されます。セッション数には関係ありません。<br><br>この指標は、同時アクティブセッションを使用する、「レポート」セクションの同時視聴者数レポートとは異なります。ユニークユーザーを使用すると、（セッションの終了と開始が同時に行われる）番組の境界で不要なピークが削除されます。 |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[パネルの作成](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>>[メディア再生滞在時間パネル](media-playback-time-spent.md)
>>[メディア分平均オーディエンスパネル](average-minute-audience-panel.md)
>
<!--
# Media Concurrent Viewers panel

Customers who have purchased the Streaming Media Collection Add-on can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Concurrent Viewers is the number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a report suite with streaming media components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

Here is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panel Inputs {#Input}

You can configure the Media Concurrent Viewers panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown| Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges. <br><br>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br><br>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.<br><br>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

### Default view

![Default view](assets/concurrent-viewers-default.png)


### Series breakdown view

![series breakdown view](assets/concurrent-viewers-series-breakdown.png)

## Panel Output {#Output}

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![concurrent viewers output](assets/concurrent-viewers-output.png)

### Data Source

The only metric that can be used in this panel is Concurrent Viewers:

|Metric|Description|
|---|---|
|Concurrent Viewers| Number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted 'spikes' at show boundaries (where sessions are ending and starting at the same time).|

A Freeform table is not available in this view.  In order to view the data source, you may right-click on the line chart and download as a .csv file.  Series breakdowns will be included.


![concurrent viewers output](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source by right-clicking on the line chart and downloading the CSV file.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, segments, content types, etc?|To compare these in a single visualization, drag segments, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique visitors instead of active sessions?|Using unique visitors enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers is the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, Concurrent viewers is defined as the number of unique visitors viewing your media stream at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted spikes at show boundaries—where sessions are ending and starting at the same time.|

-->
