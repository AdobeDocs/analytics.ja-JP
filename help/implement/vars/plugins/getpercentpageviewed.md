---
title: getPercentPageViewed
description: 訪問者が閲覧したページの割合を取得します。
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 91%

---

# アドビプラグイン：getPercentPageViewed

{{plug-in}}

`getPercentPageViewed` プラグインは訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。ページの高さが小さい場合や、スクロール動作を測定したくない場合は、このプラグインは不要です。

## Web SDK または Web SDK 拡張機能を使用したプラグインのインストール

このプラグインは、Web SDK 内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用したプラグインのインストール

Adobeには、Adobe Analyticsで最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * アクションタイプ：Initialize getPercentPageViewed
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
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPercentPageViewed` 関数は次の引数を使用します。

* **`pid`**（オプション、文字列）：現在のページに等しい変数または値。デフォルトでは、Analytics AppMeasurement `pageName` 変数に設定されています。AppMeasurement pageName 変数が設定されていない場合は、現在の URL になります。
* **`ch`**（オプション、ブール値）：初回読み込み後にページのサイズに対して行われた変更を考慮しない場合は、`false`（または `0`）に設定します。省略した場合、この引数はデフォルトで `true` になります。ほとんどの場合、この引数は省略することをお勧めします。

この関数を呼び出すと、何も返されません。代わりに、次の変数が設定されます。

* `window._ppvPreviousPage`：表示された前のページの名前。現在のページの最終的なスクロール値は、新しいページが読み込まれるまで使用できません。
* `window._ppvInitialPercentViewed`：前のページで、最初の読み込み時に表示された割合。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `100` です。
* `window._ppvHighestPercentViewed`：訪問者が閲覧した前のページの最高閲覧率（ページの高さ）。訪問者が前のページを下にスクロールした最も遠いポイント。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `100` です。
* `window._ppvFinalPercentViewed`：訪問者が現在のページに移動した際に表示されていた、前のページの割合。この値は、最初に表示された割合以上、最も表示されたページの割合以下になります。
* `window._ppvHighestPixelsSeen`：前のページで、訪問者が下にスクロールしたときに表示された合計ピクセル数の最高値（高さが基準）。
* `window._ppvFoldsAvailable`：前のページで下にスクロールできる「ページの折り目」の合計数です。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `1` です。
* `window._ppvFoldsSeen`：前のページで、訪問者が下にスクロールしたときに表示された「ページの折り目」の最高値（高さが基準）。この変数には、「ページの先頭」の折り目が含まれます。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `1` です。

これらの変数の 1 つ以上を eVar に割り当てて、レポート内のディメンションデータを表示します。

このプラグインは、上記の値を含む、`s_ppv` という名前のファーストパーティ Cookie を作成します。ブラウザーセッションの終わりに有効期限が切れます。

## 例

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## バージョン履歴

### 5.1（2022年12月8日）

* `_finalPercentViewed` ソリューションを追加しました。

### 5.0.1（2021年6月22日）

* 特定の特殊文字が原因でプラグインが壊れる問題を修正しました。

### 5.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### v4.0（2019年10月7日）

* `s._ppvFoldsSeen` および `s._ppvFoldsAvailable` ソリューションを追加しました。

### V3.01（2018年8月13日）

* 複数の AppMeasurement オブジェクトがあるページの問題を修正しました。

### V3.0（2018年4月13日）

* ポイントリリース（再コンパイル、コードサイズ縮小）
* プラグインで、戻り値の代わりに Adobe Analytics 変数に割り当てる変数を作成できるようになりました。
