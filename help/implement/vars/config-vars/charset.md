---
title: charSet
description: charSet 変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
translation-type: ht
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

charSet 変数は、Analytics での保存とレポート用に、受信データを UTF-8 に変換するためにアドビが使用します。サイトで UTF-8 以外の charSet を使用している場合、この変数を使用すると、データをアドビが適切にエンコードできます。この変数は、サイトで異なるページで異なるエンコーディングを使用する場合に、ページごとに設定できます。

## Adobe Experience Platform Launch の文字セット

「文字セット」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL 文字セット]」フィールドが表示されます。

プリセット文字セットまたはカスタム文字セットを指定できます。この値は、サイトの文字エンコーディングと一致する必要があります。ほとんどのサイトでは `UTF-8` を使用します。

## AppMeasurement の s.charSet と Launch カスタムコードエディター

`charSet` 変数は文字列です。この変数は、サイトの `<meta charset="">` HTML タグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
