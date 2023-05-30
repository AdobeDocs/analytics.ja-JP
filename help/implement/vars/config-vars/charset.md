---
title: charSet
description: charSet 変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: ef82c34f97a0c8172f097b83b521860a1897c82c
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 66%

---

# charSet

この `charSet` 変数は、Adobeが受信データを UTF-8 に変換して、Analytics での保存とレポートを可能にするために使用します。 ほとんどのサイトでは、この変数を設定する必要はありません。

この変数は、レポートに文字化けした値（[mojibake](https://ja.wikipedia.org/wiki/Mojibake)）が表示される場合にのみ設定します。 サイトが異なるページで異なるエンコーディングを使用している場合は、この変数をページごとに設定できます。

## Web SDK の文字セット

Web SDK は現在、UTF-8 のみをサポートしており、エンコーディングを変更するオプションは提供していません。

## Adobe Analytics拡張機能の文字セット

文字セットは [!UICONTROL 一般] アコーディオンを使用してAdobe Experience Platformデータ収集でAdobe Analytics拡張機能を設定する際に使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL 文字セット]」フィールドが表示されます。

プリセット文字セットまたはカスタム文字セットを指定できます。レポートに文字化けした値が表示されない限り、`UTF-8` から値を変更しないでください。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.charSet

`charSet` 変数は文字列です。Adobe Analytics に文字化けした値がある場合は、この変数をサイトの `<meta charset="">` HTML タグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
