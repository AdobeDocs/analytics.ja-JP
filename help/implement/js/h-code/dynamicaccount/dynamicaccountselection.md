---
title: 'dynamicAccountSelection '
description: dynamicAccountSelection 変数は、動的アカウント選択を有効化または無効化します。
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '85'
ht-degree: 100%

---

# dynamicAccountSelection 

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform Launch ではサポートされていません。

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
