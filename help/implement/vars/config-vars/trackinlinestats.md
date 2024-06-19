---
title: trackInlineStats
description: （廃止）実装内のClickMapを有効または無効にします。
keywords: clickmap の無効化
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 30%

---

# trackInlineStats

>[!IMPORTANT]
>
> この変数は廃止されています。参照： [Activity Mapを有効にする](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) その代わり。

ClickMapは、Adobe Analyticsで廃止された機能で、訪問者のクリック場所とクリック内容に関するデータを収集するものです。 機能はに置き換えられました [Activity Map](/help/analyze/activity-map/activity-map.md).

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。各クリックからの情報は、というラベルの付いた cookie に保存されます `s_sq`.

## Adobe Analytics拡張機能を使用したClickMapの有効化

[!UICONTROL ClickMapを有効にする] 「」の下のチェックボックスです [!UICONTROL リンクトラッキング] Adobe Analytics拡張機能の設定時のアコーディオン。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. を展開します。 [!UICONTROL リンクトラッキング] アコーディオンは、 [!UICONTROL ClickMapを有効にする] チェックボックス。

>[!NOTE]
>
>このチェックボックスは、 [!UICONTROL Activity Mapを使用] の下にあるチェックボックス [!UICONTROL ライブラリ管理] アコーディオン。

## AppMeasurementー内の s.trackInlineStats と Analytics 拡張機能のカスタムコードエディター

この `s.trackInlineStats` は、ClickMapトラッキングを有効または無効にするブール値です。 この機能は廃止されるので、Adobeではこの変数の設定はお勧めしません。 デフォルト値は `false` です。

```js
s.trackInlineStats = false;
```
