---
title: ページイベント
description: トリガーされたリンクトラッキングアクションの数。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 33%

---

# ページイベント

「ページイベント」 [指標](overview.md) は、リンクトラッキングコールがおこなわれた回数を示します。 この指標は、どのページが最も魅力的なコンテンツを持つかを把握する場合に役立ちます。この指標の測定は、訪問者が新しいページに移動せずにページ上でアクションを実行できる場合に最も役立ちます。

例えば、e コマースサイトの一般的なジャーニーでは、訪問者は 1 つのページで複数のインタラクションを持つことができます。 一般的な Analytics の実装では、これらのインタラクションがリンクトラッキング ([`tl()`](/help/implement/vars/functions/tl-method.md)) 呼び出しを呼び出し、ページビュー ([`t()`](/help/implement/vars/functions/t-method.md)) 呼び出しは、最初のページ読み込み用に予約されています。 この実装方法は、訪問者のジャーニーが継続する前に発生したインタラクションに関するインサイトを提供する、エンリッチメントされたイベントトラッキングを提供します。

## この指標の計算方法

この指標は、レポートスイート内のすべてのリンクトラッキングコール（[`tl()`](/help/implement/vars/functions/tl-method.md)）をカウントします。この指標には、特にすべてのリンクタイプが含まれます [カスタムリンク](../dimensions/custom-link.md), [ダウンロードリンク](../dimensions/download-link.md)、および [出口リンク](../dimensions/exit-link.md). ページビュー呼び出し ([`t()`](/help/implement/vars/functions/t-method.md)) をクリックします。

## 類似の指標と比較

* **ページイベントと [ページビュー数](page-views.md)**：ページイベントは、リンクトラッキングコール数 ([`tl()`](/help/implement/vars/functions/tl-method.md)) とページビュートラッキングコール ([`t()`](/help/implement/vars/functions/t-method.md)) をクリックします。 ページビューは逆で、ページビュートラッキングコール数をカウントし、リンクを除外します。
