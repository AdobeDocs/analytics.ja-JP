---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# 平均セッション時間（モバイル）

「平均セッション長（モバイル）」 [ 指標 ](overview.md) は、ディメンション項目あたりの特定のディメンション項目の平均滞在時間を示します。 この指標は、モバイルSDK固有のコンポーネントを計算の一部として使用する点を除き、[[!UICONTROL  訪問あたりの滞在時間（秒） ]](time-spent-per-visit.md) 指標に似ています。

## この指標の計算方法

この指標は、[ ライフサイクル指標 ](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) を使用して計算さ `'Total Session length' / ('Launches' - 'First launches'` ます。
