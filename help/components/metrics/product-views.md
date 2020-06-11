---
title: 製品表示
description: 商品ページへの表示数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# 製品表示

「製品表示」指標は、製品が表示された回数を示します。 この指標は、最も多く閲覧された商品を表示したり、全体の商品表示の経時的なトレンドを確認したりする場合に役立ちます。

## この指標の計算方法

この指標では、次のい **ずれかに一致するヒット数をカウントします** 。

* この値 `prodView` は変数に存在し [`events`](/help/implement/vars/page-vars/events/events-overview.md) ます。 または
* 変数が設定され、その変数に買い物かごイベントが存在しな [`products`](/help/implement/vars/page-vars/products.md)`events` い。 カスタム(`event1` - `event1000`)以外のイベントは買い物かごイベントです。