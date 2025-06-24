---
title: charSet
description: charSet 変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 65%

---

# charSet

Adobeでは、`charSet` 変数を使用して受信データを UTF-8 に変換し、Analytics で保存およびレポート作成できるようにします。 ほとんどのサイトでは、この変数を設定する必要はありません。

この変数は、レポートに文字化けした値（[mojibake](https://ja.wikipedia.org/wiki/Mojibake)）が表示される場合にのみ設定します。 サイトが異なるページで異なるエンコーディングを使用している場合は、この変数をページごとに設定できます。

## Web SDKの文字セット

Web SDKは現在 UTF-8 のみをサポートしており、エンコーディングを変更するオプションは提供していません。

## Adobe Analytics拡張機能の文字セット

「文字セット」は、Adobe Experience Platform Data Collection でAdobe Analytics拡張機能を設定する際に「[!UICONTROL &#x200B; 一般 &#x200B;]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL 文字セット]」フィールドが表示されます。

プリセット文字セットまたはカスタム文字セットを指定できます。レポートに文字化けした値が表示されない限り、`UTF-8` から値を変更しないでください。

## AppMeasurementの s.charSet と Analytics 拡張機能のカスタムコードエディター

`charSet` 変数は文字列です。Adobe Analytics に文字化けした値がある場合は、この変数をサイトの `<meta charset="">` HTML タグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
