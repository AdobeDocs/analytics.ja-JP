---
title: dynamicVariablePrefix
description: 動的変数を識別する文字列をカスタマイズできます。
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

動的変数は、変数間で値をコピーできる簡単な概念です。 イメージリクエストのURL長を短縮するのに役立つ、変数の値が長い場合に役立ちます。 この概 [念について詳しくは](../page-vars/dynamic-variables.md) 、「動的変数」を参照してください。

デフォルトでは、動的変数はプレフィックスを使用しま `D=`す。 この変 `dynamicVariablePrefix` 数を使用すると、動的変数を識別する文字列をカスタマイズできます。 大文字と小文字が区別されます。

## Adobe Experience Platform Launchの動的変数プレフィックス

動的変数プレフィックスは、Adobe Analytics拡張の設定時に [!UICONTROL 「グローバル変数] 」アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「グローバル変 [!UICONTROL 数] 」アコーディオンを展開すると、「動的変数のプレフィ [!UICONTROL ックス」フィールドが表示されます] 。

このフィールドにはデフォルトで `D=` 値が含まれています。 別の動的変数のプレフィックスを使用する場合は、値を変更できます。 サイト上の文字エンコーディングと一致する限り、任意の値を使用できます。

## AppMeasurementおよびLaunchカスタムコードエディターのs.dynamicVariablePrefix

変数 `s.dynamicVariablePrefix` は、任意の文字シーケンスを含む文字列です。 この変数を定義しない場合、AppMeasurementはデフォルトでこの文字列を `D=` 使用します。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
