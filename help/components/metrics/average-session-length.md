---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 100%

---


# 平均セッション時間（モバイル）

「平均セッション時間（モバイル）」指標は、ディメンション項目ごとに特定のディメンション項目が存在する平均時間を示します。この指標は、[サイトでの平均滞在時間](average-time-on-site.md)指標に似ていますが、この指標が計算の一部としてモバイル SDK 固有のコンポーネントを使用する点が異なります。

## この指標の計算方法

この指標は、[モバイル指標](https://docs.adobe.com/content/help/ja-JP/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)を使用して計算されます`'Total session length' / ('Launches' - 'First launches'`。
