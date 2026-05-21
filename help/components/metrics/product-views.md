---
title: 製品表示
description: 製品ページへの表示数。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
TQID: https://experienceleague.adobe.com/bspBkiEAfkwBQwWV3-KoDKDRNGLogCKkSXvY2Cpyv-M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 80
ht-degree: 72%

---

# 製品表示

「製品ビュー」 [指標](overview.md)には、製品が閲覧された回数が表示されます。 この指標は、最も多く閲覧された製品を表示したり、全体の製品表示の経時的なトレンドを確認したりする場合に役立ちます。

## この指標の計算方法

この指標では、次の&#x200B;**いずれかに**&#x200B;一致するヒット数をカウントします。

* `prodView` の値は [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在する、または
* [`products`](/help/implement/vars/page-vars/products.md)変数が設定され、`events`変数が空です。
