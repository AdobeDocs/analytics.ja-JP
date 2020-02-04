---
title: 'dynamicAccountSelection '
description: dynamicAccountSelection変数は、動的アカウント選択を有効または無効にします。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection 

> [!IMPORTANT] 動的アカウントは、レガシーJavaScript実装（Hコード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurementライブラリまたはAdobe Experience Platform Launchではサポートされていません。

この変 `dynamicAccountSelection` 数は、動的アカウント選択を使用するかどうかを決定するブール値です。

に設定した場 `true`合、JavaScriptファイルはとを参照 `dynamicAccountMatch` します `dynamicAccountList`。

に設定した場 `false`合、またはこの変数を定義していない場合、変数と `dynamicAccountMatch` 変数 `dynamicAccountList` は無視されます。

この変数を定義しない場合、デフォルト値はです `false`。

## 構文

```js
s.dynamicAccountSelection = [boolean];
```

## 例

```js
s.dynamicAccountSelection = true;
```
