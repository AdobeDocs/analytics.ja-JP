---
title: 製品表示
description: 製品ページへの表示数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '94'
ht-degree: 100%

---

# 製品表示

「製品表示」指標は、製品が表示された回数を示します。この指標は、最も多く閲覧された製品を表示したり、全体の製品表示の経時的なトレンドを確認したりする場合に役立ちます。

## この指標の計算方法

この指標では、次の&#x200B;**いずれかに**&#x200B;一致するヒット数をカウントします。

* `prodView` の値は [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在する、または
* [`products`](/help/implement/vars/page-vars/products.md) 変数が設定され、`events` 変数に買い物かごイベントが存在しない。カスタム（`event1` - `event1000`）以外のイベントは買い物かごイベントです。
