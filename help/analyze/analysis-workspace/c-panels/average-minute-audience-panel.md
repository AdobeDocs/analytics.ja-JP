---
title: メディア分平均オーディエンスパネル
description: Analysis Workspaceのメディア分平均オーディエンスパネルを使用および解釈する方法について説明します。
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 92%

---

# メディア分平均オーディエンスパネル {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="メディア分平均オーディエンス"
>abstract="パネルを作成して、特定のコンテンツまたは特定の期間の分平均オーディエンスを分析します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="メディア分平均オーディエンス"
>abstract="特定のメディアコンテンツまたはカスタム期間のパフォーマンスを表示します。<br/><br/>**一般パラメーター&#x200B;**<br/>**指標の計算**：パネルに使用する指標を選択します。「**特定のコンテンツ**」を選択し、コンテンツの長さに基づいて、特定のコンテンツまたはイベントの分平均オーディエンスを分析します。**カスタム期間を選択**&#x200B;し、カスタム選択された期間の分平均オーディエンスの変化を分析します。<br/>**レポートディメンション**：**コンテンツ ID** ディメンションの&#x200B;**ビデオ名**&#x200B;でレポートする場合に選択します。指標として「特定のコンテンツ」を選択した場合にのみ使用できます。<br/>**精度**：レポートの精度を選択します。指標として「カスタム期間」を選択した場合にのみ使用できます。<br/>**コンテンツのフィルター基準（オプション）**：特定の番組、シーズン、エピソードを選択するか、コンテンツをフィルタリングするカスタムディメンションを選択します。<br/><br/>**詳細設定&#x200B;**<br/>**テーブル設定**：計算値をテーブルに表示するかどうかを選択します。<br/>**滞在時間指標**：特定のコンテンツ計算に使用する滞在時間指標を選択します。指標として「特定のコンテンツ」を選択した場合にのみ使用できます。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_この記事は、_ AdobeAnalytics![&#x200B; &#x200B;](/help/assets/icons/AdobeAnalytics.svg)Adobe Analytics _&#x200B;**のメディア分平均オーディエンスパネルに関する情報を提供します**&#x200B;_。<br/>_この記事の [CustomerJourneyAnalytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/average-minute-audience-panel)_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) 版については、_&#x200B;**メディア分平均オーディエンスパネル** を参照してください。_

>[!ENDSHADEBOX]

>[!NOTE]
>
>**[!UICONTROL メディア分平均オーディエンス]** パネルは、Adobe Analytics for Streaming Media アドオンを購入したお客様のみが利用できます。
>
>詳しくは、アドビ担当営業または販売店か、アドビアカウントチームにお問い合わせください。
>

Analysis Workspace では、分平均オーディエンスは次の情報を提供できます

* 特定のメディアストリームの視聴に費やした時間を、コンテンツの期間で割った値、または
* 選択した精度で、カスタム期間中に視聴に費やした時間。

メディア分平均オーディエンスパネルを使用すると、あらゆる長さやジャンルのプログラムを比較して、コンテンツの平均消費量を理解できます。例えば、30 分のシットコムと 3 時間のスポーツイベントを比較すると、平均消費量を理解できます。

さらに、メディア分平均オーディエンスパネルを使用して、このデジタル分平均オーディエンスを、線形 TV 分平均指標と比較したり追加したりできます。

メディア分平均オーディエンスパネルでは、分平均オーディエンス指標に対して次のメリットがあります。

* カスタム期間をサポートします

* ビューを処理した後に期間の分類を更新できます（期間の分類が存在しなかったか、修正する必要がある場合）

  指標を使用する際にこの更新を行うと、期間の分類は存在しません（分類が存在しなかった場合）。 または、期間の分類が古くなっています（分類が存在したが正しくない場合）。

## 使用

**[!UICONTROL メディア分平均オーディエンス]**&#x200B;パネルを使用するには：

