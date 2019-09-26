---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

 変数は、導入でサードパーティ 2o7.net または omtrdc.net ドメインが使用されている場合でも、JavaScript（s_sq、s_cc、プラグイン）によって設定された本質的にファーストパーティの Cookie 用に使用されます。

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use , it is good practice to specify a value for  as well. *`cookieDomainPeriods`**`fpCookieDomainPeriods`**`fpCookieDomainPeriods`* は値を継承 *`cookieDomainPeriods`* します。 Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

「」とい *`fpCookieDomainPeriods`*&#x200B;う名前は、ピリオド(".")の数を表します。ドメインが「www」で始まる場合のドメインのピリオド（.）の数を指します。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

for javaScriptフ [!DNL AppMeasurement] ァイルは、変数を使 *`fpCookieDomainPeriods`* 用して、訪問者ID  (s_vi) cookie以外のファーストパーティcookieを設定するドメインを決定します。 There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). [!UICONTROL getValOnce] などのプラグインで使用される cookie も影響を受けます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | cookieDomainPeriods |

## Cookie ドメイン変数の設定に関するサンプルコード

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## 構文と可能な値

Folio Builder *`cookieDomainPeriods`* 変数は、以下のような文字列になります。

```js
s.fpCookieDomainPeriods="3"
```

## 例

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## 設定

なし