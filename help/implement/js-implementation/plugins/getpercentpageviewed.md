---
description: 訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。このプラグインを使用すると、ユーザーが平均的に見ているコンテンツの量を判断できるので、ユーザーの行動に基づいてページの長さやレイアウトを最適化できます。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPercentPageViewed

getPercentPageViewed プラグインは、訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。

>[!NOTE]
>Web ページの高さが小さく、訪問者がどれだけ下にスクロールするかを測定する必要がない場合は、getPercentPageViewed プラグインを使用する必要はありません。また、離脱ページでのスクロールアクティビティのみを測定する場合は、このプラグインを使用できません。

## 前提条件

getPercentPageViewed プラグインを実行するには、AppMeasurement と handlePPVevents ヘルパープラグインが必要です。

## 実装

このプラグインを実装するには、[!DNL AppMeasurement] ファイルの **[!UICONTROL プラグイン]**&#x200B;セクション内の任意の場所にコードをコピーして貼り付けます。

>[!NOTE]
>コードの太字のコメント／バージョン番号を AppMeasurement ファイルに追加すると、実装時に発生する可能性のある問題のトラブルシューティングに役立ちます。

必要に応じて doPlugins 関数内で、必要に応じて `getPercentPageViewed` 関数を実行できます（以下の呼び出し例を参照）。

## 渡す引数

| 引数 | 定義 |
|---|---|
| pid（オプション、文字列） | プラグイン測定によって提供されるパーセンテージと関連するページ識別子。デフォルトでは、Analytics の pageName 変数に設定されます。pageName が設定されていない場合は URL になります。 |
| ch（オプション、ブール値） | この引数では、「true」が推奨値であり、デフォルト値です。SPA コードや動的 HTML などによる、最初の読み込み後のページサイズの変更についてはプラグインで考慮しない場合は、この引数を false に設定します。 |

## 戻り値

getPercentPageViewed プラグインは何も返しません。その代わり、AppMeasurement オブジェクト内の次の変数が設定されます。

* `s._ppvPreviousPage`：前に閲覧されたページの名前（新しいページが読み込まれるまで、最終的な測定値を使用できないため）。
* `s._ppvHighestPercentViewed`：訪問者が閲覧した前のページの最高閲覧率（ページの高さ）。つまり、前のページで、訪問者が前のページを最も下までスクロールしたポイントです。
* `s._ppvInitialPercentViewed`：前のページで、最初の読み込み時に表示されたパーセンテージ。
* `s._ppvHighestPixelSeen`：前のページで、訪問者が下にスクロールしたときに表示された合計ピクセル数の最高値（高さが基準）。

## Cookie

getPercentPageViewed プラグインは、ページからページに渡される、「`s_ppv`」というcookieを作成します。Cookie の内容には、上記の 4 つの変数に挿入された値が含まれ、有効期限はセッションが終わるまでです。

## 呼び出しの例

**サンプル呼び出し 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

上記のコード例：
* s.pageName が設定されているかどうかを判断し、設定されている場合、コードは getPercentPageViewed 関数を実行します。
* `getPercentPageViewed` 関数を実行すると、上記の「戻り値」の節で説明した変数が作成されます。
* 「戻り値」変数が正常に設定された場合：

   * コードセット s.prop1 は`s._ppvPreviousPag` の値（例：`s.pageName` の前の値、または前のページ）
   * また、s.prop2 には、前のページの最高閲覧率と、前のページの初期閲覧率に等しい値を設定します。

>[!NOTE]
>ページが最初に読み込まれたときにページ全体が表示される場合、「最高閲覧率」と「初期閲覧率」の両方のディメンションは 100 に等しくなります。ただし、ページが最初に読み込まれたときにページ全体が表示されず、訪問者が次のページに進む前にページをスクロールしなかった場合、最高閲覧率ディメンションと初期閲覧率ディメンションの両方が同じ値になります。

**サンプル呼び出し 2**

ページ名全体ではなくロールアップされた「ページタイプ」を取り込むため、s.prop5 が別途設定されているとします。

次のコードは、s.prop5 が設定されているかどうかを判別し、設定されている場合はその値を「前のページ」として保存して、最高閲覧率（％）ディメンションと初期閲覧率（％）ディメンションを関連付けます。この値は `s._ppvPreviousPage` 変数に保存されたままですが、前のページ名の代わりに前のページタイプとして扱うことができます。

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## S オブジェクトの置換

「s」以外の名前でメインの AppMeasurement ライブラリオブジェクトをインスタンス化する場合は、プラグインコードの次の部分を、

`s.getPercentPageViewed=function(pid,ch)`

次のように変更します。

`[objectname].getPercentPageViewed=function(pid,ch)`

## デプロイするコード

Plugins Section：`s_code.js` ファイルにある PLUGINS SECTION という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
