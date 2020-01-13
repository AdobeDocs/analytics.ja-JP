---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.linkExternalFilters

サイトに外部サイトへのリンクが多数含まれており、一部の出口リンクは追跡する必要がない場合、 を使用すると、出口リンクの特定のサブセットについてレポートすることができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク | "" |

*`linkExternalFilters`* 変数はオプションの変数です。リンクが出口リンクかどうかを判断するため、*`linkInternalFilters`* と組み合わせて使用します。出口リンクは、訪問者がサイトから出て行くすべてのリンクとして定義されます。出口リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが出口リンクレポートに表示されるかどうかに影響しません。出口リンクは、*`trackExternalLinks`* が「True」に設定されているときのみ有効です。*`linkExternalFilters`* と *`linkInternalFilters`* のフィルターは、大文字と小文字を区別します。

> [!NOTE]*`linkExternalFilters`* を使用しない場合は、削除するか "" に設定します。

デフォルトでは、*`linkExternalFilters`* および *`linkInternalFilters`* のフィルターのリストは、デフォルトではリンクのドメインとパスに適用されます。*`linkLeaveQueryString`* が「true」に設定されている場合、フィルターは URL 全体（ドメイン、パス、クエリ文字列）に適用されます。これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

ほとんどの企業では、*`linkInternalFilters`* によって出口リンクを十分に制御できるので、*`linkExternalFilters`* は必要ありません。*`linkExternalFilters`* を使用すると、出口リンクが外部リンクと見なされる可能性が少なくなります。*`linkExternalFilters`* に値が設定されているときは、*`linkInternalFilters`* が *`linkExternalFilters`* と一致しない場合にのみ、リンクは外部とみなされます。

次の例では、この変数の使用方法を示します。この例では、ページの URL は `https://www.mysite.com/index.html` です。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## 構文と可能な値

*`linkExternalFilters`* 変数は、ASCII 文字のコンマ区切りリストです。スペースは使用できません。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL の任意の部分をコンマで区切って、*`linkExternalFilters`* から構成される明示的な画像セットを指定します。

## 例

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## 設定

なし

## 注意事項、質問、ヒント

* *`linkExternalFilters`* を使用すると、サイト上で出口リンクとして扱われるリンク数を少なくすることができます。内部リンクを強制的に出口リンクにする場合は、*`linkInternalFilters`* の代わりにこの変数を使用しないでください。

* *`linkExternalFilters`* をリンクのクエリ文字列に適用する必要がある場合は、*`linkLeaveQueryString`* が「true」に設定されていることを確認します。`"true"` に設定する前に、[linkLeaveQueryString](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) を参照してください。

* 出口リンクトラッキングを無効にするには、*`trackExternalLinks`* を `"false"` に設定します。
