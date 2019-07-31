---
description: 訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。このプラグインを使用すると、ユーザーが平均的に見ているコンテンツの量を判断できるので、ユーザーの行動に基づいてページの長さやレイアウトを最適化できます。
keywords: Analytics の導入
seo-description: 訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。このプラグインを使用すると、ユーザーが平均的に見ているコンテンツの量を判断できるので、ユーザーの行動に基づいてページの長さやレイアウトを最適化できます。
seo-title: getPercentPageViewed
solution: Analytics
subtopic: プラグイン
title: getPercentPageViewed
topic: 開発者と導入
uuid: 1751dddb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: f9912a0da5930be965e4d249f3d2c1891cfd6ed6

---


# getPercentPageViewed

getPercentPageViewedプラグインは、訪問者のスクロールアクティビティを測定して、訪問者が他のページに移動する前に閲覧したページの割合を表示します。

>[!NOTE]
>Webページの高さが小さい場合、getPercentPageViewedプラグインを使用する必要はありません。また、訪問者がどれだけ下にスクロールするかを測定する必要はありません。また、終了ページでのみスクロールアクティビティを測定する場合、このプラグインは使用できません。

## 前提条件

getPercentPageViewedプラグインを実行するには、AppMeasurementおよびhandlePvEventsヘルパープラグインが必要です。

## 実装

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>太字のコメント/バージョン番号をAppMeasurementファイルに追加すると、潜在的な実装の問題をトラブルシューティングできます。

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## 渡す引数

| 引数 | 定義 |
|---|---|
| pid（オプション、文字列） | プラグイン測定によって提供される割合と相関しているページ識別子。これは、Analytics pageName変数またはpageName変数が設定されていない場合はURLです |
| ch（オプション、ブール型） | この引数の推奨/デフォルト値は"True"です。SPAコード、動的HTMLなどにより、ページの初期読み込み後にページのサイズに加えた変更をこのプラグインに考慮しないようにするには、このプラグインを"false"に設定します。 |

## 戻り値

getPercentPageViewedプラグインは何も返しません。その代わり、AppMeasurement オブジェクト内の次の変数が設定されます。

* `s._ppvPreviousPage`:前のページの名前（最後のページが読み込まれるまでは使用できないため）。
* `s._ppvHighestPercentViewed`:訪問者が閲覧した前のページの割合（高さ）。つまり、訪問者が前のページを下にスクロールした時点で最も遠いポイントです。
* `s._ppvInitialPercentViewed`:前のページが最初に読み込まれたときに表示された前のページの割合。
* `s._ppvHighestPixelSeen`:訪問者が前のページをスクロールダウンしたときに表示される総ピクセル数（高さ）。

## Cookie

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. cookieのコンテンツには、前述の4つの変数に挿入された値が含まれており、セッションの最後に期限切れになります。

## 呼び出しの例

**サンプル呼び出し1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

上記のコードサンプル:
* s. pageNameが設定されているかどうかを判定します。そうしないと、コードはgetPercentPageViewed関数を実行します。
* `getPercentPageViewed` 関数が実行されると、上記の「戻り値」セクションで説明されている変数が作成されます。
* 「戻り値」変数が正常に設定された場合:

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * また、このコードでは、s. prop2に前のページで表示された上位の割合の割合と、前のページで表示された初期の割合の割合が設定されます。

>[!NOTE]
>最初にロードされたときにページ全体が表示されている場合、表示される割合の上限と表示比率の初期値は100となります。ただし、最初のページに移動したときにページ全体が表示されないが、訪問者が次のページに移動する前にページをスクロールしない場合、「閲覧された最大の割合」のディメンションと最初の割合の表示ディメンションの両方が同じ値になります。

**サンプル呼び出し2**

s. prop5が、ページ名全体ではなく、ロールアップ「ページタイプ」を取得するように別途設定されているとします。

次のコードでは、s. prop5が設定されているかどうかを判断し、その場合は「前のページ」として値を保存して、表示された上位の割合と表示された初期の割合のディメンションとコリレートします。The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Sオブジェクトの置き換え

"s"以外の名前を持つメインのAppMeasurementライブラリオブジェクトをインスタンス化するときは、次のプラグインコードの一部を変更してください。

`s.getPercentPageViewed=function(pid,ch)`

を次に示します。

`[objectname].getPercentPageViewed=function(pid,ch)`

## 導入コード

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
