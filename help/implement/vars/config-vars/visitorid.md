---
title: visitorID
description: カスタム訪問者 ID を使用します。
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 86%

---

# visitorID

アドビでは、サイトの訪問者を識別するために複数の異なる方法を使用しています。`visitorID` 変数は、他のすべての訪問者識別の方法より優先されます。

>[!IMPORTANT]
>
> この変数の使用はお勧めしません。代わりに、[Adobe Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してください。

## Web SDK を使用した訪問者 ID の上書き

近日開始！

## Adobe Analytics拡張機能を使用した訪問者 ID

「[!UICONTROL 訪問者 ID]」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開し、「[!UICONTROL 訪問者 ID]」フィールドを表示します。

このフィールドを、カスタム訪問者 ID を含むデータ要素に割り当てます。このフィールドに静的値を設定しないでください。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.visitorID

`s.visitorID` 変数は、訪問者の一意のカスタム識別子を含む文字列です。有効な値には、最大 100 バイトの英数字が含まれます。この変数では、ダッシュ、スペース、アンダースコアまたは記号の使用を避けます。

>[!WARNING]
>
>1 回の訪問で `visitorID` 変数を分割して設定した場合、データは 2 人のユニーク訪問者を示します。

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>カスタム訪問者 ID を無効に実装すると、データが正しくなくなり、レポートのパフォーマンスが低下する可能性があります。この変数にデフォルト値（`"0"` やなど `"NULL"`）が含まれている場合、これらのヒットは同じ訪問者であるかのように扱われます。この状況では、誤ったデータが返され、訪問者数と訪問者レベルのセグメントが期待どおりに機能しなくなります。また、カスタム訪問者 ID が誤って実装されると、処理サーバーに負荷がかかり、[待ち時間](/help/technotes/latency.md)が増加し、レポートのパフォーマンスが低下します。
