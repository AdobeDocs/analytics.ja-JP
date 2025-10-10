---
title: 'dynamicAccountSelection '
description: dynamicAccountSelection 変数は、動的アカウント選択を有効化または無効化します。
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection 

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在のAppMeasurement ライブラリやAdobe Experience Platform Data Collection ではサポートされていません。

`dynamicAccountSelection` 変数は、動的アカウント選択を使用するかどうかを決定するブール値です。

`true` に設定した場合、JavaScript ファイルは `dynamicAccountMatch` と `dynamicAccountList` を参照します。

`false` に設定した場合、またはこの変数を定義していない場合、`dynamicAccountMatch` 変数と `dynamicAccountList` 変数は無視されます。

この変数を定義しない場合、デフォルト値は `false` です。

## 構文

```js
s.dynamicAccountSelection = [boolean];
```

## 例

```js
s.dynamicAccountSelection = true;
```
