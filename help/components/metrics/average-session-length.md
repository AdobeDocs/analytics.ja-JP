---
title: 平均セッション時間（モバイル）
description: モバイルデバイスの平均セッション長です。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
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
source-wordcount: 83
ht-degree: 36%

---

# 平均セッション時間（モバイル）

「平均セッション長（モバイル）」 [指標](overview.md)は、ディメンション項目ごとに特定のディメンション項目が存在する平均時間を示します。 これは、[[!UICONTROL 訪問当たりの滞在時間（秒） &#x200B;]](time-spent-per-visit.md)指標と似ていますが、この指標では、計算の一部としてモバイル SDK固有のコンポーネントを使用します。

## この指標の計算方法

この指標は、[&#x200B; ライフサイクル指標](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`を使用して計算されます。
