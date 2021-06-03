---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 90%

---

# 平均セッション時間（モバイル）

「平均セッション時間（モバイル）」指標は、ディメンション項目ごとに特定のディメンション項目が存在する平均時間を示します。この指標は、[サイトでの平均滞在時間](average-time-on-site.md)指標に似ていますが、この指標が計算の一部としてモバイル SDK 固有のコンポーネントを使用する点が異なります。

## この指標の計算方法

この指標は、[モバイル指標](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)を使用して計算されます`'Total session length' / ('Launches' - 'First launches'`。
