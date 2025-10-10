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

「ページイベント [&#x200B; 指標 &#x200B;](overview.md) は、リンクトラッキングコールが行われた回数を示します。 この指標は、どのページが最も魅力的なコンテンツを持つかを把握する場合に役立ちます。この指標の測定は、訪問者が新しいページに移動せずにページ上でアクションを実行できる場合に最も役立ちます。

例えば、e コマースサイトの一般的なジャーニーでは、訪問者は 1 ページで複数のインタラクションを持つことができます。 一般的な Analytics 実装では、これらのインタラクションはリンクトラッキング（[`tl()`](/help/implement/vars/functions/tl-method.md)）呼び出しとして設定されますが、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）呼び出しは最初のページ読み込み用に予約されます。 この実装方法は、訪問者がジャーニーを続ける前にどのようなインタラクションが起こったかについてinsightに提供する、エンリッチメントされたイベントトラッキングを提供します。

## この指標の計算方法

この指標は、レポートスイート内のすべてのリンクトラッキングコール（[`tl()`](/help/implement/vars/functions/tl-method.md)）をカウントします。この指標には、すべてのリンクタイプ、特に [&#x200B; カスタムリンク &#x200B;](../dimensions/custom-link.md)、[&#x200B; ダウンロードリンク &#x200B;](../dimensions/download-link.md)、および [&#x200B; 離脱リンク &#x200B;](../dimensions/exit-link.md) が含まれます。 ページビューコール（[`t()`](/help/implement/vars/functions/t-method.md)）は含まれません。

## 類似の指標と比較

* **ページイベントと [&#x200B; ページビュー](page-views.md)**：ページイベントは、リンクトラッキングコールの数（[`tl()`](/help/implement/vars/functions/tl-method.md)）をカウントし、ページビュートラッキングコールを除外（[`t()`](/help/implement/vars/functions/t-method.md)）します。 ページビュー数は逆で、ページビュートラッキングコールの数をカウントし、リンクを除外します。
