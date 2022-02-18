---
title: メディア分平均オーディエンスパネル
description: Analysis Workspaceの Media Average Minute Audience パネルの使用方法と解釈方法。
feature: Panels
role: User, Admin
source-git-commit: 3cb991e7f440a72247b7261ad5959e15619e8a76
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 10%

---

# メディア分平均オーディエンスパネル

Media Analytics customers can use the average minute audience panel to better understand average consumption of their content. Average minute audience enables comparisons of programming of any length or genre. さらに、顧客は、このデジタル平均分オーディエンスを、線形 TV 平均分指標と比較または追加できます。 このパネルでは、カスタム期間の平均オーディエンスをより柔軟に測定できるほか、期間の分類が事後に更新された場合にも測定できます。 現在の分平均オーディエンス指標は、処理時間が処理時に使用できる場合にのみ機能します。

Analysis Workspaceでの分平均オーディエンスは、メディアストリームの視聴に費やした時間を、コンテンツの期間または選択した精度の期間の合計選択範囲で割った値です。

メディア分平均オーディエンスパネルは、期間が分類を使用して使用可能になっている場合に、選択した特定のコンテンツに基づいて分平均オーディエンス分析を提供します。
分平均オーディエンスパネルでは、選択した期間の分析も提供されます。分類を使用して期間を利用できるかどうかに関わらず、特定のコンテンツでフィルタリングできます。 To access the Media Average Minute Audience Panel, navigate to a report suite with Media Analytics components enabled. 次に、左端のパネルアイコンをクリックし、 パネルを Analysis Workspace プロジェクトにドラッグします。

<!-- For more information, see the Media Average Minute Audience introduction video:
<< replace with AMA video when available >> -->

<!-- >[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12) -->

## パネル入力 {#Input}

次の入力設定を使用して、メディアの分平均オーディエンスパネルを設定できます。

| 設定 | 説明 |
|---------|------------|
| パネルの日付範囲 | パネルの日付範囲のデフォルトは「今日」です。 一度に 1 日または複数の月を表示するように編集できます。<br></br>この視覚化は、1440 行のデータに制限されています（たとえば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は自動的に更新され、日付範囲全体に対応します。 |
| Drag a segment here (or any other components) | 他のパネルと同様に、この設定では、作成したセグメントに基づいて選択内容がフィルタリングされます。 これは、特定のプラットフォーム、ライブストリーム、またはその他の一般的なメディアセグメントを確認する優れた方法です。 |
| 指標の計算対象 | この設定を使用すると、「 」を選択して、特定のコンテンツの分平均オーディエンスを表示するかどうかを選択できます *特定のコンテンツ*&#x200B;またはを選択し、特定の期間の分平均オーディエンスを表示する場合は、 *カスタム期間*. <br></br>特定のコンテンツは、期間が分類を使用して更新された場合にのみ機能します。 If the duration is unavailable, or if you want to view the average minute audience for a time series with multiple pieces of content or content without a specific assigned duration (like during a live stream or event), then you should select custom time period. This setting changes the workflow and report output. |

### 特定のコンテンツ

| 設定 | 説明 |
|---------|------------|
| Reporting dimensions | 特定のコンテンツを選択する場合、レポート出力を選択して、ビデオ名またはコンテンツ ID フィールドを使用し、選択した期間に対するコンテンツと関連する分平均オーディエンスを表示できます。 |
| コンテンツを (オプション) でフィルタリング | You can filter the specific content depending on the view you want or the way your data is structured. |
| 表示、シーズン、エピソード | 「表示、シーズン、エピソード」を選択すると、使用可能な番組がドロップダウンに表示され、検索を使用してフィルタリングできます（または、左の列から番組名をドラッグ&amp;ドロップします）。 選択を終了してショーの季節をすべて表示したり、季節ごとにフィルターしたり、エピソードごとにフィルターしたりできます。 この設定は、選択した期間の番組、季節、エピソードのデータを表示します。 |
| カスタムのディメンション | 番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して見つけることができます。 ディメンション項目は、その選択に基づいて自動的に入力され、エピソードとして扱われます。 |
| なし | 次を選択できます。 *なし* 選択した項目の 1 分平均オーディエンスデータを持つすべてのビデオ名を表示します。 |

