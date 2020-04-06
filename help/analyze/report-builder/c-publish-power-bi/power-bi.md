---
description: 'null'
title: Power BI への発行 - 概要
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Power BI への発行 - 概要

Microsoft Power BIは、データを分析し、インサイトを共有するビジネス分析ダッシュボードのスイートです。 Adobe AnalyticsとPower BIの統合により、Report Builder AnalyticsのデータをMicrosoft Power BI内で視覚化し、組織全体で簡単に共有できます。

以前は、アナリストとして、電子メール（またはftp）を使用してReport Builderのワークブックを配布するようにスケジュールしていました。 ビジネスユーザーの利害関係者に、（Power BIアカウント内から）プラットフォームやデバイス間でアクセス可能な、Webベースの環境内の正確で最新のデータにアクセスできるようになりました。

Report Builderのレポート生成機能とPower BIのビジュアライゼーション機能を組み合わせると、組織の全員が情報にアクセスしやすくなります。 Power BIを使用すると、Adobe Analyticsを他のデータソース（販売時点、CRMなど）と統合して、一意の顧客インサイト、関連性およびオポチュニティを見つけることもできます。

![](assets/aaplusbi.png)

Adobe Report Builderとの統合により、

* [スケジュールされた Report Builder ワークブックを Power BI に発行する](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [ワークブック内のすべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行する](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [すべての Report Builder リクエストを Power BI データセットテーブルとして発行する](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## 必要システム構成 {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 が[インストールされている](/help/analyze/report-builder/setup/t-install-arb.md)
* Power BI にログインできるアクティブな Microsoft アカウント

## ワークブックを Power BI に発行する {#section_21CA66229EC240D49594A9A7D3FBA687}

スケジュールされたワークブックは、Adobe Analytics のデータが取り込まれた、フォーマット済みの Excel スプレッドシートです。スケジュールに従って定期的に送信されます。

**Report Builder でのワークブックの発行**

1. Report Builderで、ワークブックを生成し、保存します。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 基本スケジュールウィザードで、の横のチェックボックスをオンにしま **[!UICONTROL Publish Workbook to Microsoft Power BI]**&#x200B;す。

   ![](assets/simple-schedule-wizard.png)

1. 電子メールを指定して即座に送信するか、スケジュールの頻度（時間別、日別など）を指定します。
1. をクリッ **[!UICONTROL OK]** クして投稿します。
1. これで、Microsoftアカウントにログインするように求められます。 資格情報を入力します。
1. Report Builderワークブックがスケジュールされ、Power BIに発行されます。

   各スケジュール済みインスタンスで、Report Builderのスケジュールプロセスで更新されたAnalyticsデータを使用してワークブックを更新した後、ワークブックはMicrosoft Power BIに発行されます。

**Power BI での Report Builder のワークブックデータの表示**

1. Power BIで、重複メニューの下のワークブックをクリック [!UICONTROL Workbooks] します。

   ![](assets/workbooks-power-bi.png)

1. これで、ワークブックのダッシュボードデータを表示できるようになります。    ![](assets/view-data-pbi.png)

1. このワークブックの領域をピン留めして任意の Power BI ダッシュボードに追加することができます。

## ワークブック内のすべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行する {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] ワークブックにマクロが含まれている場合、「すべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行」は無効になります。

ブック全体をインポートする代わりに、ブック内の形式設定されたすべてのテーブルの内容のみをインポートできます。

**使用例**:複数のReport Builderリクエストからデータを取り込み、多数の数式を含む概要表を作成するExcelワークブックがある。 概要テーブルのみをPower BIに読み込んで、そのビジュアライゼーションを作成できます。

**Report Builder でのフォーマット済みテーブルの発行**

1. Report Builder で、ヘッダー行とそれに続くデータ行を含むデータテーブルを生成します。
1. テーブルを選択し、メニュー **[!UICONTROL Format as Table]** からを選択 [!UICONTROL Home] します。 The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 基本スケジュールウィザードで、をクリックしま **[!UICONTROL Advanced Scheduling Options]**&#x200B;す。
1. のタブ [!UICONTROL Scheduling Wizard - Advanced]で、の横のボッ **[!UICONTROL Publishing Options]** クスをオンにします **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**。

   ![](assets/advanced-schedule-wizard2.png)

1. （オプション）Power BIで公開済みアセットの名前をカスタマイズできます。 これは、バージョン管理をワークブック名の一部（myworkbook_v1.1.xlsxなど）として使用し、発行されたPower BIアセットの名前にバージョン番号を表示しない場合に便利です。 バージョン番号が変更されても、発行済みのアセットは変更されないという利点があります。 (表示 [の仕様は](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) 、ここを参照)。

**Power BI でのテーブルデータの表示**

1. Power BIで、/メニューに移 **[!UICONTROL Workspaces]** 動し **[!UICONTROL Datasets]** ます。

   ![](assets/datasets-menu.png)

1. 公開したデータセットを選択し、横のアイコ [!UICONTROL Create report] ンをクリックします。 テーブルがフィールドとして表示されます。

   ![](assets/formatted-tables.png)

1. テーブルと関連する列を選択します。

   ![](assets/view-table-dataset.png)

1. Power BIのテ [!UICONTROL Visualizations] ーブルの視覚化方法をメニューから選択できます。 例えば、データを折れ線グラフとして表示するように選択できます。

   ![](assets/bi-line-graph.png)

1. ここから、このデータセットテーブルからビジュアライゼーションを作成できます。

## すべての Report Builder リクエストを Power BI データセットテーブルとして発行する {#section_0C26057C7DBB4068A643FDD688F6E463}

すべてのリクエストをデータセットテーブルに変換し、その上にビジュアライゼーションを作成することができます。

>[!IMPORTANT]
>
>ワークブックに 100 を超えるリクエストが含まれている場合、Power BI に発行されるのは最初の 100 件のリクエストのみです。さらに、Power BIに発行される各リクエストに対して、最初の10,000行のデータのみが発行されます。 したがって、これらの要求はスケジュールを通じて正常に配信されますが、Power BIへの投稿の範囲は限られます。

1. Report Builderで、Report Builderリクエストを含むワークブックを開くか、作成します。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. 基本スケジュールウィザードで、をクリックしま **[!UICONTROL Advanced Scheduling Options]**&#x200B;す。
1. のタブ [!UICONTROL Scheduling Wizard - Advanced]で、の横のボ **[!UICONTROL Publishing Options]** ックスをオンにします **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. クリック **[!UICONTROL OK]**.

**Power BI でのリクエストデータの表示**

各予定されたReport Builderリクエストは、データセット内の表として発行されます。 各リクエストテーブルには、リクエスト内のプライマリディメンションにちなんで名前が付けられ、1つの列 [!UICONTROL Report Suite] と1つが含ま [!UICONTROL Segments] れます。

1. Power BIで、/メニューに移 **[!UICONTROL Workspaces]** 動し **[!UICONTROL Datasets]** ます。

1. 公開したリクエストを選択し、横のアイコン [!UICONTROL Create report] をクリックします。

   リクエストがテーブルとしてメニューに表示され [!UICONTROL Fields] ます。

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >ワークシートで Report Builder リクエストのレイアウトをどのように設定しても（ピボットレイアウト、カスタムレイアウト、一部の列を非表示）、リクエストは同じ 2 次元の単一ヘッダー行形式（日付、ディメンション、指標、レポートスイート、セグメント）で常に発行されます。

1. また、という別の表があります **[!UICONTROL Legend]**。 Report Builderのコンテキストからリクエストを取り出すと、各リクエストの意味を覚えにくくなる場合があります。 凡例テーブルの目的は、例えば、テーブルIDの下に各リクエストの名前を表示することです。 その他の凡例列を追加して、リクエストの完全な表示を取得することもできます。

   ![](assets/legend-table.png)

