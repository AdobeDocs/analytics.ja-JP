---
title: trackInlineStats
description: （廃止）実装でClickMapを有効または無効にします。
keywords: clickmap の無効化
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---

# trackInlineStats

>[!IMPORTANT]
>
>この変数は廃止され、使用されなくなりました。

ClickMapは、Adobe Analyticsの廃止された機能で、訪問者のクリック場所とクリック内容に関するデータを収集するものです。 機能は [Activity Map](/help/analyze/activity-map/overview.md) に置き換えられました。

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。各クリックからの情報は、`s_sq` というラベルの付いた cookie に保存されます。

## Adobe Analytics拡張機能を使用したClickMapの有効化

[!UICONTROL ClickMapを有効にする ] は、Adobe Analytics拡張機能の設定時に「[!UICONTROL  リンクトラッキング ]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL  リンクトラッキング ]」アコーディオンをを展開して、「[!UICONTROL ClickMapを有効にする ]」チェックボックスを表示します。

>[!NOTE]
>
>このチェックボックスは、「[!UICONTROL  ライブラリ管理 ] アコーディオンの下にある「[!UICONTROL Activity Mapを使用 ] チェックボックスとは異なります。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.trackInlineStats

`s.trackInlineStats` は、ClickMapのトラッキングを有効または無効にするブール値です。 この機能は廃止されるので、Adobeではこの変数を設定することはお勧めしません。 デフォルト値は `false` です。

```js
s.trackInlineStats = false;
```
