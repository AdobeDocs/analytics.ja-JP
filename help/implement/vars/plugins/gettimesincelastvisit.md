---
title: getTimeSinceLastVisit
description: 2 回の訪問の間の経過時間を測定します。
feature: Variables
exl-id: c5cef219-8a8a-4e57-a372-f2e063325a67
role: Admin, Developer
source-git-commit: a63567bd6b27a25486a99b62d4817a93ae673907
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 72%

---

# アドビプラグイン：getTimeSinceLastVisit

{{plug-in}}

`getTimeSinceLastVisit` プラグインを使用すると、訪問者が最後の訪問後にサイトに戻ってきた時間を追跡できます。

## Web SDK拡張機能を使用したプラグインのインストール

Adobeでは、web SDKで最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の **[!UICONTROL タグ]** をクリックしてから、目的のタグプロパティをクリックします。
1. 左側の **[!UICONTROL 拡張機能]** をクリックしてから、「**[!UICONTROL カタログ]**」タブをクリックします
1. **[!UICONTROL Common Web SDK Plugins]** 拡張機能を見つけてインストールします。
1. 左側の **[!UICONTROL データ要素]** をクリックしてから、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張機能：Common Web SDK Plugins
   * データ要素：`getTimeSinceLastVisit`
1. 変更を保存してデータ要素に公開します。

## Web SDKを手動で実装するプラグインのインストール

このプラグインは、web SDKの手動実装内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用してプラグインをインストールします

Adobeでは、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getTimeSinceLastVisit
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeSinceLastVisit v2.0 */
function getTimeSinceLastVisit(){if(arguments&&"-v"===arguments[0])return{plugin:"getTimeSinceLastVisit",version:"2.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.getTimeSinceLastVisit="2.0");window.formatTime=window.formatTime||function(c,b,d){function f(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var e="";"string"===typeof b&&"d"===b||("string"!==typeof b||!f("h,m,s",b))&&86400<=c?(b=86400,e="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!f("m,s",b))&&3600<=c?(b=3600,e="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!f("s",b))&&60<=c?(b=60,e="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,e="seconds",d=isNaN(d)?.2:b/d);e=Math.round(c*d/b)/d+" "+e;0===e.indexOf("1 ")&&(e=e.substring(0,e.length-1));return e}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var f=window.location.hostname,e=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){e=2<e?e:2;var k=f.lastIndexOf(".");if(0<=k){for(;0<=k&&1<e;)k=f.lastIndexOf(".",k-1),e--;k=0<k?f.substring(k):f}}g=k;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>f?b.length:f)))?c:""};h=new Date;var m=h.getTime(),n=cookieRead("s_tslv")||0,l=Math.round((m-n)/1E3);h.setTime(m+63072E6);cookieWrite("s_tslv",m,h);return n?1800<l||cookieRead("s_inv")?(cookieRead("s_inv")&&(l=cookieRead("s_inv")),cookieWrite("s_inv",l,30),"0"!==l?formatTime(l):"New Visitor"):"":(cookieWrite("s_inv","0",30),"New Visitor")}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeSinceLastVisit` 関数では引数を使用しません。訪問者が最後にサイトに来てから経過した時間を次の形式でグループ化して返します。

* 最後の訪問から 30 分～1 時間の時間は、最も近い 0.5 分のベンチマークに設定されます。例：`"30.5 minutes"`、`"53 minutes"`。
* 1 時間～1 日の時間は、最も近い 0.25 時間刻みのベンチマーク値に丸められます。例：`"2.25 hours"`、`"7.5 hours"`。
* 1 日を超える時間は、最も近い 1 日刻みのベンチマーク値に丸められます。例：`"1 day"`、`"3 days"`、`"9 days"`、`"372 days"`。
* 訪問者が訪問しなかった場合、または経過時間が 2 年を超える場合、値は `"New Visitor"` に設定されます。

>[!NOTE]
>
> このプラグインは、訪問の最初のヒット時にのみ値を返します。

このプラグインは、Unix の現在の時刻のタイムスタンプに設定される、ファーストパーティ Cookie「`"s_tslv"`」を作成します。この Cookie は、無操作状態が 2 年間続くと有効期限が切れます。

## 例

```js
// Given a visitor's first visit to the site
// Sets prop1 to "New Visitor"
s.prop1 = getTimeSinceLastVisit();

// 35 minutes later, the same visitor returns
// Sets prop1 to "35 minutes"
s.prop1 = getTimeSinceLastVisit();

// 4 days later, the same visitor returns
// Sets prop1 to "4 days"
s.prop1 = getTimeSinceLastVisit();
```

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 4 月 16 日（PT））

* ポイントリリース（コードの再コンパイルとコード縮小）。
* `getDaysSinceLastVisit` プラグインから派生したコード（現在は廃止され、名前が変更されています）。
* 戻り値に `formatTime` と `inList` プラグインを使用するようになりました。
