---
title: visitorID
description: カスタム訪問者 ID を使用します。
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: 7adf39a7f4ae5515f629894f90f7e8edf4519893
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 71%

---

# visitorID

アドビでは、サイトの訪問者を識別するために複数の異なる方法を使用しています。`visitorID` 変数は、他のすべての訪問者識別の方法より優先されます。

>[!IMPORTANT]
>
> この変数の使用はお勧めしません。代わりに、[Adobe Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してください。

## Adobe Analytics拡張機能を使用した訪問者 ID

「[!UICONTROL 訪問者 ID]」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開し、「[!UICONTROL 訪問者 ID]」フィールドを表示します。

このフィールドを、カスタム訪問者 ID を含むデータ要素に割り当てます。このフィールドに静的値を設定しないでください。

## AppMeasurementの s.visitorID と Analytics 拡張機能のカスタムコードエディター

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

## Web SDK と Experience Edge を使用した訪問者 ID

Experience Edge を使用すると、XDM の [ID マップ](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=en#using-identitymap). ID マップ内の ID は、それぞれ異なる名前空間を持ちます。 訪問者 ID に使用する名前空間を、 [データストリーム設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja#analytics). 設定が完了すると、この名前空間に指定された値を持つイベントを送信する際に、Analytics で訪問者 ID として自動的に使用されます。
