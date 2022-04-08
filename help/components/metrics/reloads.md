---
title: リロード回数
description: ページがリロードされた回数。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '63'
ht-degree: 100%

---

# リロード回数

「リロード回数」指標は、再読み込み中にディメンション項目が存在した回数を示します。訪問者によるブラウザーの更新は、再読み込みをトリガーする最も一般的な方法です。

## この指標の計算方法

この指標は、[`Page`](../dimensions/page.md) ディメンションに前のヒットと同じ値が含まれるヒット数をカウントします。
