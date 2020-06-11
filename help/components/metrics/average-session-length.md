---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# 平均セッション時間（モバイル）

「Average session length (mobile)」指標は、ディメンション値ごとに特定のディメンション値が存在する平均時間を示します。 この指標は、 [Average time on site](average-time-on-site.md) （サイトでの平均滞在時間）指標に似ていますが、この指標が計算の一部としてモバイルSDK固有のコンポーネントを使用する点が異なります。

## この指標の計算方法

この指標は、 [モバイル指標を使用して計算されます](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)`'Total session length' / ('Launches' - 'First launches'`。
