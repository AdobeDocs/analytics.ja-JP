---
title: doubleEncodeLinkParameters
description: AppMeasurementの二重エンコーディングリンクトラッキング変数を有効または無効にします。
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# doubleEncodeLinkParameters

この `doubleEncodeLinkParameters` 変数は、リンクトラッキング変数を 1 回エンコードするかどうかを決定するブール値です ( `false`) または 2 回 ( 設定されている場合 `true`) をクリックします。 影響はのみ `linkName` ( [`tl()`](../functions/tl-method.md) メソッド ) および [`linkURL`](linkurl.md). 使用するには、AppMeasurement2.23.1以降が必要です。 この変数のデフォルト値は `true`.

以前のバージョンのAppMeasurementでは、リンクトラッキング変数は常に 2 回 URL エンコードされていました。 通常は 1 バイト文字に依存する実装では問題になりませんが、レポートで 2 バイト文字の値が誤ってエンコードされていました。 この変数を `false` はリンクトラッキング値を 1 回エンコードします。これは通常、必要な動作です。

* 実装でマルチバイト文字を使用し、リンクトラッキング変数が URL デコードされてAppMeasurementの二重エンコードをオフセットする場合、この変数をに設定します。 `true`. この値を指定しても、既存のAppMeasurement機能は維持されます。
* 実装でマルチバイト文字を使用し、URL デコードリンクトラッキング値を使用しない場合、Adobeではこの変数をに設定することをお勧めします。 `false`.
* 実装でマルチバイト文字を使用していない場合、この変数は不要です。 ただし、Adobeでは、この変数を `false` マルチバイト文字が送信される場合。

## Web SDK を使用してリンクパラメーターを二重エンコード

この変数はAppMeasurementに固有のもので、どのタイプの Web SDK 実装でも必要ありません。

## Adobe Analytics拡張機能を使用してリンクパラメーターを二重エンコードする

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.doubleEncodeLinkParameters

この `s.doubleEncodeLinkParameters` 変数は、リンクトラッキングの値が二重にエンコードされるかどうかを決定するブール値です。 この変数を定義しない場合、デフォルト値は `true` 既存の実装の機能を保持するため。 Adobeでは、この値をに設定することをお勧めします。 `false` （特にリンクトラッキングレポートに URL エンコードされた値が表示される場合）。

```js
s.doubleEncodeLinkParameters = false;
```
