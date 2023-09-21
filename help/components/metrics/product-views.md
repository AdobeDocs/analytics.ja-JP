---
title: 製品表示
description: 製品ページへの表示数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 72%

---

# 製品表示

「製品表示」 [指標](overview.md) 製品が表示された回数を示します。 この指標は、最も多く閲覧された製品を表示したり、全体の製品表示の経時的なトレンドを確認したりする場合に役立ちます。

## この指標の計算方法

この指標では、次の&#x200B;**いずれかに**&#x200B;一致するヒット数をカウントします。

* `prodView` の値は [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在する、または
* The [`products`](/help/implement/vars/page-vars/products.md) 変数が設定され、 `events` 変数が空です。
