---
title: 動的アカウントの概要
description: Hコードを使用してレポートスイートを動的に選択する方法に関するワークフローについて説明します。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# 動的アカウントの概要

> [!IMPORTANT] 動的アカウントは、レガシーJavaScript実装（Hコード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurementライブラリまたはAdobe Experience Platform Launchではサポートされていません。

動的アカウントは、定義した条件に基づいてどのレポートスイートを使用するかを決定できる実装機能です。 組織で複数のレポートスイートが必要で、サイト間で同じ実装を使用する場合は、動的アカウントを使用するとよいソリューションです。

> [!TIP] アドビでは、データを単一のレポートスイートに送信し、必要に応じて仮想レポートスイートを使用してデータを分離することをお勧めします。 詳しくは、 [グローバルレポートスイートの考慮事項](../../../prepare/global-rs.md) （英語）を参照してください。

3つの変数を使用して、レポートスイートを動的に選択します。

* [`dynamicAccountSelection`](dynamicaccountselection.md):動的アカウント選択を有効または無効にします。
* [`dynamicAccountMatch`](dynamicaccountmatch.md):観察する値を決定します。 例えば、URLやクエリ文字列などです。
* [`dynamicAccountList`](dynamicaccountlist.md):との値を比較し、 `dynamicAccountMatch`一致が見つかった場合は変数を入力し `account` ます。

の場 `dynamicAccountSelection = true`合、内の値がと比 `dynamicAccountMatch` 較されます `dynamicAccountList`。 値が一致する場 `dynamicAccountList` 合、レポートスイートIDが変数に含まれ `account` ます。

## デフォルトのレポートスイート

`account` 変数を最初に設定し、指定された文字列が見つからない場合にデフォルト値として使用できます。次に例を示します。

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

また `location.hostname` はのいず `dev.example.com` れもな `example.com`い場合、ヒットはに送信されます `examplersiddefault`。

## マルチスイートタギング

マルチスイートタギングは、動的アカウント選択で使用できます。 次に例を示します。

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

が含ま `location.hostname` れる場 `example.com`合、ヒットはとの両方に送 `examplersid1` 信されま `examplersid2`す。
