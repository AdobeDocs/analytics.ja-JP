---
title: 分類セットルール
description: 分類セットのルールを表示および編集する方法について説明します。
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 5%

---

# 分類セットルール

>[!IMPORTANT]
>
>分類セットは、まだルールをサポートしていません。 従来のルールビルダー機能が使用できなくなる前に、ルール機能が分類セットインターフェイスに追加されます。
>>分類にルールが必要な場合は、引き続き [ 分類ルールビルダー ](/help/components/classifications/crb/classification-rule-builder.md) を使用します。


<!--
Classification set rules allow you to automatically classify values based on the value that the variable is set to. These rules apply to all incoming variable values for all subscriptions of the classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired classification set name > **[!UICONTROL Rules]**

![classification set rules UI](../../assets/csets-rules.png)

## Rule settings

Settings that apply to the entire set of rules.

* **[!UICONTROL Rules overwrite]**: Determines the behavior of all rules in cases where a classification value exists.
  * **[!UICONTROL Apply to all values]**: If a rule matches, always overwrite the classification value.
  * **[!UICONTROL Apply only to unset values]**: If a rule matches, only write the classification value if it is blank. If a classification value exists, do nothing.
* **[!UICONTROL Lookback window]**: When this rule is activated, all rules run against all unique values seen within the lookback window set here.

## Rules

A list of rules that run for each unique value.

* **[!UICONTROL Search]**: A search box that allows you to filter rules by match criteria.
* **[!UICONTROL Add rule]**: Adds a blank row to the rule table.
* **[!UICONTROL Test rule set]**: Brings up a test UI that allows you to validate your rules. On the left, you can manually type key values, or you can drag and drop a classification file to import many values to test against. On the right is a table that shows preliminary results of what classified values would look like if the rule set was activated. Since this interface is only for validation, no values are classified.

Select one or more rules by clicking the checkbox next to the desired rule. Selecting a rule reveals the following options:

* **[!UICONTROL Delete]**: Deletes the row from the rule table.
* **[!UICONTROL Duplicate]**: Copies the selected rows to new rows in the rule table.

## Rule table

The rule table is separated vertically into two main parts: matching condition and classification action. Each row (an individual rule) contains a matching condition and a classification action.

* **Rule number**: Rules run in the same order that you configure the rule table. If [!UICONTROL Rules overwrite] is set to [!UICONTROL Apply to all values], the last matching rule overwrites any previous rules for the same classification dimension. If [!UICONTROL Rules overwrite] is set to [!UICONTROL Apply to only unset values], the first rule that sets a classification value applies.
* **[!UICONTROL Select rule type]**: The rule criteria. Options include [!UICONTROL Contains], [!UICONTROL Ends with], [!UICONTROL Regular expression], [!UICONTROL Regular expression], and [!UICONTROL Starts with].
* **[!UICONTROL Enter match criteria]**: The text string to match. If you select [!UICONTROL Regular expression] as the rule type, an overlay appears that lets you enter the value, test the regular expression, and provides sample syntax.
* **[!UICONTROL Set classification]**: A drop-down list that sets the classification dimension that you want to assign a value to. Valid options include elements in your [schema](schema.md).
* **[!UICONTROL To]**: The text string to set the classified value to. If the rule type is [!UICONTROL Regular expression], you can include a combination of text and match groups.

-->