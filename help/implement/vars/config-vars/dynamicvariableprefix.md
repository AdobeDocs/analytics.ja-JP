---
title: dynamicVariablePrefix
description: 動的変数を識別する文字列をカスタマイズできます。
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 100%

---


# dynamicVariablePrefix

動的変数は、変数間で値をコピーできる簡単な概念です。動的変数はイメージリクエストの URL の長さを短くするのに役立つため、変数の値が長い場合に役立ちます。この概念について詳しくは、[動的変数](../page-vars/dynamic-variables.md)を参照してください。

デフォルトでは、動的変数は `D=` プレフィックスを使用します。`dynamicVariablePrefix` 変数を使用すると、動的変数を識別する文字列をカスタマイズできます。大文字と小文字が区別されます。

## Adobe Experience Platform Launch の「動的変数プレフィックス」

「動的変数プレフィックス」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL グローバル変数]」アコーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL グローバル変数]」アコーディオンを展開すると、「[!UICONTROL 動的変数のプレフィックス]」フィールドが表示されます。

このフィールドにはデフォルトで `D=` 値が含まれています。別の動的変数のプレフィックスを使用する場合は、値を変更できます。サイト上の文字エンコーディングと一致する限り、任意の値を使用できます。

## AppMeasurement および Launch カスタムコードエディターの s.dynamicVariablePrefix

`s.dynamicVariablePrefix` 変数は、任意の文字シーケンスを含む文字列です。この変数を定義しない場合、AppMeasurement はデフォルトで文字列 `D=` を使用します。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
