---
title: 動的アカウントの概要
description: H コードを使用してレポートスイートを動的に選択する方法に関するワークフローについて説明します。
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 100%

---

# 動的アカウントの概要

>[!IMPORTANT]
>
>動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。 これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform のタグではサポートされていません。

動的アカウントは、定義した条件に基づいてどのレポートスイートを使用するかを決定できる実装機能です。 組織で複数のレポートスイートが必要で、サイト間で同じ実装を使用する場合は、動的アカウントはよいソリューションです。

>[!TIP]
>
>アドビでは、データを単一のレポートスイートに送信し、必要に応じて仮想レポートスイートを使用してデータを分離することをお勧めします。 詳しくは、[グローバルレポートスイートの考慮事項](../../../prepare/global-rs.md)を参照してください。

3 つの変数を使用して、レポートスイートを動的に選択します。

* [`dynamicAccountSelection`](dynamicaccountselection.md)：動的アカウント選択を有効化または無効化します。
* [`dynamicAccountMatch`](dynamicaccountmatch.md)：観察する値を決定します。 例えば、URL やクエリ文字列などです。
* [`dynamicAccountList`](dynamicaccountlist.md)：`dynamicAccountMatch` との値を比較し、一致が見つかった場合は `account` 変数を入力します。

`dynamicAccountSelection = true` の場合、`dynamicAccountMatch` の値が `dynamicAccountList` と比較されます。 `dynamicAccountList` の値が一致する場合、レポートスイート ID が `account` 変数に含まれます。

## デフォルトのレポートスイート

`account` 変数を最初に設定し、指定された文字列が見つからない場合にデフォルト値として使用できます。 次に例を示します。

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

`location.hostname` が `dev.example.com` または `example.com` のいずれでもない場合、ヒットは `examplersiddefault` に送信されます。

## マルチスイートタギング

マルチスイートタギングは、動的アカウント選択で使用できます。 次に例を示します。

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

`location.hostname` に `example.com` が含まれる場合、ヒットは `examplersid1` と `examplersid2` の両方に送信されます。
