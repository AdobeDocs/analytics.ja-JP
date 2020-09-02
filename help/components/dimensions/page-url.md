---
title: ページ URL
description: ページの URL。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 64%

---


# ページ URL

「ページ URL」ディメンションは、サイト上の URL をリストします。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。他のAnalyticsソリューションでURLディメンションを使用する場合は、ヒットごとに [eVar](evar.md) に値をコピーすることを検討してください。

## このディメンションへのデータ入力

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [リンクトラッキングコール(`tl()`)](/help/implement/vars/functions/tl-method.md) 。 `g` クエリ文字列が存在する場合でも、常にこのディメンションを除去します。

URL が 255 バイトを超える場合があります。AppMeasurement は、イメージリクエストの URL の最初の 255 バイトに対して `g` クエリー文字列パラメーターを使用します。URL が 255 バイトを超える場合、残りの URL は `-g` クエリー文字列パラメーターに保存されます。URL 内のプロトコルとクエリー文字列がこの変数に含まれます。

AppMeasurementは、ページのURLに基づいてこのデータを自動的に収集します。 この [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用して、収集された値を上書きできます。

## eVar への URL の入力

eVar を連結された文字列 `window.location.hostname + window.location.pathname` に設定することをお勧めします。この文字列は、プロトコル、クエリ文字列、アンカータグを省略するので、通常、`window.location.href` 文字列よりも適切に動作します。

eVar を Data Warehouse の「ページ URL」ディメンションと完全に一致させる場合は、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、各ヒットに対して eVar を `D=g` に設定できます。

## Dimension項目

Dimension項目には、サイトのページのURLが含まれます。
