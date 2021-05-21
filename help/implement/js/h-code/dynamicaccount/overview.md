---
title: 動的アカウントの概要
description: H コードを使用してレポートスイートを動的に選択する方法に関するワークフローについて説明します。
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

---

# 動的アカウントの概要

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform Launch ではサポートされていません。

動的アカウントは、定義した条件に基づいてどのレポートスイートを使用するかを決定できる実装機能です。組織で複数のレポートスイートが必要で、サイト間で同じ実装を使用する場合は、動的アカウントはよいソリューションです。

>[!TIP]
>
> アドビでは、データを単一のレポートスイートに送信し、必要に応じて仮想レポートスイートを使用してデータを分離することをお勧めします。詳しくは、[グローバルレポートスイートの考慮事項](../../../prepare/global-rs.md)を参照してください。

3 つの変数を使用して、レポートスイートを動的に選択します。

* [`dynamicAccountSelection`](dynamicaccountselection.md)：動的アカウント選択を有効化または無効化します。
* [`dynamicAccountMatch`](dynamicaccountmatch.md)：観察する値を決定します。例えば、URL やクエリー文字列などです。
* [`dynamicAccountList`](dynamicaccountlist.md)：`dynamicAccountMatch` との値を比較し、一致が見つかった場合は `account` 変数を入力します。

`dynamicAccountSelection = true` の場合、`dynamicAccountMatch` の値が `dynamicAccountList` と比較されます。`dynamicAccountList` の値が一致する場合、レポートスイート ID が `account` 変数に含まれます。

## デフォルトのレポートスイート

`account` 変数を最初に設定し、指定された文字列が見つからない場合にデフォルト値として使用できます。次に例を示します。

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

`location.hostname` が `dev.example.com` または `example.com` のいずれでもない場合、ヒットは `examplersiddefault` に送信されます。

## マルチスイートタギング

マルチスイートタギングは、動的アカウント選択で使用できます。次に例を示します。

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

`location.hostname` に `example.com` が含まれる場合、ヒットは `examplersid1` と `examplersid2` の両方に送信されます。
