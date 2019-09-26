---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。

The default value for  is "2". *`cookieDomainPeriods`* This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain ,  should be "2". `www.mysite.com`*`cookieDomainPeriods`* For ,  should be "3".`www.mysite.co.jp`*`cookieDomainPeriods`*

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting  to "2" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www.mysite.co.jp``s_cc``s_sq``co.jp``co.jp` は無効なドメインであるので、ほぼすべてのブラウザーでこれらの cookie が拒否されます。その結果、訪問者クリックマップ用のデータが消失し、[!UICONTROL 訪問者プロファイル]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートに、ほぼ 100 ％の訪問者から cookie が拒否されたと示されます。

if *`cookieDomainPeriods`* が「3」で、ドメインにピリオドが 2 つだけ含まれている場合、JavaScript ファイルはサイトのサブドメインに対して cookie を設定します。For example, if setting  to "3" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www2.mysite.com``s_cc``s_sq``www2.mysite.com`When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example,  would still have  set to "2". `store.toys.mysite.com`*`cookieDomainPeriods`*&#x200B;この変数定義によって、ルートドメイン [!DNL mysite.com] に対して cookie が正しく設定されます。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | CDP | 訪問者 ID の保存方法と処理方法を制御するため、複数のレポートに影響します。 | "2" |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) これらのサービスに実装すると、お客様の独自のドメインを設定していない場合（導入をテストする場合など）に、すべての Cookie をブロックしているユーザーを削除する Analytics のプライバシー設定による影響が生じることがあります。その場合は、システムによって Cookie が無効化されている、機能していないまたはアクセスできないと判断されたヒットは、すべてオプトアウトされるので、レポートからは除外されます。

## 例

変数を手動で設定します。

```js
s.cookieDomainPeriods = "3";
```

コア JavaScript ファイルで両方のタイプをホストしている場合に、変数を動的に設定するいくつかの例を示します。

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## 注意事項、質問、ヒント

* 訪問者クリックマップ用のデータがないことに気付いた場合、または[!UICONTROL トラフィック]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートで大きな割合の訪問者が cookie を拒否していることを示している場合、*`cookieDomainPeriods`* の値が正しいことを確認してください。

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. この設定により、訪問者がサブドメインを切り替えたときにデータが消失する可能性があります。
* The  variable was used in deprecated implementations prior to  to set the visitor ID cookie. *`cookieDomainPeriods`**`trackingServer`* Though only present in outdated code, failure to correctly define  in this circumstance puts your implementation at risk of data loss.*`cookieDomainPeriods`*