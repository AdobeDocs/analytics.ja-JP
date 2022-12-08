---
title: getPercentPageViewed
description: 訪問者が閲覧したページの割合を取得します。
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: 2575db561c244a9b52f98355137e73f05b3b7ee4
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 87%

---

# アドビプラグイン：getPercentPageViewed

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getPercentPageViewed` プラグインは訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。ページの高さが小さい場合や、スクロール動作を測定したくない場合は、このプラグインは不要です。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getPercentPageViewed
1. Save and publish the changes to the rule.-->

## カスタムコードエディターを使用したプラグインのインストール

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform データ収集](https://experience.adobe.com/data-collection)にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPercentPageViewed` 関数は次の引数を使用します。

* **`pid`** （オプション、文字列）:現在のページに等しい変数または値。 デフォルトで Analytics AppMeasurement に設定されます。 `pageName` 変数に値を格納します。AppMeasurement pageName 変数が設定されていない場合は、現在の URL になります。
* **`ch`**（オプション、ブール値）：初回読み込み後にページのサイズに対しておこなわれた変更を考慮しない場合は、`false`（または `0`）に設定します。省略した場合、この引数はデフォルトで `true` になります。ほとんどの場合、この引数は省略することをお勧めします。

この関数を呼び出すと、何も返されません。代わりに、次の変数が設定されます。

* `window._ppvPreviousPage`：表示された前のページの名前。現在のページの最終的なスクロール値は、新しいページが読み込まれるまで使用できません。
* `window._ppvInitialPercentViewed`：前のページで、最初の読み込み時に表示された割合。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `100` です。
* `window._ppvHighestPercentViewed`：訪問者が閲覧した前のページの最高閲覧率（ページの高さ）。訪問者が前のページを下にスクロールした最も遠いポイント。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `100` です。
* `window._ppvFinalPercentViewed`:訪問者が現在のページに移動した時点で表示された、前のページの割合。 この値は、初期閲覧率以上になり、最も閲覧されたページの最高閲覧率以下になります。
* `window._ppvHighestPixelsSeen`：前のページで、訪問者が下にスクロールしたときに表示された合計ピクセル数の最高値（高さが基準）。
* `window._ppvFoldsAvailable`：前のページで下にスクロールできる「ページの折り目」の合計数です。ページが最初に読み込まれたときにページ全体が表示されている場合、この値は `1` です。
* 
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
  s.prop2 = "initialPercent=" + _ppvInitialPercent + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercent + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## バージョン履歴

### 5.1（2022 年 12 月 9 日）

* 追加された `_finalPercentViewed` ソリューション

### 5.0.1（2021 年 6 月 22 日（PT））

* 特定の特殊文字が原因でプラグインが壊れる問題を修正しました。

### 5.0 （2021 年 3 月 29 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### v4.0（2019 年 10 月 7 日（PT））

* `s._ppvFoldsSeen` および `s._ppvFoldsAvailable` ソリューションを追加しました。

### V3.01（2018 年 8 月 13 日（PT））

* 複数の AppMeasurement オブジェクトがあるページの問題を修正しました。

### V3.0（2018 年 4 月 13 日（PT））

* ポイントリリース（再コンパイル、コードサイズ縮小）
* プラグインで、戻り値の代わりに Adobe Analytics 変数に割り当てる変数を作成できるようになりました。
