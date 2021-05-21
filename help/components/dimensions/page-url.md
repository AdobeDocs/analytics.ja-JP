---
title: ページ URL
description: ページの URL。
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# ページ URL

「ページ URL」ディメンションは、サイト上の URL をリストします。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。他の Analytics ソリューションで URL ディメンションを使用する場合は、ヒットごとに [eVar](evar.md) に値をコピーすることを検討してください。

## このディメンションへのデータ入力

このディメンションは、[ページビュー呼び出し（`t()`）](/help/implement/vars/functions/t-method.md) の [`g` および `-g` のクエリ文字列 ](/help/implement/validate/query-parameters.md) からデータを取得します。 [リンクトラッキング呼び出し（`tl()`）](/help/implement/vars/functions/tl-method.md) は、 `g` クエリ文字列が存在する場合でも、常にこのディメンションを取り除きます。

URL が 255 バイトを超える場合があります。AppMeasurement は、イメージリクエストの URL の最初の 255 バイトに対して `g` クエリー文字列パラメーターを使用します。URL が 255 バイトを超える場合、残りの URL は `-g` クエリー文字列パラメーターに保存されます。URL 内のプロトコルとクエリー文字列がこの変数に含まれます。

AppMeasurement は、ページの URL に基づいてこのデータを自動的に収集します。 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用して、収集された値を上書きできます。

## eVar への URL の入力

eVar を連結された文字列 `window.location.hostname + window.location.pathname` に設定することをお勧めします。この文字列は、プロトコル、クエリ文字列、アンカータグを省略するので、通常、`window.location.href` 文字列よりも適切に動作します。

eVar を Data Warehouse の「ページ URL」ディメンションと完全に一致させる場合は、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、各ヒットに対して eVar を `D=g` に設定できます。

## ディメンション項目

ディメンション項目には、サイトのページの URL が含まれます。
