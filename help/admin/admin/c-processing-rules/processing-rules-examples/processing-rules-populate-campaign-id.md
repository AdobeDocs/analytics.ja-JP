---
description: クエリー文字列パラメーターを使用して、変数を入力することができます。
subtopic: Processing rules
title: クエリー文字列パラメーターからのキャンペーン ID の入力
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 100%

---

# クエリー文字列パラメーターからのキャンペーン ID の入力

クエリー文字列パラメーターを使用して、変数を入力することができます。

ほとんどの場合、クエリー文字列からの変数の入力にはプラグインを使用します。入力ミスなどの問題によって値を入力できない場合、処理ルールを使用して変数を入力できます。

値を上書きする前に、値が空白であるか、期待された値が含まれているかを必ず確認する必要があります。

| ルールセット | 値 |
|---|---|
| 条件 | キャンペーンが設定されていない |
| アクション | キャンペーンの値を上書きしてクエリー文字列パラメーター cpid の値に設定する |

次に例を示します。

![](assets/set-campaign-conditionally.png)
