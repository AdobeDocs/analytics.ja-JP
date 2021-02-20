---
title: charSet
description: charSet 変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 60%

---


# charSet

charSet 変数は、Analytics での保存とレポート用に、受信データを UTF-8 に変換するためにアドビが使用します。ほとんどのサイトでは、この変数を設定する必要はありません。

この変数は、レポートに文字化けした値([mojibake](https://en.wikipedia.org/wiki/Mojibake))が表示される場合にのみ設定します。 サイトで異なるページで異なるエンコーディングを使用している場合は、この変数をページごとに設定できます。

## Adobe Experience Platform Launch の文字セット

「文字セット」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL 文字セット]」フィールドが表示されます。

プリセット文字セットまたはカスタム文字セットを指定できます。レポートに文字化けした値が表示されない限り、`UTF-8`から値を変更しないでください。

## AppMeasurement および Launch カスタムコードエディターの s.charSet

`charSet` 変数は文字列です。Adobe Analyticsで値が文字化けしている場合は、この変数をサイトの`<meta charset="">` HTMLタグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
