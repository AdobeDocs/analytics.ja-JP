---
title: visitorID
description: カスタム訪問者IDを使用します。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

アドビでは、サイトの訪問者を識別するために複数の異なる方法を使用しています。 この変数 `visitorID` は、訪問者の識別の他のすべての方法より優先されます。

> [!IMPORTANT] この変数の使用をお勧めします。 代わりに、 [Adobe Experience Cloud IDサービスを使用します](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。

## Adobe Experience Platform Launchでの訪問者ID

[!UICONTROL 訪問者IDは] 、Adobe Analytics拡張機能を設定する際に [!UICONTROL 、「Cookies] 」アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL Cookies] 」アコーディオンを展開し、「訪問者ID [!UICONTROL 」フィールドを] 表示します。

このフィールドを、カスタム訪問者IDを含むデータ要素に割り当てます。 このフィールドに静的値を設定しないでください。

## AppMeasurementのs.visitorIDとカスタムコードエディターの起動

変数 `s.visitorID` は、訪問者のカスタム一意識別子を含む文字列です。 有効な値には、最大100バイトの英数字が含まれます。 この変数では、ダッシュ、スペース、アンダースコアまたは記号の使用を避けます。

> [!WARNING] 1回の訪問で変数を `visitorID` 分割して設定した場合、データは2人の個別訪問者になります。

```js
s.visitorID = "abc123";
```