1. **[!UICONTROL メディア分平均オーディエンス]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. Adobe Analytics for Streaming Media アドオンから設定されたコンポーネントを含むパネルのレポートスイートを選択していることを確認してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

この節で説明している入力設定を使用して、メディア分平均オーディエンスパネルを設定します。

1. 次の入力設定を指定します。

   | 設定 | 説明 |
   |---------|------------|
   | **パネルの日付範囲** | パネルの日付範囲のデフォルトは「[!UICONTROL **今月**]」です。一度に 1 日または複数の月を表示するように編集できます。<br></br>このビジュアライゼーションは、1440 行のデータ（例えば、分単位の精度で 24 時間）に制限されています。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。 |
   | [!UICONTROL **ここにセグメント（または他のコンポーネント）をドロップ**] | 他のパネルと同様に、この設定では、作成したセグメントに基づいて選択内容がフィルタリングされます。この設定は、特定のプラットフォーム、ライブストリームまたはその他の一般的なメディアセグメントを調べる優れた方法です。 |
   | [!UICONTROL **指標の計算対象**] | [**[!UICONTROL 特定のコンテンツ]**](#specific-content)の分平均オーディエンスを表示するかどうかを選択します。 または、[**[!UICONTROL カスタム期間]**](#custom-time-period)の分平均オーディエンスを表示する場合も同様です。<br/><br/>次の場合に&#x200B;[!UICONTROL **カスタム期間**]&#x200B;を選択します。 <ul><li>期間を使用できない場合、または </li><li>複数のコンテンツを含む時系列の分平均オーディエンスを表示する場合、または</li><li>（ライブストリームやイベント中など）特定の期間が割り当てられていないコンテンツの場合</li></ul></li></li></ul> <p>この設定により、ワークフローとレポートの出力が変更されます。</p> |

1. [!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンリストで選択したオプションに応じて、[特定のコンテンツ](#specific-content)または[カスタム期間](#custom-time-period)に進みます。

#### 特定のコンテンツ

1. [パネル入力を設定](#panel-inputs)する際に、[!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンメニューで「[!UICONTROL **特定のコンテンツ**]」を選択した場合は、次の設定オプションを指定します。

   | 設定 | 説明 |
   |---------|------------|
   | [!UICONTROL **レポートディメンション**] | 特定のコンテンツを選択する場合、レポート出力を選択して、ビデオ名またはコンテンツ ID フィールドを使用し、コンテンツとそれに関連する分平均オーディエンスを表示できます。 |
   | [!UICONTROL **コンテンツのフィルター基準（オプション）**] | 目的とする表示やデータの構造によって特定のコンテンツをフィルタリングする方法を選択します。 <ul>[!UICONTROL **番組、シーズン、エピソード**]：使用可能な番組がドロップダウンに表示され、検索を使用してフィルタリングできます（または、左の列から番組名をドラッグ＆ドロップします）。 そこで選択を終了して、番組のすべてのシーズンを表示するか、個々のシーズン、次に個々のエピソードでフィルタリングできます。この設定では、選択した期間の番組、シーズンまたはエピソードのデータを表示します。</li><li>[!UICONTROL **カスタムディメンション**]：番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して見つけることができます。ディメンション項目は、その選択に基づいて自動的に入力され、エピソードとして扱われます。</li><li>[!UICONTROL **なし**]：選択した項目の分平均オーディエンスデータを持つすべてのビデオ名が表示されます（このオプションはデフォルトで選択されています）。</li></ul> |

1. [特定のコンテンツの詳細設定](#specific-content-advanced-settings)に進んで、詳細設定を指定します。

#### 特定のコンテンツの詳細設定

1. [!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンメニューで「[!UICONTROL **特定のコンテンツ**]」を選択し、「[!UICONTROL **詳細設定を表示**]」を選択して、次の設定オプションを指定します。

   | オプション | 説明 |
   |---------|------------|
   | **[!UICONTROL テーブル設定]** | デフォルトオプションの「**[!UICONTROL テーブル内の計算値を表示]**」では、分平均オーディエンスの分子と分母がテーブルの前の列として表示されます。このオプションを選択解除すると、これら 2 つの列が削除されます。 分平均オーディエンス列は、ビデオ名またはコンテンツ ID の横のテーブルに残ります。 |
   | **[!UICONTROL 滞在時間指標]** | デフォルトの「**[!UICONTROL コンテンツ視聴時間]**」オプション（コンテンツ視聴時間のみを含む）を選択できます。または、**[!UICONTROL メディア視聴時間]**（コンテンツ時間と広告時間を含む）を分平均オーディエンスの分子の計算に使用することを選択できます。 |

1. 「[!UICONTROL **作成**]」を選択して、メディア分平均オーディエンスパネルの作成を完了します。

1. メディア分平均オーディエンスパネルの使用方法について詳しくは、[パネル出力](#panel-output)を参照してください。

#### カスタム期間

1. [パネル入力を設定](#panel-inputs)する際に、[!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンメニューで「[!UICONTROL **カスタム期間**]」を選択した場合は、次の設定オプションを指定します。

   | オプション | 説明 |
   |---------|------------|
   | **[!UICONTROL 精度]** | デフォルトの精度は [!UICONTROL **5 分**]&#x200B;ですが、選択された期間の範囲内で、時系列の分母として使用される任意の精度を選択できます。例えば、精度を 5 分にして午後 12:00～12:30 を選択すると、30 分間全体の分平均オーディエンスと、5 分間ごとの分平均オーディエンスを含んだ 6 つの行が返されます。 これらの行は、時系列グラフのデータポイントとして使用されます。 |
   | [!UICONTROL **コンテンツのフィルター基準（オプション）**] | 目的とする表示やデータの構造によって特定のコンテンツをフィルタリングする方法を選択します。 <ul>[!UICONTROL **番組、シーズン、エピソード**]：使用可能な番組がドロップダウンに表示され、検索を使用してフィルタリングできます（または、左の列から番組名をドラッグ＆ドロップします）。 そこで選択を終了して、番組のすべてのシーズンを表示するか、個々のシーズン、次に個々のエピソードでフィルタリングできます。この設定では、選択した期間の番組、シーズンまたはエピソードのデータを表示します。</li><li>[!UICONTROL **カスタムディメンション**]：番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して見つけることができます。ディメンション項目は、その選択に基づいて自動的に入力され、エピソードとして扱われます。</li><li>[!UICONTROL **なし**]：選択した項目の分平均オーディエンスデータを持つすべてのビデオ名が表示されます（このオプションはデフォルトで選択されています）。</li></ul> |

1. [カスタム期間の詳細設定](#custom-time-period-advanced-settings)に進んで、詳細設定を指定します。

#### カスタム期間の詳細設定

1. [!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンメニューで「[!UICONTROL **カスタム期間**]」を選択し、「[!UICONTROL **詳細設定を表示**]」を選択して、次の設定オプションを指定します。

   | オプション | 説明 |
   |---------|------------|
   | **[!UICONTROL テーブル設定]** | デフォルト設定では、テーブル内の計算値が表示され、分平均オーディエンスの分子と分母がテーブルの前の列として表示されます。このオプションの選択を解除すると、2 つの列が削除され、期間の横の分平均オーディエンスのみが残ります。 |

1. 「[!UICONTROL **作成**]」を選択して、メディア分平均オーディエンスパネルの作成を完了します。

1. メディア分平均オーディエンスパネルの使用方法について詳しくは、[パネル出力](#panel-output)を参照してください。

### パネル出力

パネル出力は、[パネル入力を設定](#panel-inputs)する際に&#x200B;[!UICONTROL **指標の計算対象**]&#x200B;ドロップダウンメニューで「[!UICONTROL **特定のコンテンツ**]」または「[!UICONTROL **カスタム期間**]」のどちらを選択したかによって異なります。

#### 特定のコンテンツ

メディア分平均オーディエンスパネルは、次の値を返します。

* 選択期間全体の合計分平均オーディエンス
* テーブルに表示される個々のビデオのフィルターおよび分平均オーディエンス
* 詳細設定が選択されている場合は、コンテンツ視聴時間とビデオの長さ（期間）

パネルを編集および再作成するには、右上の ![編集](/help/assets/icons/Edit.svg) を選択します。

![デフォルトのビュー](assets/specific-content-panel-output.png)

#### 特定のコンテンツのデータソース

メディア分平均オーディエンスパネルでは、分平均オーディエンス指標のみを使用してデータを収集します。パネルでは、分類や他の指標は使用できません。

| 指標 | 説明 |
|--------|-------------|
| **[!UICONTROL 分平均オーディエンス]** | メディアストリームの視聴に費やした時間を、分類で提供されたビデオの長さ（期間）で割った値です。 |

#### カスタム期間 {#custom-time-period-output}

メディア分平均オーディエンスパネルは、次の値を返します。

* 選択期間全体の合計分平均オーディエンス

* 最大と最小の分平均オーディエンス

* 選択期間全体の分平均オーディエンスを示す線系列グラフ。

* 精度のフィルターと分平均オーディエンス、および期間ごとのコンテンツ視聴時間と精度を示すテーブル

  このテーブルは、詳細設定の「[!UICONTROL **テーブル内の計算値を表示**]」オプションを選択した場合にのみ表示されます。

パネルを編集および再作成するには、右上の ![メディア分平均オーディエンスパネルを編集](/help/assets/icons/Edit.svg) を選択します。


#### カスタム期間のデータソース

メディア分平均オーディエンスパネルでは、分平均オーディエンス指標のみを使用してデータを収集します。パネルでは、分類や他の指標は使用できません。

| 指標 | 説明 |
|---|---|
| **[!UICONTROL 分平均オーディエンス]** | メディアストリームの視聴に費やした時間を、選択期間全体または選択した精度（分単位）で割った値です。 |


>[!MORELIKETHIS]
>
> [パネルの作成](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
> [メディア同時視聴者数パネル](media-concurrent-viewers.md)
> [メディア再生滞在時間パネル](media-playback-time-spent.md)
>


<!--

# Media average minute audience panel

>[!NOTE]
>
>The Media average minute audience panel is available only to customers who have purchased the Streaming Media Collection Add-on. 
>
>Contact your Adobe Sales Representative or Adobe Account Team to purchase the Streaming Media Collection Add-on. 

In Analysis Workspace, average minute audience is the time spent viewing your media stream divided by the duration of the content or the total selection of the period and selected granularity.

The Media average minute audience panel enables you to better understand average consumption of your content by comparing programs of any length or genre. For example, you can understand average consumption when comparing a 30-minute sitcom with a 3-hour sporting event.

In addition, you can use the Media average minute audience panel to compare or append this digital average minute audience to linear TV average minute metrics. 

The Media average minute audience panel provides the following benefits over the Average Minute Audience metric:

* Supports custom time periods

* Allows for updating the duration classification after views are processed (if it was not present or if it needs to be corrected)

  If you did this when using the metric, it either won't exist (if the classification wasn't present) or it will be out of date (if the classification was present but incorrect).

## Access the Media average minute audience panel

1. In Analysis Workspace, go to a report suite that has streaming media components enabled. 

1. In the left nav, select the **Panels** icon.

   ![Panels icon in left nav](assets/panels-icon.png)

1. Drag the [!UICONTROL **Media average minute audience**] panel onto the canvas in Analysis Workspace.

1. To configure the panel, continue with [Panel inputs](#panel-inputs).

## Panel inputs {#Input}

Use the input settings described in this section to configure the Media average minute audience panel.

1. Begin creating a Media average minute audience panel, as described in [Access the Media average minute audience panel](#access-the-media-average-minute-audience-panel).

1. Configure the following input settings:

   | Setting | Description |
   |---------|------------|
   | **Panel date range** | The panel date range default is [!UICONTROL **This month**]. You can edit it to view a single day or many months at a time. <br></br> This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range. |
   | [!UICONTROL **Drop a segment here (or any other component)**] | Like other panels, this setting filters your selections based on segments you've created. This is a great way to look at specific platforms, live streams, or other common media segments. |
   | [!UICONTROL **Calculate metric for**] | Choose whether you want to see the average minute audience for a specific piece of content, or if you want to see the average minute audience for a custom period of time:<ul><li>**Specific content:** This is available only if the duration has been updated using Classifications. If the duration is unavailable, or if you want to view the average minute audience for a time series with multiple pieces of content or content without a specific assigned duration (like during a live stream or event), then you should select [!UICONTROL **Custom time period**]. (Durations can be set using Classifications either before or after processing time.)</li><li>**Custom time period:** This is available regardless of whether the durations is made available using Classifications.</li></ul> <p>This setting changes the workflow and report output.</p>  |

1. Continue with [Specific content](#specific-content) or [Custom time period](#custom-time-period), depending on the option you chose in the [!UICONTROL **Calculate metric for**] drop-down menu.

### Specific content

1. If you selected [!UICONTROL **Specific content**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | [!UICONTROL **Reporting dimension**] | When you choose specific content, you can select the report output to use either the video name or content ID fields to show the content and its associated average minute audience for the time period selected. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Specific content advanced settings](#specific-content-advanced-settings) to configure advanced settings. 

### Specific content advanced settings

1. With [!UICONTROL **Specific content**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting shows the calculation values in the table, which shows the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns, leaving only the average minute audience next to the video name or content ID. |
   | Time spent metric | You can choose the default content time spent, which includes only content time, or you can choose to use the media time spent, which includes content and ad time together as the numerator calculation for the average minute audience. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

### Custom time period

1. If you selected [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Granularity | The default granularity is [!UICONTROL **5-Minute**], but you can choose any of the granularities that are used as the denominator for the time series within your overall time period selection made in the calendar selection. For example, selecting 12:00 pm to 12:30 pm with a 5-minute granularity returns the average minute audience over the full half hour as well as six rows with the average minute audience for each 5-minute period. These rows are used as the datapoints for the time series chart. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Custom time period advanced settings](#custom-time-period-advanced-settings) to configure advanced settings. 

### Custom time period advanced settings

1. With [!UICONTROL **Custom time period**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration option:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting displays the calculation values in the table, which displays the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns leaving only the average minute audience next to the time period. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

## Panel output

The panel output differs depending on whether you chose [!UICONTROL **Specific content**] or [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs).

### Specific content

The Media average minute audience panel returns the following:

* Total average minute audience for your entire selection
* Filters and average minute audience for the individual videos displayed in a table 
* Content time spent and video length (duration) if that advanced setting was selected

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![Default view](assets/specific-content-panel-output.png)

### Specific content data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

| Metric | Description |
|--------|-------------|
| Average Minute Audience | The time spent viewing your media stream divided by the video length (duration) supplied via Classifications. |

### Custom time period {#custom-time-period-output}

The Media average minute audience panel returns the following:

* The total average minute audience for your entire selection

* The maximum and minimum average minute audience

* The line series graph showing the average minute audience over the entire selection.

* A table that shows the filters and average minute audience for the granularities, as well as the content time spent and granularity for each time period 

  This table displays only if the option under advanced settings called [!UICONTROL **Show calculation values in table**] is selected.

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![concurrent viewers output](assets/custom-time-period-panel-output.png)

### Custom time period data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

|Metric|Description|
|---|---|
|Average Minute Audience| The time spent viewing your media stream divided by the total selection or selected granularity in minutes.|

-->