---
title: decodeLinkParameters
description: AppMeasurementのダブルエンコーディングリンクトラッキング変数を有効または無効にします。
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 8%

---

# decodeLinkParameters

`decodeLinkParameters`変数は、リンクトラッキング変数が1回（`true`に設定されている場合）または2回（`false`に設定されている場合）エンコードされるかどうかを決定するブール値です。 `linkName` （[`tl()`](../functions/tl-method.md) メソッドの一部）と[`linkURL`](linkurl.md)にのみ影響します。 使用するには、AppMeasurement v2.24.0以降が必要です。 この変数のデフォルト値は`false`です。

AppMeasurement v2.24.0以前のバージョンでは、リンクトラッキング変数は常に2回URL エンコードされていました。 通常は1 バイト文字に依存する実装では問題ではありませんが、ダブルエンコーディングでは、レポート内のマルチバイト文字に対して誤ってエンコードされた値が作成されました。 この変数を`true`に設定すると、リンクのトラッキング値が1回エンコードされます。これは通常、目的の動作です。

* 実装でマルチバイト文字を使用し、リンクトラッキング変数がURL デコードされてAppMeasurementのダブルエンコーディングがオフセットされる場合は、この変数を`false`に設定します。 この値は、既存のAppMeasurement機能を保持します。
* 実装でマルチバイト文字を使用しており、URL デコード リンクのトラッキング値を使用しない場合は、Adobeでは、この変数を`true`に設定することをお勧めします。
* 実装でマルチバイト文字を使用しない場合、この変数は必要ありません。 ただし、Adobeでは、マルチバイト文字が送信される可能性がある場合は、この変数を`true`に設定することをお勧めします。

## Web SDKを使用したリンクパラメーターのダブルエンコーディング

この変数はAppMeasurement固有であり、Web SDKの実装では必要ありません。

## Adobe Analytics拡張機能を使用したリンクパラメーターのダブルエンコーディング

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.decodeLinkParametersとAnalytics拡張機能のカスタムコードエディター

`s.decodeLinkParameters`変数は、リンクトラッキング値が二重エンコードされるかどうかを決定するブール値です。 この変数が定義されていない場合、既存の実装の機能を保持するために、デフォルト値は`false`です。 Adobeでは、特にリンクトラッキングレポートにURL エンコードされた値が表示される場合は、すべての新しい実装でこの値を`true`に設定することをお勧めします。

```js
s.decodeLinkParameters = true;
```