### Specific content advanced settings

| 設定 | 説明 |
|---------|------------|
| テーブル設定 | デフォルト設定では、テーブル内の計算値が表示され、平均分オーディエンスの分子と分母がテーブルの前の列として表示されます。 このオプションの選択を解除すると、2 つの列が削除され、ビデオ名またはコンテンツ ID の横の分平均オーディエンスのみが残ります。 |
| 滞在時間指標 | デフォルトのコンテンツ視聴時間（コンテンツ視聴時間のみを含む）を選択するか、メディア視聴時間（コンテンツと広告時間を含む）を分平均オーディエンスの分子計算として使用するかを選択できます。 |

### カスタムの期間

| 設定 | 説明 |
|---------|------------|
| 精度 | デフォルトの精度は 5 分ですが、カレンダーの選択で行われた全期間の選択内で時系列の分母として使用される任意の精度を選択できます。 例えば、精度を 5 分にして午後 12:00 ～ 12:30 に設定した場合、30 分間の平均分オーディエンスと、各 5 分間の平均分オーディエンスを持つ 6 つの行が返されます。 これらの行は、時系列グラフのデータポイントとして使用されます。 |
| コンテンツを (オプション) でフィルタリング | 目的の表示やデータの構造に応じて、特定のコンテンツをフィルタリングできます。 |
| 表示、シーズン、エピソード | 選択 *表示、シーズン、エピソード* 使用可能な番組がドロップダウンに表示され、検索でフィルタリングできます（または、左の列から番組名をドラッグ&amp;ドロップしてフィルタリングできます）。 選択を終了してショーの季節をすべて表示したり、季節ごとにフィルターしたり、エピソードごとにフィルターしたりできます。 この設定は、選択した期間の番組、季節、エピソードのデータを表示します。 |
| カスタムのディメンション | 番組名がカスタムディメンションの下にある場合は、ディメンション（オプション）ドロップダウンで検索するか、左列の検索を使用して見つけることができます。 The dimension item automatically populates based on that selection and is treated as an episode. |
| なし | You can choose *None* to show all the video names over the time period you’ve chosen. |

### Custom time period advanced settings

| 設定 | 説明 |
|---------|------------|
| テーブル設定 | The default setting displays the calculation values in the table, which displays the numerator and denominator of the average minute audience as the preceding columns in the table. このオプションの選択を解除すると、これら 2 つの列が削除され、期間の次の平均分オーディエンスのみが残ります。 |


## Specific Content Panel Output

Media Average Minute Audience パネルは、次の値を返します。

* 選択全体の合計分平均オーディエンス
* Filters and average minute audience for the individual videos displayed in a table
* 詳細設定が選択されている場合は、コンテンツ視聴時間とビデオの長さ（時間）

パネルを編集および再構築するには、右上の編集鉛筆をクリックします。

![デフォルトのビュー](assets/specific-content-panel-output.png)


### 特定のコンテンツデータソース

このパネルで使用できる唯一の指標は、分平均オーディエンスです。

| 指標 | 説明 |
|--------|-------------|
| 分平均オーディエンス | The time spent viewing your media stream divided by the video length (duration) supplied via Classifications. |

## Custom Time Period Panel Output {#custom-time-period-output}

メディア分平均オーディエンスパネルは、選択全体の分平均オーディエンス、最大分平均オーディエンスと最小分平均オーディエンス、および選択全体の分平均オーディエンスを示す線系列グラフを返します。 The table below shows the filters and average minute audience for the granularities, as well as the content time spent and granularity for each time period if that advanced setting was selected.

パネルを編集および再構築するには、右上の編集鉛筆をクリックします。

![同時ビューア出力](assets/custom-time-period-panel-output.png)

### Custom Time Period Data Source

このパネルで使用できる唯一の指標は、分平均オーディエンスです。

| 指標 | 説明 |
|---|---|
| 分平均オーディエンス | メディアストリームの視聴に費やした時間を、合計選択または選択した精度（分単位）で割った値です。 |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
