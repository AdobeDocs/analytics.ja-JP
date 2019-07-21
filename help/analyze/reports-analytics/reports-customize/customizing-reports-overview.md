---
description: レポートの実行後は、レポートをカスタマイズしてニーズに応じたデータの表示、分析を行うことができます。レポートデータをフィルターしたり、データを図示する方法を変更したり、日付精度を変更したりできます。
seo-description: レポートの実行後は、レポートをカスタマイズしてニーズに応じたデータの表示、分析を行うことができます。レポートデータをフィルターしたり、データを図示する方法を変更したり、日付精度を変更したりできます。
seo-title: レポートの概要のカスタマイズ
solution: Analytics
title: レポートの概要のカスタマイズ
topic: Reports and Analytics
uuid: 37d221b7-50fd-4425- b2ba- f40911b72a2f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# レポートの概要のカスタマイズ

レポートの実行後は、レポートをカスタマイズしてニーズに応じたデータの表示、分析を行うことができます。レポートデータをフィルターしたり、データを図示する方法を変更したり、日付精度を変更したりできます。

## カスタムレポートの作成 {#task_BA6EACA3039C40AEA5605E1D8C76E646}

すべてのユーザーに表示される新規カスタムレポートとしてレポートの現在の設定を保存する手順を説明します。

<!-- 

t_reports_custom.xml

 -->

管理者だけがカスタムレポートを作成できます。作成したカスタムレポートは、その基となったレポートの隣にあるメインレポートメニューに追加されます。

**カスタムレポートを作成するには**

1.  レポートを実行し、必要に応じて設定します。
1. **[!UICONTROL その他]** /カスタムレポート **[!UICONTROL の作成をクリック]**&#x200B;します。
1. Name the report, then click **[!UICONTROL Save.]**

   既存のレポート名と重複していないことを確認します。

>[!MORE_LIKE_THIS]
>
>* [メニューのカスタマイズ](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=customize_menus)


## 日付または日付範囲の選択 {#task_9BEF7D4D839A4748B76E8500D1406C34}

レポートデータの対象期間を選択する手順を説明します。

<!-- 

t_reports_select_date.xml

 -->

特定の日、週、月、または年を選択できます。比較レポートを実行することもできます。を参照してください。

開いたダッシュボードに様々な日付範囲のレポートレットがある場合は、カレンダーで新しい日付範囲を選択できます。変更は、ダッシュボード内のすべてのレポートレットに適用されます。

**日付範囲を選択するには**

1. レポートの実行.
1. 右上のカレンダーアイコンをクリックします。
1.  日付を選択します。

   以下の操作を行うことができます。

   * 日、月、年を表示します（3 つまで）。
   * 日付上でカーソルをドラッグして範囲を選択します。
   * 日付を手動で入力します。
   * 月をクリックして月を選択します。
   * 「**[!UICONTROL プリセットの選択]」をクリックして、プリセット日付を選択します。**
   * 日付を比較します

1. Click **[!UICONTROL Run Report]**.

## 比較日 {#task_95155C3700774B709F5FB81AE96B0824}

カレンダーを使用してランクレポート間の日付の比較を実行する手順を説明します。

<!-- 

t_reports_comparing_dates.xml

 -->

トレンドレポート間の日付の比較はできません。

>[!NOTE]
>
>If you want to perform a date comparison on key metrics in a dashboard, you can pull the data into [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/) using two separate requests. その後、Excel 内でカスタム数式を使用して両者の違いを分析します。

Reports &amp; Analytics のランクレポート間で日付を比較するには、以下のようにします。

1. レポートの実行.
1. 右上のカレンダーをクリックします。
1. Click **[!UICONTROL Compare Dates]**.
1. 使用する日付を選択します。
1. Click **[!UICONTROL Run Report]**.

## 割合のグラフとしての表示 {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

レポートの表内の割合をグラフとして表示するかどうかを指定する手順を説明します。

<!-- 

t_reports_graph_percent.xml

 -->

