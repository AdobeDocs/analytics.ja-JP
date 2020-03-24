---
description: ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。 1つの変数に対して複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。
subtopic: Classifications
title: 分類ルールセット
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。 1つの変数に対して複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。 1つの変数に対して複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。

## Classification Rule Builder Page {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]**／**[!UICONTROL Admin]**／**[!UICONTROL Classification Rule Builder]**

では、次のフィールドとオプションを使用できま [!UICONTROL Classifications Rule Builder]す。

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  >ルールセットを追加</a>      </p> </td> 
   <td colname="col2"> <p>ルールセットを作成します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ルール </p> </td> 
   <td colname="col2"> セットに含まれるルールの数を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> ルールセットのアクティビティステータス（ドラフト、アクティブなど）を表示します。 アクティブなルールは毎日処理され、通常は1か月後に分類データを調べます。 ルールは、新しい値を自動的に確認し、分類をアップロードします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最後の変更 </p> </td> 
   <td colname="col2"> ルールセットがいつ編集されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複製 </p> </td> 
   <td colname="col2"> ルールセットを別の変数や異なるレポートスイートの同じ変数に適用できるように、ルールセットを複製（コピー）します。 </td> 
  </tr> 
 </tbody> 
</table>

## 分類ルールセットの作成 {#create-classification-rule-set}

分類ルールセットに名前を付け、変数を適用して、上書き設定を指定します。

1. （前提条件）>で分類構造を定義し **[!UICONTROL Admin]** ます **[!UICONTROL Report Suites]**。

   (分類の追加につ [いては](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) 、管理ツールヘルプの分類を参照してください)。

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   変数の分類は、/// **[!UICONTROL Admin]** (または/ **[!UICONTROL Report Suites]** ) **[!UICONTROL Traffic]** で作 **[!UICONTROL Traffic Classifications]** 成で **[!UICONTROL Conversion]** きます **[!UICONTROL Conversion Classifications]**。 Then select the variable, then click **[!UICONTROL Add Classification]**.

1. ルールセットを作成するには、//をク **[!UICONTROL Admin]** リック **[!UICONTROL Classification Rule Builder]** しま **[!UICONTROL Add Rule Set]**&#x200B;す。

   ![](assets/new_rule_set.png)

1. ルールセットに名前を付け、をクリックしま **[!UICONTROL Create Rule Set]**&#x200B;す。
1. 編集するルールセットを選択します。

   ![](assets/classification_rules_page.png)

1. クリック **[!UICONTROL Select Report Suites and Variables]**.

   レポートスイートと変数のリストには、ログインしている会社のすべてのレポートスイートで使用できるすべての分類された変数が入力されます。 レポートスイート内の1つの変数は、1つのルールセットにのみ属することができます。

   See *`Variable`* in the definitions for the [Classification Rule Builder](/help/components/c-classifications2/crb/classification-rule-definitions.md) page for more information.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. 引き続き、[分類ルールの追加](/help/components/c-classifications2/crb/classification-rule-set.md)をおこないます。
