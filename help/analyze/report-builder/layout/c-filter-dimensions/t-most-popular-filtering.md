---
description: Boolean ロジックと AND／OR 検索式を使用して設定する、ランキングおよび条件フィルター。
title: 最頻使用フィルター
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最頻使用フィルター

Boolean ロジックと AND／OR 検索式を使用して設定する、ランキングおよび条件フィルター。

最頻使用フィルターは、BooleanロジックとAND/OR条件（条件や、、などの条件のグループなど）を使用して設定する式 [!UICONTROL Page does not contain]*`<product name>`* フィルター [!UICONTROL Includes All]です [!UICONTROL Includes Any][!UICONTROL Excludes All]。 現在のワークブックや他のワークブックで使用する他のリクエスト用に、これらの式を[保存](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md)することができます。

**最頻使用フィルターを作成するには**

1. リクエストを作成または編集し、に進みま [!UICONTROL Request Wizard: Step 2]す。

   ![ステップ情報](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. フォーム上 [!UICONTROL Choose Page] でを有効に **[!UICONTROL Most Popular]**&#x200B;し、次のオプションを設定します。

   **開始ランク：**&#x200B;ディメンションの表示開始位置です。デフォルトのランクである「1」は、レポートされるデータのリストの最上位項目を示します。For example, for the dimension [!UICONTROL Page], a starting mark of 1 indicates the single most requested page of your site. 開始ランクセルには 10 などの他の値を指定することもできます。これにより、「10」位以降の項目が表示されます。指標は降順に並べられます。このため、最大のアクティビティがある行項目が、リストの最初に表示されます。最大行数である 50,000 を超える項目を取得したい場合は、リクエストをコピーして開始ランクを変更することで、50,000 の単位で大量のデータを取得することができます。

   **エントリ数：** (の [!UICONTROL Pivot Layout] み)特定の指標に関して、日付範囲でレポートされる項目数を定義します。 1 つの指標に対して何百ものエントリを表示する指標もあれば、数個のエントリのみを表示する指標もあります。For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   矢印を使用すると、シート内の最 [!UICONTROL Starting Rank] 初のデ [!UICONTROL Number of Entries] ータポイントのおよびを変更できます。 デフォルトでは、は1 [!UICONTROL Starting Rank] に、は10に設定さ [!UICONTROL Number of Entries] れています。 これらの値は、最小 1、最大 50,000 の間で調整できます。各指標の上限はそれぞれ異なりま [!UICONTROL Number of Entries]す。 負の数やゼロをこれらのフィールドに入力することはできません。If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. つまり、最も訪問されたページの上位 15 位から 25 位までにランクされたすべてのページが、降順で表示されます。

   >[!NOTE]
   >
   >既存のリクエストにフィルターを適用すると、表示されているデータが変更されます。上位10位のセルを$A$1 ～ $A$10 [!UICONTROL Pages] のセルにマッピングし、1をforに、1をforに [!UICONTROL Starting Rank] 10をforに設定したとします [!UICONTROL Number of Entries]。 If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![ステップ情報](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_cell_icon.png](assets/select_cell_icon.png) をクリックすると、セルの値に定義された条件が示されます。

   **条件を追加：**&#x200B;式に条件を追加します。追加できる条件の数に制限はありません。

1. クリック **[!UICONTROL OK]**.

   ![ステップ情報](assets/choose_page_02.png)

1. フォーム上 [!UICONTROL Choose Page] でをクリックし、 **[!UICONTROL Save]** 式を保存します。
1. クリック **[!UICONTROL OK]**.
