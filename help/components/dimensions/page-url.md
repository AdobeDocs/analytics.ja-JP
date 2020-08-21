---
title: ページ URL
description: ページの URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# ページ URL

「ページ URL」ディメンションは、サイト上の URL をリストします。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。他の Analytics ソリューションで URL ディメンションを使用する場合は、[eVar](evar.md) を使用します。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`g`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、[`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用してこのデータを収集します。

## eVar への URL の入力

eVar を連結された文字列 `window.location.hostname + window.location.pathname` に設定することをお勧めします。この文字列は、プロトコル、クエリ文字列、アンカータグを省略するので、通常、`window.location.href` 文字列よりも適切に動作します。

eVar を Data Warehouse の「ページ URL」ディメンションと完全に一致させる場合は、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、各ヒットに対して eVar を `D=g` に設定できます。すべての [`tl()`](/help/implement/vars/functions/tl-method.md) の呼び出しでページ URL が削除されるので、このメソッドは、カスタムリンクヒットに対しては動作しません。

## Dimension項目

Dimension項目には、サイトのページのURLが含まれます。
