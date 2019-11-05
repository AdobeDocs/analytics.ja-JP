---
description: ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。
seo-description: ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。
seo-title: 分類ルールセット
solution: Analytics
subtopic: 分類
title: 分類ルールセット
topic: 管理ツール
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールセット

ルールセットは、特定の変数の分類ルールのグループです。変数をルールセットに適用します。1 つの変数に対して複数のルールセットを作成するには、それぞれのルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールビルダーページ {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** /管理 **[!UICONTROL 者]** /分 **[!UICONTROL 類ルールビルダー]**

[!UICONTROL 分類ルールビルダー]には、次のフィールドとオプションがあります。

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

## Create a Classification Rule Set {#create-classification-rule-set}

<!-- 

t_classification_rule_set.xml

 -->

分類ルールセットに名前を付け、変数を適用して、上書き設定を指定します。

1. (Prerequisite) Define the classification structure in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

   （分類の追加については、管理ツールのヘルプの[分類](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)を参照してください。）

   変数は、その変数に対して 1 つ以上の分類が定義されている場合にのみ[!UICONTROL 新しいルールセット]パネルに表示されます。

   You can create classifications on a variable in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Traffic]** &gt; **[!UICONTROL Traffic Classifications]** (or **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**). Then select the variable, then click **[!UICONTROL Add Classification]**.

1. To create the rule set, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]** &gt; **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Name the rule set, then click **[!UICONTROL Create Rule Set]**.
1. 編集するルールセットを選択します。

   ![](assets/classification_rules_page.png)

1. Click **[!UICONTROL Select Report Suites and Variables]**.

   レポートスイートと変数リストには、ログインしている会社のすべてのレポートスイートで利用できるすべての分類された変数が入力されます。レポートスイート内の 1 つの変数が所属することのできるルールセットは、1 つのみです。

   詳しくは、*`Variable`*（[分類ルールビルダー](/help/components/c-classifications2/crb/classification-rule-definitions.md)ページの定義）を参照してください。
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Continue by [adding classification rules](/help/components/c-classifications2/crb/classification-rule-set.md) to the rule set.
