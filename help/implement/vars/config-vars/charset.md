---
title: charSet
description: charSet変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

charSet変数は、Analyticsでの保存とレポート用に、受信データをUTF-8に変換するためにアドビが使用します。 サイトでUTF-8以外のcharSetを使用している場合、この変数を使用すると、データをアドビが適切にエンコードできます。 この変数は、サイトで異なるページで異なるエンコーディングを使用する場合に、ページごとに設定できます。

## Adobe Experience Platform Launchの文字セット

「文字セット」は、Adobe Analytics拡張機能を設定す [!UICONTROL る際に] 、一般アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 一般アコーデ [!UICONTROL ィオンを展開すると] 、「文字セット」フィールド [!UICONTROL が表示されます] 。

プリセット文字セットまたはカスタム文字セットを使用できます。 この値は、サイトの文字エンコーディングと一致する必要があります。 ほとんどのサイトでは、を使用し `UTF-8`ます。

## AppMeasurementのs.charSetとカスタムコードエディターの起動

変数 `charSet` は文字列です。 この変数は、サイトの `<meta charset="">` HTMLタグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
