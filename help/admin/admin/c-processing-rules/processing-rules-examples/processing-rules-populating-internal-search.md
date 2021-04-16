---
description: q などの一般的な変数を使用して検索用語を入力する場合、処理ルールを使用して内部検索用語 eVar にこのような変数の値を入力できます。
subtopic: Processing rules
title: クエリー文字列パラメーターを使用して内部検索用語を入力
feature: 管理ツール
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 100%

---

# クエリー文字列パラメーターを使用して内部検索用語を入力

q などの一般的な変数を使用して検索用語を入力する場合、処理ルールを使用して内部検索用語 eVar にこのような変数の値を入力できます。

処理ルールで読み取れるように、クエリー文字列値を Unicode または UTF-8 でエンコードする必要があります。

| ルールセット | 値 |
|---|---|
| 条件 | クエリー文字列パラメーター q が設定されている場合 |
| アクション | 内部検索用語の値を上書きしてクエリー文字列パラメーター q の値に設定する |

次に例を示します。

![](assets/populate-internal-search-terms.png)
