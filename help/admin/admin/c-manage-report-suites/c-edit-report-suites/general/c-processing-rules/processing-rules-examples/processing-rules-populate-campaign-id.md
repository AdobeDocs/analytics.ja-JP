---
description: クエリ文字列パラメーターを使用して、変数を入力することができます。
subtopic: Processing rules
title: クエリ文字列パラメーターからのキャンペーン ID の入力
feature: Admin Tools
role: Admin
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%

---

# クエリ文字列パラメーターからのキャンペーン ID の入力

クエリ文字列パラメーターを使用して、変数を入力することができます。

ほとんどの場合、クエリ文字列からの変数の入力にはプラグインを使用します。入力ミスなどの問題によって値を入力できない場合、処理ルールを使用して変数を入力できます。

値を上書きする前に、値が空白であるか、期待された値が含まれているかを必ず確認する必要があります。

| ルールセット | 値 |
|---|---|
| 条件 | キャンペーンが設定されていない |
| アクション | キャンペーンの値を上書きしてクエリ文字列パラメーター cpid の値に設定する |

次に例を示します。

![](assets/set-campaign-conditionally.png)
