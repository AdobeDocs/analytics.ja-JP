---
description: フィルタリングおよび重み付け指標の例について説明します。
title: フィルター済み指標と重み付け指標
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 19%

---

# フィルター適用済み指標と重み付け指標

この記事では、フィルタリングされた指標と重み付けされた指標の例を示します。

## バウンス率のフィルター

このシンプルなフィルター済み指標は、100回以上の訪問を持つページのみのバウンス率を示します。

![&#x200B; バウンス率のフィルター](assets/filtered-bounce-rate.png){zoomable="yes"}

この式は、一定の時間範囲に依存することに留意してください。 1日のレポートを実行する場合、訪問数が20を超えるページは閲覧する価値があります。 レポートを 1 ヶ月間実行する場合は、訪問回数がさらに多い場合に対応したフィルターが必要になる可能性があります。

## パーセンタイルでバウンス率をフィルタリング

このフィルターは、訪問者数で並べ替えた場合のページの上位30%の直帰率を示します。

![&#x200B; パーセンタイル &#x200B;](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}のフィルターされたバウンス率

## 重み付けバウンス率

一般的に直帰率でソートしたいが、訪問数が多いページはリストの上位に表示されるべきです。 そのためには、次のような重みを付けたバウンス率を作成します。

![](assets/weighted-bounce-rate.png)
