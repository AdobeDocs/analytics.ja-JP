---
description: レポートの実行後は、レポートをカスタマイズして表示を行い、必要に応じてデータを分析できます。 レポートデータのフィルタリング、データのグラフ表示方法の変更、日付精度の変更などを行うことができます。
title: レポートのカスタマイズの概要
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# レポートのカスタマイズの概要

レポートの実行後は、レポートをカスタマイズして表示を行い、必要に応じてデータを分析できます。 レポートデータのフィルタリング、データのグラフ表示方法の変更、日付精度の変更などを行うことができます。

## カスタムレポートの作成 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

すべてのユーザーに対して表示する新しいカスタムレポートとして、レポートの現在の設定を保存する手順を説明します。

<!-- 

t_reports_custom.xml

 -->

管理者のみがカスタムレポートを作成できます。 作成したカスタムレポートは、その基となるレポートの横のメインレポートメニューに追加されます。

**カスタムレポートを作成するには**

1.  レポートを実行し、必要に応じて設定します。
1. クリック **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   既存のレポート名と重複していないことを確認します。

>[!MORELIKETHIS]
>
>* [メニューのカスタマイズ](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/customize-menus.translate.html)


## 日付または日付範囲の選択 {#task_9BEF7D4D839A4748B76E8500D1406C34}

レポートデータの期間を選択する際の手順を説明します。

<!-- 

t_reports_select_date.xml

 -->

特定の日、週、月または年を選択できます。 比較レポートを実行することもできます。

異なる日付範囲のレポートレットを含むダッシュボードを開くと、カレンダーで新しい日付範囲を選択できます。 変更は、レポート内のすべてのレポートレットに適用されるダッシュボードです。

**日付範囲を選択するには**

1. レポートを実行します。
1. 右上のカレンダーアイコンをクリックします。
1. 日付を選択します。

   次のことができます。

   * 表示の日、月または年（3つまで）。
   * 日付の上でカーソルをドラッグして、範囲を選択します。
   * 日付を手動で入力します。
   * 月名をクリックして月を選択します。
   * をクリック **[!UICONTROL Select Preset]** して、プリセット日を選択します。
   * 日付を比較します

1. クリック **[!UICONTROL Run Report]**.

## 比較日 {#task_95155C3700774B709F5FB81AE96B0824}

カレンダーを使用して、ランクレポート間の日付の比較を実行する手順を説明します。

<!-- 

t_reports_comparing_dates.xml

 -->

トレンドレポート間で日付を比較することはできません。

>[!NOTE]ダッシュボード内で主要指標について日付比較を行いたい場合は、2 つの異なるリクエストを使用してデータを [Report Builder](https://marketing.adobe.com/resources/help/ja_JP/arb/) に取り込みます。その後、Excel 内でカスタム数式を使用して両者の違いを分析します。

Reports &amp; Analyticsのランクレポート間で日付を比較するには：

1. レポートを実行します。
1. 右上のカレンダーをクリックします。
1. クリック **[!UICONTROL Compare Dates]**.
1. 使用する日付を選択します。
1. クリック **[!UICONTROL Run Report]**.

## 割合のグラフとしての表示 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

レポートの表に割合をグラフとして表示するかどうかを指定する手順を説明します。

<!-- 

t_reports_graph_percent.xml

 -->

このビジュアライゼーションは、ダッシュボードレポートレットでも使用できます。

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. クリック **[!UICONTROL Percent Shown As: Graph]**.

## レポートデータの標準化 {#task_8005B55E59BD479DA67BC618FF8BC94A}

レポートデータを標準化する手順を説明します。

<!-- 

t_reports_normalize.xml

 -->

比較日付のレポートを実行した後、またはA/B比較用に、データを標準化してレポート間の変化の割合を表示できます。 セカンダリデータセットは、選択した日数の差、またはトラフィックの量の差を補正するために調整されます。

**レポートデータを標準化するには**

1.  日付の比較をサポートするレポートを実行します。
1. をクリ **[!UICONTROL Compare Dates]**&#x200B;ックし、日付比較を指定します。
1. クリック **[!UICONTROL Run Report]**.
1. クリック **[!UICONTROL Normalize Data: Yes]**.

## レポート対象のページの選択 {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Web サイトのページからレポートのために特定のページを選択する手順を説明します。

<!-- 

t_reports_select_page.xml

 -->

1. (> > [!UICONTROL Page Views Report] )などのレ **[!UICONTROL Reports]** ポート **[!UICONTROL Site Metrics]** を生成 **[!UICONTROL Page Views]**&#x200B;する。
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1.  必要に応じて、ページを検索します。
1. ズーム後に **[!UICONTROL OK.]**

## レポートスイートの比較 {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

同じレポート内の2つのレポートスイートのレポートを表示する手順を説明します。

<!-- 

t_reports_compare_suites.xml

 -->

グラフ表示に加えて、レポートの表では割合の比較が表示されます。 次のレポートは比較して実行できます。

* サイトコンテンツ
* モバイル
* トラフィックソース
* キャンペーン
* 製品
* 訪問者保持率
* 訪問者プロファイル
* カスタムコンバージョン
* カスタムトラフィック
* ターゲット
* 調査

**レポートスイートを比較するには**

1. 比較できるレポートを生成します。
1. Click the **[!UICONTROL Compare to Site]** link.
1.  レポートスイートを選択します。
1. ズーム後に **[!UICONTROL OK.]**

## レポート精度の指定 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

時間別、日別、週別、月別、四半期別、または年別に表示レポートの合計を作成する手順を説明します。

<!-- 

t_reports_granularity.xml

 -->

レポートの期間によって、使用できる精度オプションが決まります。 例えば、1 ～ 2日の期間を **[!UICONTROL Hourly]** 選択している場合にのみ選択できます。 精度は、1年を超え **[!UICONTROL Yearly]** る場合にのみ選択できます。

**レポート精度を指定するには**

1. トレンドレポートの生成( **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## 曜日レポートの実行 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

特定の日の特定の曜日（特定の日付範囲の各月曜日など）にレポートを実行する手順を説明します。

<!-- 

t_reports_day_of_week.xml

 -->

この機能は、週または日の日付範囲でフィルターされたトレンドレポートにのみ適用されます。

1. 指定した日付範囲でトレンドレポートを実行します。
1. リンクをク **[!UICONTROL Day of Week]** リックし、日をクリックします。

## 「ワークスペースで試す」ボタン {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

レポートの上 **[!UICONTROL Try In Workspace]** 部にあるボタンをクリックすると、同じレポートがWorkspaceに読み込まれます。分析

<!-- 

try_in_workspace.xml

 -->

Reports &amp; Analyticsのほとんどのレポートに、「ワークスペースで試す」ボタンが追加され、分析ワークスペースで現在の表示を再現してさらにカスタマイズできるようになりました。

現在、このボタンは、ユーザー名にWorkspaceへのフル権限がある場合にのみ分析できます。

レポートをカスタマイズするすべての方法の詳細については、『 [分析ワークスペース](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/) 』ガイドを参照してください。