グラフによる視覚化は、ダッシュボードのレポートレットでも利用できます。

1.  [!UICONTROL ページレポート]のように、パーセンテージをサポートするレポートを実行します。
1. **[!UICONTROL 割合の表示形式をクリックします。グラフ]**&#x200B;を参照してください。

## レポートデータの標準化 {#task_8005B55E59BD479DA67BC618FF8BC94A}

レポートデータを標準化する手順を説明します。

<!-- 

t_reports_normalize.xml

 -->

比較日付のレポートを実行した後、または A/B 比較用に、データを正規化してレポート間の変化の割合を表示できます。選択した日数間の差、またはトラフィック量の差を補正するためにセカンダリデータセットが調整されます。

**レポートデータを正規化するには**

1.  日付の比較をサポートするレポートを実行します。
1. Click **[!UICONTROL Compare Dates]**, then specify your date comparison.
1. Click **[!UICONTROL Run Report]**.
1. Click **[!UICONTROL Normalize Data: Yes]**.

## レポート対象のページの選択 {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Web サイトのページからレポートのために特定のページを選択する手順を説明します。

<!-- 

t_reports_select_page.xml

 -->

1. Generate a report, such as a [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Page Views]**).
1. 「**選択されたアイテム (ページ)**」リンクをクリックします。
1. 必要に応じて、[!UICONTROL ページの選択]ページで、表示するページを選択します。
1.  必要に応じて、ページを検索します。
1. Click **[!UICONTROL OK.]**

## レポートスイートの比較 {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

同じレポート内に 2 つのレポートスイートからのレポートを表示する手順を説明します。

<!-- 

t_reports_compare_suites.xml

 -->

グラフィック表示に加えて、レポート表でパーセント比較が表示されます。以下のレポートの比較を実行できます。

* サイトコンテンツ
* モバイル
* トラフィックソース
* キャンペーン
* 製品
* 訪問者保持率
* 訪問者プロファイル
* カスタムコンバージョン
* カスタムトラフィック
* Target
* Survey

**レポート スイートを比較するには**

1. 比較できるレポートを生成します。
1. 「**サイトと比較**」リンクをクリックします。
1.  レポートスイートを選択します。
1. Click **[!UICONTROL OK.]**

## レポート精度の指定 {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

レポート合計を時間別、日別、週別、月別、四半期別、年別に表示する手順を説明します。

<!-- 

t_reports_granularity.xml

 -->

レポートの期間によって、使用できる精度オプションが決まります。例えば、1～2 日の時間枠を選択した場合は、**[!UICONTROL 時間単位]しか選択できません。** 1 年を超える場合は、**[!UICONTROL 年単位]しか表示されません。**

**レポート精度を指定するには**

1. **[!UICONTROL サイトコンテンツ]** / **[!UICONTROL ページなどのトレンドレポートを生成します。]**
1.  「**閲覧者**」リンクをクリックし、精度をクリックします。

## 曜日レポートの実行 {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

期間を指定して、毎月曜日などの特定の曜日にレポートを実行する手順を説明します。

<!-- 

t_reports_day_of_week.xml

 -->

この機能は、週または日の日付範囲でフィルターされたトレンドレポートでのみ使用できます。

1. 指定した日付範囲でトレンドレポートを実行します。
1. 「**曜日**」リンクをクリックし、 曜日をクリックします。

## 「ワークスペースで試す」ボタン{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

レポートの上部にある「**[!UICONTROL ワークスペースで試す]」ボタンをクリックすると、同じレポートが Analysis Workspace に読み込まれます。**

<!-- 

try_in_workspace.xml

 -->

Reports &amp; Analytics のほとんどのレポートには現在、「ワークスペースで試す」ボタンがあります。このボタンを使用すると、現在のビューを Analysis Workspace で再現して、さらにカスタマイズすることができます。

現在、このボタンが使用できるのは、ユーザーに Analysis Workspace の完全な権限が付与されている場合のみです。

レポートをカスタマイズするすべての方法について詳しくは、[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) ガイドを参照してください。
