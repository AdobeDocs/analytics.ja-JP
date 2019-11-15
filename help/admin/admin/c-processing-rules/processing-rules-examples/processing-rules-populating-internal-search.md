---
description: q などの一般的な変数を使用して検索用語を入力する場合、処理ルールを使用して内部検索用語 eVar にこのような変数の値を入力できます。
solution: Analytics
subtopic: Processing rules
title: クエリ文字列パラメーターを使用して内部検索用語を入力
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

