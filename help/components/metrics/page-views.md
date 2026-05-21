---
title: ページビュー数
description: Adobe Analytics でディメンション項目が設定または保持された回数。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
TQID: https://experienceleague.adobe.com/ZJOoxc3imuMfVTa7caV5eQ6-XJh0amCRq65ByuANFq0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 100%

---

# ページビュー数

**[!UICONTROL ページビュー]**[指標](overview.md)は、特定のディメンション項目がページ上で設定または持続した回数を示します。 これは、レポートで最も一般的で基本的な指標の 1 つです。

## この指標の計算方法

この指標は、レポートスイート内のすべてのページビュートラッキングコール（[`t()`](/help/implement/vars/functions/t-method.md)）をカウントします。 ディメンションの場合、ディメンション項目が設定または保持されるヒットが含まれます。 これには、リンクトラッキングコール（[`tl()`](/help/implement/vars/functions/tl-method.md)）や[データソース](/help/import/data-sources/overview.md)からのデータは含まれません。

## 類似の指標と比較

* **ページビュー数と[訪問回数](visits.md)**：ページビュー数は、あるページが表示された回数をカウントします。 訪問回数は、訪問者のセッション数をカウントします。 1 回の訪問回数は、1 つ以上のページビュー数で構成されます。
* **ページビュー数と[ページイベント数](page-events.md)**：ページビュー数は、ページビュートラッキングコール数（`t()`）をカウントし、リンクトラッキングコール数（`tl()`）を除外します。 ページイベント数は反対に、リンクトラッキングコール数をカウントし、ページビュートラッキングコール数を除外します。
