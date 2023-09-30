---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 26%

---

# 平均セッション時間（モバイル）

「平均セッション時間（モバイル）」 [指標](overview.md) は、ディメンション項目ごとに特定のディメンション項目が存在する平均時間を示します。 これは、 [[!UICONTROL 訪問別滞在時間（秒）]](time-spent-per-visit.md) 指標を除き、この指標は、モバイル SDK 固有のコンポーネントを計算の一部として使用します。

## この指標の計算方法

この指標は、 [ライフサイクル指標](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
