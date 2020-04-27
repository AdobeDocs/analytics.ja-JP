---
description: フィルターを適用してパスレポートを作成する手順について説明します。
title: リクエストウィザードを使用したパスレポートのフィルタリング
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# リクエストウィザードを使用したパスレポートのフィルタリング

フィルターを適用してパスレポートを作成する手順について説明します。

この例では、サイトセクションのパスを使用します。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 適切なレポートスイートを選択します。
1. 左側のツリー表示で、//を **[!UICONTROL Paths]** 選択 **[!UICONTROL Site Sections]** します **[!UICONTROL Site Section Paths]**。

   ![](assets/site_section_path_1.png)

1. 適切な日付を指定します。
1. クリック **[!UICONTROL Next]**.
1. ウィザードの手順2の下のリン **[!UICONTROL Row Labels]**&#x200B;クをクリックし **[!UICONTROL Top 1-10 (pattern applied)]** ます。 パスレポートに、デフォルトでパターンが適用されます。

   ![](assets/site_section_path_2.png)

1. 「**[!UICONTROL Filter]**」オプションを選択します。

   ![](assets/filter_option.png)

1. このダイ **[!UICONTROL Define 'Site Section Paths' Path Pattern]** アログで、
   1. レポートに表示を開始するランク
   1. レポートに表示するエントリ数
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. 利用可能なパターンは次のとおりです。

   ![](assets/select_a_pattern.png)

   これらのパターンのうち、入口の次、出口の前、次のアイテムの各パターンは、Report Builder に固有のパターンです。
1. 事前定義済みのパターンを編集するには：
   1. パターンを選択します。例えば、次を選択しま **[!UICONTROL Exited Site Pattern]**&#x200B;す。 ![](assets/exited_site_pattern.png)

   1. ユーザーが離脱する直前のサイトセクションを定義するため、クリック **[!UICONTROL Specific Item(s): 0 selected]**. セルの範囲から選択するか（既存のリクエストを編集している場合）、またはセクションのリストから選択して、このパスを定義できます。
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. その後、レポートからセルを選択します。![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. クリック **[!UICONTROL OK]**。 ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. Click **[!UICONTROL OK]** three times and then click **[!UICONTROL Finish]**. フィルターが適用されたパスリクエストが生成されます。
