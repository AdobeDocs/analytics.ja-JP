---
title: ページ URL
description: ページの URL。
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 95%

---

# ページ URL

「ページ URL」 [ ディメンション ](overview.md)には、サイト上のURLが一覧表示されます。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。 他の Analytics ソリューションで URL ディメンションを使用する場合は、ヒットごとに [eVar](evar.md) に値をコピーすることを検討してください。

## このディメンションへのデータ入力

このディメンションは、[ページビュー呼び出し（`t()`）](/help/implement/vars/functions/t-method.md) の [`g` および `-g` のクエリ文字列 ](/help/implement/validate/query-parameters.md) からデータを取得します。 [リンクトラッキング呼び出し（`tl()`）](/help/implement/vars/functions/tl-method.md) は、 `g` クエリ文字列が存在する場合でも、常にこのディメンションを取り除きます。

URL が 255 バイトを超える場合があります。 AppMeasurement は、イメージリクエストの URL の最初の 255 バイトに対して `g` クエリ文字列パラメーターを使用します。 URL が 255 バイトを超える場合、残りの URL は `-g` クエリ文字列パラメーターに保存されます。 URL 内のプロトコルとクエリ文字列がこの変数に含まれます。

AppMeasurement は、ページの URL に基づいてこのデータを自動的に収集します。 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 変数を使用して、収集された値を上書きできます。

## eVar への URL の入力

eVar を連結された文字列 `window.location.hostname + window.location.pathname` に設定することをお勧めします。 この文字列は、プロトコル、クエリ文字列、アンカータグを省略するので、通常、`window.location.href` 文字列よりも適切に動作します。

eVar を Data Warehouse の「ページ URL」ディメンションと完全に一致させる場合は、[動的変数](/help/implement/vars/page-vars/dynamic-variables.md)を使用して、各ヒットに対して eVar を `D=g` に設定できます。

## ディメンション項目

ディメンション項目には、サイトのページの URL が含まれます。
