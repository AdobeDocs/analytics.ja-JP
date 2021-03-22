---
title: getPercentPageViewed
description: 訪問者が閲覧したページの割合を取得します。
translation-type: tm+mt
source-git-commit: f11ad012756b5d42b1b53483c8688e30b4b79c83
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 98%

---


# アドビプラグイン：getPercentPageViewed

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getPercentPageViewed` プラグインは訪問者のスクロール操作を測定します。訪問者が別のページに移動する前に、該当のページのどのくらいの割合を閲覧したのかがわかります。ページの高さが小さい場合や、スクロール動作を測定したくない場合は、このプラグインは不要です。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * アクションタイプ：getPercentPageViewedの初期化
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPercentPageViewed` メソッドでは、次の引数を使用します。

* **`pid`**（オプション、文字列）：プラグインの測定値によって提供される割合と相関させることができるページベースの識別子です。デフォルトで `pageName` 変数に設定されます。
* **`ch`**（オプション、ブール値）：初回読み込み後にページのサイズに対しておこなわれた変更を考慮しない場合は、`false`（または `0`）に設定します。省略した場合、この引数はデフォルトで `true` になります。ほとんどの場合、この引数は省略することをお勧めします。

このメソッドを呼び出すと、何も返されません。代わりに、次の変数が設定されます。

* `s._ppvPreviousPage`：表示された前のページの名前。現在のページの最終的なスクロール値は、新しいページが読み込まれるまで使用できません。
* `s._ppvHighestPercentViewed`：訪問者が閲覧した前のページの最高閲覧率（ページの高さ）。訪問者が前のページを下にスクロールした最も遠いポイント。
* `s._ppvInitialPercentViewed`：前のページで、最初の読み込み時に表示された割合。
* `s._ppvHighestPixelsSeen`：前のページで、訪問者が下にスクロールしたときに表示された合計ピクセル数の最高値（高さが基準）。
* `s._ppvFoldsSeen`：前のページで、訪問者が下にスクロールしたときに表示された「ページの折り目」の最高値（高さが基準）。この変数には、「ページの先頭」の折り目が含まれます。
* `s._ppvFoldsAvailable`：前のページで下にスクロールできる「ページの折り目」の合計数です。

これらの変数の 1 つ以上を eVar に割り当てて、レポート内のディメンションデータを表示します。

このプラグインは、上記の値を含む、`s_ppv` という名前のファーストパーティ Cookie を作成します。ブラウザーセッションの終わりに有効期限が切れます。

## 呼び出しの例

### 例 1

次のコードは…

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* s.pageName が設定されているかどうかを判断し、設定されている場合、コードは getPercentPageViewed 関数を実行します
* getPercentPageViewed 関数を実行すると、上記の「戻り値」の節で説明した変数が作成されます
* 「戻り値」変数が正常に設定された場合：
   * コードは s.prop1 を s._ppvPreviousPage の値（つまり、s.pageName の前の値、または前のページ）に設定します
   * また、s.prop2 には、訪問者が閲覧した折り目の数と利用可能な折り目の数と共に、前のページの「最高閲覧率」と「初期閲覧率」に等しい値が設定されます

**注意**：ページを最初に読み込むときにページ全体が表示される場合、「最高閲覧率」ディメンションと「初期閲覧率」ディメンションの両方が 100 になり、「閲覧された折り目」と「利用可能な折り目」の両方が 1 になります。ページが最初に読み込まれたときにページ全体が表示されず、訪問者が次のページに進む前にページをスクロールしなかった場合、「最高閲覧率」ディメンションと「初期閲覧率」ディメンションの両方が同じ値になります。

### 例 2

ページ名全体ではなくロールアップされた「ページタイプ」を取り込むため、s.prop5 が別途設定されているとします。

次のコードは、s.prop5 が設定されているかどうかを判別し、設定されている場合はその値を「前のページ」として保存して、「最高閲覧率」ディメンションと「初期閲覧率」ディメンションを関連付けます。この値は s._ppvPreviousPage 変数に保存されたままですが、前のページ名の代わりに前のページタイプとして扱うことができます。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## バージョン履歴

### 5.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### v4.0（2019 年 10 月 7 日（PT））

* `s._ppvFoldsSeen` および `s._ppvFoldsAvailable` ソリューションを追加しました。

### V3.01（2018 年 8 月 13 日（PT））

* 複数の AppMeasurement オブジェクトがあるページの問題を修正しました。

### V3.0（2018 年 4 月 13 日（PT））

* ポイントリリース（再コンパイル、コードサイズ縮小）
* プラグインで、戻り値の代わりに Adobe Analytics 変数に割り当てる変数を作成できるようになりました。
