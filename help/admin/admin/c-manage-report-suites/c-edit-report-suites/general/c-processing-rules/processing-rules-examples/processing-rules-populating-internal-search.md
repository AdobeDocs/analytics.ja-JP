---
description: q などの一般的な変数を使用して検索用語を入力する場合、処理ルールを使用して内部検索用語 eVar にこのような変数の値を入力できます。
subtopic: Processing rules
title: クエリ文字列パラメーターを使用して内部検索用語を入力
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# クエリ文字列パラメーターを使用して内部検索用語を入力

q などの一般的な変数を使用して検索用語を入力する場合、処理ルールを使用して内部検索用語 eVar にこのような変数の値を入力できます。

処理ルールで読み取れるように、クエリ文字列値を Unicode または UTF-8 でエンコードする必要があります。

| ルールセット | 値 |
|---|---|
| 条件 | クエリ文字列パラメーター q が設定されている場合 |
| アクション | 内部検索用語の値を上書きしてクエリ文字列パラメーター q の値に設定する |

次に例を示します。

![](assets/populate-internal-search-terms.png)
