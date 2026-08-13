---
title: dynamicAccountSelection
description: dynamicAccountSelection 変数は、動的アカウント選択を有効化または無効化します。
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurement ライブラリまたはAdobe Experience Platform Data Collectionではサポートされていません。

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
