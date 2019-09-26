---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

サイトに外部サイトへのリンクが多数含まれており、一部の離脱リンクは追跡する必要がない場合、 を使用すると、離脱リンクの特定のサブセットについてレポートすることができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク | "" |

Folio Builder  variable is an optional variable used in conjunction with  to determine whether a link is an exit link. *`linkExternalFilters`**`linkInternalFilters`*&#x200B;出口リンクは、訪問者がサイトから出て行くすべてのリンクとして定義されます。離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。出口リンクは、 *`trackExternalLinks`* is set to 'true.' とのフィルターでは、大 *`linkExternalFilters`* 文字と *`linkInternalFilters`* 小文字が区別されません。

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

デフォルトでは、のフィルタ *`linkExternalFilters`* ーリスト *`linkInternalFilters`* とは、リンクのドメインとパスに適用されます。 を「true」 *`linkLeaveQueryString`* に設定すると、フィルターはURL全体（ドメイン、パス、クエリ文字列）に適用されます。 これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

ほとんどの企業では、 *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

次の例では、この変数の使用方法を示します。In this example, the URL of the page is `https://www.mysite.com/index.html`.

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

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. スペースは使用できません。

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. 内部リンクを強制的に離脱リンクにする場 *`linkInternalFilters`* 合は、の代わりにこの変数を使用しないでください。

* リン *`linkExternalFilters`* クのクエリ文字列に適用する必要がある場合は、が「true」に設 *`linkLeaveQueryString`* 定されていることを確認します。 See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
