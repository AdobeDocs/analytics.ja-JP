---
title: trackInlineStats
description: 実装でClickMapを有効または無効にします。
keywords: clickmap を無効にする
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: a3df69f7de45ba3694e1212e5c16a10bb4602cd6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 31%

---

# trackInlineStats

>[!IMPORTANT]
>
> この変数は廃止されています。詳しくは、 [「Enable」Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) 代わりに、

ClickMapは、訪問者がクリックした場所とクリックした内容に関するデータを収集する、Adobe Analyticsの古い機能です。 この機能はに置き換えられました。 [Activity Map](/help/analyze/activity-map/activity-map.md).

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。各クリックからの情報は、「 `s_sq`.

## Adobe Analytics拡張機能を使用したClickMapの有効化

[!UICONTROL ClickMapを有効にする] は、 [!UICONTROL リンクトラッキング] アコーディオンを使用してAdobe Analytics拡張機能を設定する際に使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. を展開します。 [!UICONTROL リンクトラッキング] アコーディオンは、 [!UICONTROL ClickMapを有効にする] チェックボックス。

>[!NOTE]
>
>このチェックボックスは、 [!UICONTROL 使用Activity Map] チェックボックス（の下） [!UICONTROL ライブラリ管理] アコーディオン。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.trackInlineStats

The `s.trackInlineStats` は、データトラッキングを有効または無効にするClickMap値です。 この機能は廃止されたので、Adobeではこの変数の設定はお勧めしません。 デフォルト値は `false` です。

```js
s.trackInlineStats = false;
```
