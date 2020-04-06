---
title: visitorID
description: カスタム訪問者 ID を使用します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# visitorID

アドビでは、サイトの訪問者を識別するために複数の異なる方法を使用しています。`visitorID` 変数は、他のすべての訪問者識別の方法より優先されます。

>[!IMPORTANT] この変数の使用はお勧めしません。代わりに、[Adobe Experience Cloud ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を使用してください。

## Adobe Experience Platform Launch の「訪問者 ID」

[!UICONTROL Visitor ID] は、Adobe Analytics拡張を設定する際に、ア [!UICONTROL Cookies] コーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Cookies] ンを展開すると、フィールドが表示 [!UICONTROL Visitor ID] されます。

このフィールドを、カスタム訪問者 ID を含むデータ要素に割り当てます。このフィールドに静的値を設定しないでください。

## AppMeasurement および Launch カスタムコードエディターの s.visitorID

`s.visitorID` 変数は、訪問者の一意のカスタム識別子を含む文字列です。有効な値には、最大 100 バイトの英数字が含まれます。この変数では、ダッシュ、スペース、アンダースコアまたは記号の使用を避けます。

>[!WARNING] 1 回の訪問で `visitorID` 変数を分割して設定した場合、データは 2 人の個別訪問者を示します。

```js
s.visitorID = "abc123";
```
