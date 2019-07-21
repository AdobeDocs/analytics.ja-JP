---
description: 動的アカウントでの一般的なエラーについて、以降の節で説明します。
keywords: Analytics の導入
seo-description: 動的アカウントでの一般的なエラーについて、以降の節で説明します。
seo-title: 一般的なエラー
solution: Analytics
subtopic: トラブルシューティング
title: 一般的なエラー
topic: 開発者と導入
uuid: 04345355-60cc-4678-81c3-390c86752df1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 一般的なエラー

動的アカウントでの一般的なエラーについて、以降の節で説明します。

## アカウントのハードコーディング {#section_FB6F89BF317F45D387C00986ACA690BC}

データを常に特定のレポートスイートに送信する場合は、[!UICONTROL s_dynamicAccountSelection] を false に設定します（または、変数をまとめて削除することもできます）。

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

上記の例では、他の 2 行を削除すると、defaultreportsuiteid が常に使用されます。

## コードの配置 {#section_05375CB2EF5A414794BC8209C906AEEB}

Defining *`s_account`* after the lines of code does not override the dynamic account selection, as shown below.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

上記の例では、「anotherreportsuiteid」アカウントは「defaultreportsuiteid」よりは優先されますが、さらに [!UICONTROL s.dynamicAccountList] で一致した項目の方が優先されます。[!UICONTROL s.dynamicAccountList] を評価する関数は、実際にはかなり後で .JS ファイル内で実行されます。

## マルチスイートタギング {#section_6C014FA9B87D4622B483BCDE4281D2A9}

マルチスイートタギングは、以下のように動的アカウント選択と組み合わせて使用できます。

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## 動的アカウント一致 {#section_647AB47B38D640D6BCC853FDA4E4342D}

[!UICONTROL 動的アカウント一致]に関する変数を引用符で囲まないでください。オプションは以下のとおりです。

| ホスト名またはドメイン名 | なし |
|---|---|
| クエリ文字列 | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| ホストまたはドメインとパス | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| パスとクエリ文字列 | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| 完全修飾 URL | s.dynamicAccountMatch=window.location.href |

