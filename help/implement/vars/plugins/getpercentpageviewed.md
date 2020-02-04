---
title: getPercentPageViewed
description: 訪問者が閲覧したページの割合を取得します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getPercentPageViewed

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

The `getPercentPageViewed` plug-in measures a visitor&#39;s scroll activity to see how much of a page they view before moving on to another page. ページの高さが小さい場合や、スクロール動作を測定したくない場合は、このプラグインは不要です。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getPercentPageViewed` ッドでは、次の引数を使用します。

* **`pid`**（オプション、文字列）: ページベースの識別子は、プラグインの測定値によって提供される割合と相関させることができます。  デフォルトで変数に設`pageName`定されます。
* **`ch`**（オプション、ブール値）: 初回読み込み`false`後にページのサイズに対して行われた変更を考慮しない場合は、これを(または`0`)に設定します。 省略した場合、この引数はデフォルトで`true`す。 ほとんどの場合、この引数は省略することをお勧めします。

このメソッドを呼び出すと、何も返されません。代わりに、次の変数が設定されます。

* `s._ppvPreviousPage`:表示された前のページの名前。 現在のページの最終的なスクロール値は、新しいページが読み込まれるまで使用できません。
* `s._ppvHighestPercentViewed`：訪問者が閲覧した前のページの最高閲覧率（ページの高さ）。訪問者が前のページを下にスクロールした最も遠いポイント。
* `s._ppvInitialPercentViewed`:前のページが最初に読み込まれたときに表示された、前のページの割合です。
* `s._ppvHighestPixelsSeen`：前のページで、訪問者が下にスクロールしたときに表示された合計ピクセル数の最高値（高さが基準）。
* `s._ppvFoldsSeen`:訪問者が前のページを下にスクロールしたときに最も多く到達した「ページの折り目」の数です。 この変数には、「ページの先頭」の折り目が含まれます。
* `s._ppvFoldsAvailable`:前のページで下にスクロールできる「ページの折り目」の合計数です。

これらの変数の1つ以上をeVarに割り当てて、レポート内のディメンションデータを表示します。

このプラグインは、上記の値を含む、という名前のファーストパー `s_ppv` ティcookieを作成します。 ブラウザーセッションの終わりに有効期限が切れます。

## 呼び出しの例

### 例1

次のコード…

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* s.pageNameが設定されているかどうかを判定し、設定されている場合は、コードがgetPercentPageViewed関数を実行します
* getPercentPageViewed関数を実行すると、上記の「戻り値」の節で説明した変数が作成されます
* 「戻り値」変数が正常に設定された場合：
   * コードは、s.prop1をs._ppvPreviousPageの値（つまり、s.pageNameの前の値、または前のページ）に設定します。
   * また、s.prop2には、訪問者が閲覧した折り目の数と利用可能な折り目の数と共に、前のページの最も高い閲覧率と最初の閲覧率に等しい値が設定されます

**注意**: ページを最初に読み込むときにページ全体が表示される場合、「最も高い閲覧率」ディメンションと「初回の閲覧率」ディメンションの両方が100になり、「閲覧された折り目」と「利用可能な折り目」の両方が1になります。   ページが最初に読み込まれても、訪問者が最後にページを下にスクロールしてから次のページに移動した場合、最も高い閲覧率ディメンションと最初の閲覧率ディメンションの両方が同じ値になります。

### 例2

ページ名全体ではなくロールアップされた「ページタイプ」を取り込むため、s.prop5 が別途設定されているとします。

次のコードは、s.prop5が設定されているかどうかを判別し、設定されている場合はその値を「前のページ」として保存して、最高閲覧率ディメンションと初期閲覧率ディメンションを関連付けます。  値はs._ppvPreviousPage変数には引き続き格納されますが、前のページ名の代わりに前のページタイプであったかのように扱うことができます。

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## バージョン履歴

### v4.0（2019年10月8日）

* 追加されたソ `s._ppvFoldsSeen` リューシ `s._ppvFoldsAvailable` ョン

### v3.01（2018年8月13日）

* ページに複数のAppMeasurementオブジェクトがあるページの問題を修正しました。

### v3.0（2018年4月14日）

* ポイントリリース（再コンパイル、コードサイズ小）
* プラグインで、戻り値の代わりにAdobe Analytics変数に割り当てる変数を作成できるようになりました。
