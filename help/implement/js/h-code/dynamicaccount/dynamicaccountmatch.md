---
title: dynamicAccountMatch
description: dynamicAccountMatch 変数は、動的アカウントで表示する値を決定します。
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。 これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform のタグではサポートされていません。

`dynamicAccountMatch` 変数は、`dynamicAccountList` が値を調べて比較する値です。 `dynamicAccountSelection` を `true` に設定しない場合、この変数は無視されます。

この変数を定義しない場合、デフォルト値は `window.location.host` です。

## 構文

```js
s.dynamicAccountMatch=[DOM object]
```

## 例

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## 追加情報

* ハードドライブに保存されたページには、複数の `location` 変数が定義されていません（例えば、`location.host` は空白）。 `s_account` にデフォルトのレポートスイートが含まれていることを確認します。
* ページが Google などの Web ベースの翻訳エンジンによって翻訳されている場合、動的アカウント選択は設計どおりに動作しません。 より精度の高いトラッキングをおこなうには、`s_account` 変数をサーバーサイドで設定してください。
