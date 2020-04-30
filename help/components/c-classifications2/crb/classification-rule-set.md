---
description: ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。
subtopic: Classifications
title: 分類ルールセット
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールビルダーページ {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]**／**[!UICONTROL Admin]**／**[!UICONTROL Classification Rule Builder]**

The following fields and options are available on the [!UICONTROL Classifications Rule Builder].

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
   <td colname="col2"> ルールセットのアクティビティステータス（ドラフト、アクティブなど）を表示します。アクティブなルールは毎日処理され、通常、分類データの調査は月に 1 回行われます。ルールでは、自動的に新しい値がチェックされ、分類がアップロードされます。 </td> 
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

   （分類の追加については、管理ツールのヘルプの[分類](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html)を参照してください。）

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   変数の分類は、/// **[!UICONTROL Admin]** (または/ **[!UICONTROL Report Suites]** ) **[!UICONTROL Traffic]** で作 **[!UICONTROL Traffic Classifications]** 成で **[!UICONTROL Conversion]** きます **[!UICONTROL Conversion Classifications]**。 Then select the variable, then click **[!UICONTROL Add Classification]**.

1. To create the rule set, click **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. ルールセットに名前を付け、をクリックしま **[!UICONTROL Create Rule Set]**&#x200B;す。
1. 編集するルールセットを選択します。

   ![](assets/classification_rules_page.png)

1. クリック **[!UICONTROL Select Report Suites and Variables]**.

   レポートスイートと変数リストには、ログインしている会社のすべてのレポートスイートで利用できるすべての分類された変数が入力されます。レポートスイート内の 1 つの変数が所属することのできるルールセットは、1 つのみです。

   詳しくは、*`Variable`*（[分類ルールビルダー](/help/components/c-classifications2/crb/classification-rule-definitions.md)ページの定義）を参照してください。
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. 引き続き、[分類ルールの追加](/help/components/c-classifications2/crb/classification-rule-set.md)をおこないます。
