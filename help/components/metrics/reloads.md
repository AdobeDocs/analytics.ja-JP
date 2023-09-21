---
title: リロード回数
description: ページがリロードされた回数。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 74%

---

# リロード回数

「リロード回数」 [指標](overview.md) 再読み込み中にディメンション項目が存在した回数を示します。 訪問者によるブラウザーの更新は、再読み込みをトリガーする最も一般的な方法です。

## この指標の計算方法

この指標は、[`Page`](../dimensions/page.md) ディメンションに前のヒットと同じ値が含まれるヒット数をカウントします。
