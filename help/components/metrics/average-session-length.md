---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 65%

---

# 平均セッション時間（モバイル）

「平均セッション時間（モバイル）」指標は、ディメンション項目ごとに特定のディメンション項目が存在する平均時間を示します。これは、 [訪問別滞在時間 [ 秒 ]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) 指標を除き、この指標は、計算の一部としてモバイル SDK 固有のコンポーネントを使用します。

## この指標の計算方法

この指標は、[モバイル指標](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=ja)を使用して計算されます`'Total session length' / ('Launches' - 'First launches'`。
