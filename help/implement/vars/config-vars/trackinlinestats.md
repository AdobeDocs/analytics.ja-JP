---
title: trackInlineStats
description: （廃止）実装でClickMapを有効または無効にします。
keywords: クリックマップを無効にする
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: https://experienceleague.adobe.com/K6rwl-ZECfoMLfC0Z25PPq2jV1FBo0cTsl1YfDeNpBQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

---

# trackInlineStats

>[!IMPORTANT]
>
>この変数は廃止され、使用されなくなりました。

ClickMapは、Adobe Analyticsの廃止された機能で、訪問者がクリックした場所とクリックした内容に関するデータを収集します。 機能は[Activity Map](/help/analyze/activity-map/overview.md)に置き換えられました。

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。 各クリックからの情報は、`s_sq`というラベルの付いたCookieに保存されます。

## Adobe Analytics拡張機能を使用してClickMapを有効にする

[!UICONTROL ClickMapを有効にする]は、Adobe Analytics拡張機能を設定する際の[!UICONTROL &#x200B; リンクトラッキング &#x200B;] アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL &#x200B; リンクトラッキング &#x200B;]」アコーディオンを展開すると、「[!UICONTROL ClickMapを有効にする]」チェックボックスが表示されます。

>[!NOTE]
>
>このチェックボックスは、[!UICONTROL &#x200B; ライブラリ管理] アコーディオンの下にある[!UICONTROL Activity Mapを使用] チェックボックスとは異なります。

## AppMeasurementのs.trackInlineStatsとAnalytics拡張機能のカスタムコードエディター

`s.trackInlineStats`は、ClickMap トラッキングを有効または無効にするブール値です。 この機能は廃止されているため、Adobeでは、この変数を設定することはお勧めしません。 デフォルト値は `false` です。

```js
s.trackInlineStats = false;
```
