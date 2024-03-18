---
title: dynamicVariablePrefix
description: 動的変数を識別する文字列をカスタマイズできます。
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 70%

---

# dynamicVariablePrefix

動的変数は、変数間で値をコピーできる簡単な概念です。動的変数はイメージリクエストの URL の長さを短くするのに役立つため、変数の値が長い場合に役立ちます。この概念について詳しくは、[動的変数](../page-vars/dynamic-variables.md)を参照してください。

デフォルトでは、動的変数は `D=` プレフィックスを使用します。`dynamicVariablePrefix` 変数を使用すると、動的変数を識別する文字列をカスタマイズできます。大文字と小文字が区別されます。

## Web SDK を使用した動的変数のプレフィックス

Web SDK では、動的な変数形式設定を使用しません。 代わりに、データストリームマッピングを使用して、単一のソースフィールドを使用して複数のターゲットフィールドにデータを入力できます。 詳しくは、 [Web SDK を使用した動的変数](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk) を参照してください。

スキーマに準拠せずにAdobe Analyticsに直接データを送信した場合、次の変数が使用されます。

* [データオブジェクト](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Adobe Analytics拡張機能を使用した動的変数プレフィックス

「動的変数プレフィックス」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL グローバル変数]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL グローバル変数]」アコーディオンを展開すると、「[!UICONTROL 動的変数のプレフィックス]」フィールドが表示されます。

このフィールドにはデフォルトで `D=` 値が含まれています。別の動的変数のプレフィックスを使用する場合は、値を変更できます。サイト上の文字エンコーディングと一致する限り、任意の値を使用できます。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.dynamicVariablePrefix

`s.dynamicVariablePrefix` 変数は、任意の文字シーケンスを含む文字列です。この変数を定義しない場合、AppMeasurement はデフォルトで文字列 `D=` を使用します。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
