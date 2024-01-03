---
title: ページイベント
description: トリガーされたリンクトラッキングアクションの数。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: a7434f72159a575f9ad7bf29644cb17777382df7
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 40%

---

# ページイベント

「ページイベント」 [指標](overview.md) は、リンクトラッキングコールがおこなわれた回数を示します。 この指標は、どのページが最も魅力的なコンテンツを持つかを把握する場合に役立ちます。この指標の測定は、訪問者が新しいページに移動せずにページ上でアクションを実行できる場合に最も役立ちます。

## この指標の計算方法

この指標ではすべてをカウントします [リンクトラッキングコール (`tl()`)](/help/implement/vars/functions/tl-method.md) 」と表示されます。 この指標には、特にすべてのリンクタイプが含まれます [カスタムリンク](../dimensions/custom-link.md), [ダウンロードリンク](../dimensions/download-link.md)、および [出口リンク](../dimensions/exit-link.md). 次を含みません。 [ページビュートラッキングコール (`t()`)](/help/implement/vars/functions/t-method.md).

## 類似の指標と比較

* **ページイベントと [ページビュー数](page-views.md)**：ページイベントは、リンクトラッキングコール数 (`tl()`) とページビュートラッキングコール (`t()`) をクリックします。 ページビューは逆で、ページビュートラッキングコール数をカウントし、リンクを除外します。
