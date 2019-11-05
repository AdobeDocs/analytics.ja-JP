---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.fpCookieDomainPeriods

 変数は、導入でサードパーティ 2o7.net または omtrdc.net ドメインが使用されている場合でも、JavaScript（s_sq、s_cc、プラグイン）によって設定された本質的にファーストパーティの Cookie 用に使用されます。

*`fpCookieDomainPeriods`* 変数は動的に設定されることはありません。*`cookieDomainPeriods`* を使用する場合は、*`fpCookieDomainPeriods`* の値も指定することをお勧めします。*`fpCookieDomainPeriods`* は *`cookieDomainPeriods`* の値を継承します。*`fpCookieDomainPeriods`* は、導入で cookie がファーストパーティ cookie として扱われる場合でも、訪問者 ID cookie が設定されるドメインには影響しません。

名前「*`fpCookieDomainPeriods`*」は、ピリオド（「.」）の数を参照します。ドメインが「www」で始まる場合のドメインのピリオド（.）の数を指します。例えば、`www.mysite.com` には 2 つのピリオドがあり、`www.mysite.co.jp` には 3 つのピリオドがあります。変数を説明する別の方法は、サイトのメインドメインのセクションの数です（`mysite.com` の場合は 2 つ、`mysite.co.jp` の場合は 3 つ）。

JavaScript 版 [!DNL AppMeasurement] ファイルは *`fpCookieDomainPeriods`* 変数を使用して、[!UICONTROL 訪問者 ID] (s_vi) cookie 以外のファーストパーティ cookie を設定するドメインを決定します。There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). [!UICONTROL getValOnce] などのプラグインで使用される cookie も影響を受けます。

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

*`cookieDomainPeriods`* 変数は、以下のような文字列になります。

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
