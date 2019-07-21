---
description: .js ファイルは、レポートスイート ID を自動的に選択するように設定できます。
keywords: Analytics の導入
seo-description: .js ファイルは、レポートスイート ID を自動的に選択するように設定できます。
seo-title: レポートスイートID-動的アカウント
solution: Analytics
title: レポートスイートID-動的アカウント
topic: 開発者と導入
uuid: 763a9741-309d-4795-8819-654386607d5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# レポートスイートID-動的アカウント

.js ファイルは、レポートスイート ID を自動的に選択するように設定できます。.js ファイルは、URL に基づいてイメージリクエストをレポートスイートへ自動的に送ります。例えば、URL が `www.mysite.com` だとすれば、イメージリクエストはレ
ポートスイート A へ自動送信されます。URL が `www.mysite1.com` だとすれば、イメージリクエストはレポートスイート B へ自動送信されます。

この文字列は次のいずれかの場所で検出できます。

* ホストまたはドメイン（デフォルト設定）
* パス
* クエリ文字列
* ホストまたはドメインとパス
* パスとクエリ文字列
* 完全修飾 URL

[!DNL Analytics]レポートスイート ID[!UICONTROL  を自動的に選択するように ] を設定する方法について詳しくは、アドビのライブサポートにお問い合わせください。

## マッチングに使用する URL セグメントの定義 {#section_8099162F75F641CFBE46FD814450EF36}

次のサンプル URL の場合の、URL の各構成要素と、`s.dynamicAccountMatch` 変数でどのように設定すべきかを以下の表に示します（デフォルト（`s.dynamicAccountMatch` が定義されていない場合）では、ホスト名またはドメイン名のみ検索します）。Sample URL: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| 構成要素 | 例（上記から引用） |
|---|---|
| ホスト名またはドメイン名 | `www.client.com` |
| パス | `directory1/directory2/filename.html` |
| クエリ文字列 | `param1=1234&param2=4321` |
| ホストまたはドメインとパス | `www.client.com/directory1/directory2/filename.html` |
| パスとクエリ文字列 | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| 構成要素 | `s.dynamicAccountmatch` |
| ホスト名またはドメイン名 | 未定義 |
| パス | `window.location.pathname` |
| クエリ文字列 | `(window.location.search?window.location.search:"?")` |
| ホストまたはドメインとパス | `window.location.host+window.location.pathname` |
| パスとクエリ文字列 | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

次の例をご覧ください。

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## 複数のルール {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

複数のルールが選択されている場合（上記の例を参照）は、ルールが左から右に実行されます。次に示すように、（特定のルールセットとの）マッチングが成功すると、すぐにルールが停止します。

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

The code first checks to determine if `qa.client.com` exists within the Host/Domain Name. If so, the report suite `devreportsuite1` is selected, and the match stops. ルールが複数ある場合はセミコロンで区切ります。

## デフォルトのレポートスイート {#section_0360D724929348B0B211708B5BA15647}

`s_account` 変数は最初に設定でき、指定した文字列が見つからない場合にはデフォルト値として機能します。次に例を示します。

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

In the case above, if the host/domain name did not contain either `qa.client.com` or `client.com`, the report suite *defaultreportsuiteid* would be used.
