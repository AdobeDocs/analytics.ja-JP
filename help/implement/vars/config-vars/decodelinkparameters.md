---
title: decodeLinkParameters
description: AppMeasurementのダブルエンコーディングリンクトラッキング変数を有効または無効にします。
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 8%

---

# decodeLinkParameters

`decodeLinkParameters` 変数は、リンクトラッキング変数を 1 回（`true` に設定されている場合）、または 2 回（`false` に設定されている場合）エンコードするかどうかを決定するブール値です。 `linkName` （[`tl()`](../functions/tl-method.md) メソッドの一部）および [`linkURL`](linkurl.md) にのみ影響します。 使用するにはAppMeasurement v2.24.0 以降が必要です。 この変数のデフォルト値は `false` です。

v2.24.0 より前のバージョンのAppMeasurementでは、リンクトラッキング変数は常に 2 回 URL エンコードされていました。 通常シングルバイト文字に依存する実装では問題になりませんが、ダブルエンコーディングでは、レポートのマルチバイト文字に対して、誤ってエンコードされた値が作成されていました。 この変数を `true` に設定すると、リンクトラッキングの値が 1 回エンコードされます。これは通常、目的の動作です。

* 実装でマルチバイト文字を使用し、リンクトラッキング変数が、オフセットAppMeasurementのダブルエンコーディングにデコードされた URL である場合は、この変数を `false` に設定します。 この値を指定すると、既存のAppMeasurement機能が保持されます。
* 実装でマルチバイト文字を使用し、URL デコードリンクトラッキングの値を指定しない場合、Adobeでは、この変数を `true` に設定することをお勧めします。
* 実装でマルチバイト文字を使用しない場合、この変数は不要です。 ただし、Adobeでは、マルチバイト文字が送信される可能性がある場合に、この変数を `true` に設定することをお勧めします。

## Web SDK を使用したダブルエンコーディングリンクパラメーター

この変数はAppMeasurementに固有で、Web SDK の実装のタイプでは必要ありません。

## Adobe Analytics拡張機能を使用したダブルエンコーディングリンクパラメーター

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.decodeLinkParameters

`s.decodeLinkParameters` 変数は、リンクトラッキング値が二重にエンコードされるかどうかを決定するブール値です。 この変数が定義されていない場合、既存の実装の機能を保持するためにデフォルト値が `false` 定されます。 Adobeでは、すべての新規実装で、特に、リンクトラッキングレポートに URL エンコード値が表示される場合、この値を `true` に設定することをお勧めします。

```js
s.decodeLinkParameters = true;
```
