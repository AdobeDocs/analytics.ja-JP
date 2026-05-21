---
title: dynamicVariablePrefix
description: 動的変数を識別する文字列をカスタマイズできます。
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
TQID: https://experienceleague.adobe.com/4NlOgI1maQuMHenSZHUnc7ESvlbst09v4CmOMlBbfEE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 71%

---

# dynamicVariablePrefix

動的変数は、変数間で値をコピーできる簡単な概念です。 動的変数はイメージリクエストの URL の長さを短くするのに役立つため、変数の値が長い場合に役立ちます。 この概念について詳しくは、[動的変数](../page-vars/dynamic-variables.md)を参照してください。

デフォルトでは、動的変数は `D=` 接頭辞を使用します。 `dynamicVariablePrefix` 変数を使用すると、動的変数を識別する文字列をカスタマイズできます。 大文字と小文字が区別されます。

## Web SDKを使用した動的変数のプレフィックス

Web SDKでは、動的変数の書式設定は使用されません。 代わりに、データストリームマッピングを使用して、1つのSource フィールドを使用して複数のターゲットフィールドに入力できます。 詳しくは、「[Web SDKを使用した動的変数](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk)」を参照してください。

スキーマに準拠せずにAdobe Analyticsに直接データを送信する場合、次の変数が使用されます。

* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Adobe Analytics拡張機能を使用した動的変数のプレフィックス

「動的変数接頭辞」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL グローバル変数]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL グローバル変数]」アコーディオンを展開すると、「[!UICONTROL 動的変数の接頭辞]」フィールドが表示されます。

このフィールドにはデフォルトで `D=` 値が含まれています。 別の動的変数の接頭辞を使用する場合は、値を変更できます。 サイト上の文字エンコーディングと一致する限り、任意の値を使用できます。

## AppMeasurementのs.dynamicVariablePrefixとAnalytics拡張機能のカスタムコードエディター

`s.dynamicVariablePrefix` 変数は、任意の文字シーケンスを含む文字列です。 この変数を定義しない場合、AppMeasurement はデフォルトで文字列 `D=` を使用します。

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
