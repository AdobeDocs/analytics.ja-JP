---
title: ページイベント
description: トリガーされたリンクトラッキングアクションの数。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
TQID: https://experienceleague.adobe.com/tOEidVQjv4ynokjH53SEdKeOHiqwZn02WZDalUESsAs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 33%

---

# ページイベント

「ページイベント」 [指標](overview.md)は、リンクトラッキング呼び出しが行われた回数を示します。 この指標は、どのページが最も魅力的なコンテンツを持つかを把握する場合に役立ちます。 この指標の測定は、訪問者が新しいページに移動せずにページ上でアクションを実行できる場合に最も役立ちます。

例えば、コマースサイトの典型的なジャーニーでは、訪問者は1つのページで複数のやり取りを体験できます。 一般的なAnalyticsの実装では、これらのインタラクションがリンクトラッキング（[`tl()`](/help/implement/vars/functions/tl-method.md)）呼び出しとして設定されていますが、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）呼び出しは最初のページ読み込み用に予約されています。 この実装方法は、訪問者がジャーニーを続ける前に何が起こるかをinsightに示す、強化されたイベントトラッキングを提供します。

## この指標の計算方法

この指標は、レポートスイート内のすべてのリンクトラッキングコール（[`tl()`](/help/implement/vars/functions/tl-method.md)）をカウントします。 すべてのリンクタイプがこの指標に含まれており、特に[ カスタムリンク ](../dimensions/custom-link.md)、[ ダウンロードリンク ](../dimensions/download-link.md)、[終了リンク ](../dimensions/exit-link.md)です。 ページビュー呼び出し（[`t()`](/help/implement/vars/functions/t-method.md)）は含まれていません。

## 類似の指標と比較

* **ページイベント対[ ページビュー](page-views.md)**: ページイベントは、リンクトラッキング呼び出し数（[`tl()`](/help/implement/vars/functions/tl-method.md)）をカウントし、ページビュートラッキング呼び出し（[`t()`](/help/implement/vars/functions/t-method.md)）を除外します。 ページビューはその逆で、ページビューのトラッキング呼び出し数をカウントし、リンクを除外します。
