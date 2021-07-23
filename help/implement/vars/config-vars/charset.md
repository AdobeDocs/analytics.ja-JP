---
title: charSet
description: charSet 変数は、画像要求の解析にアドビが使用するエンコーディングを決定します。
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 90%

---

# charSet

charSet 変数は、Analytics での保存とレポート用に、受信データを UTF-8 に変換するためにアドビが使用します。ほとんどのサイトでは、この変数を設定する必要はありません。

この変数は、レポートに文字化けした値（[mojibake](https://ja.wikipedia.org/wiki/Mojibake)）が表示される場合にのみ設定します。 サイトが異なるページで異なるエンコーディングを使用している場合は、この変数をページごとに設定できます。

## Adobe Experience Platform の文字セット

「文字セット」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. `experience.adobe.com`に移動し、プロンプトが表示されたらログインします。
1. [!UICONTROL Launch /データ収集]を選択します。
1. 「[!UICONTROL Launch /データ収集に移動]」をクリックし、「[!UICONTROL タグ]」を選択します。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL 文字セット]」フィールドが表示されます。

プリセット文字セットまたはカスタム文字セットを指定できます。レポートに文字化けした値が表示されない限り、`UTF-8` から値を変更しないでください。

## AppMeasurement および カスタムコードエディターの s.charSet

`charSet` 変数は文字列です。Adobe Analytics に文字化けした値がある場合は、この変数をサイトの `<meta charset="">` HTML タグと同じ値に設定します。

```js
s.charSet = "UTF-8";
```
