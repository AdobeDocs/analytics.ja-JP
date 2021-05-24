---
title: getPageLoadTime
description: ページの読み込みにかかる時間を追跡します。
exl-id: 9bf0e26b-f1af-48a6-900a-712f7e588d37
source-git-commit: c814c023fe909b5e78d6dd46de8c27213a4d92be
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 97%

---

# アドビプラグイン：getPageLoadTime

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getPageLoadTime` プラグインは、JavaScript パフォーマンスオブジェクトを使用して、ページの読み込みが完了するまでの時間を測定できます。ページの読み込みに要する時間を測定する場合は、このプラグインを使用することをお勧めします。

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
   * Action Type：Initialize getPageLoadTime
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

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
/* Adobe Consulting Plugin: getPageLoadTime v2.0.1 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function l(){var a=performance.timing;if(0<a.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt"))){var b=window,d=b.cookieWrite;var c=a.loadEventEnd;var f=a.navigationStart;c=0<=c&&0<=f?6E4>c-f&&0<=c-f?parseFloat((c-f)/1E3).toFixed(2):60:void 0;d.call(b,"s_plt",c);window.cookieWrite("s_pltp",window.pageName)}window.ptc=a.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0.1"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPageLoadTime="2.0.1");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var c=window.location.hostname,f=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){f=2<f?f:2;var h=c.lastIndexOf(".");if(0<=h){for(;0<=h&&1<f;)h=c.lastIndexOf(".",h-1),f--;h=0<h?c.substring(h):c}}g=h;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),c=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>c?b.length:c)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((e=performance,e.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<e.timing.loadEventEnd&&clearInterval(window.pi),this._pltLoadTime=window.cookieRead("s_plt"),this._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===e.timing.loadEventEnd)?window.pi=setInterval(function(){l()},250):0<e.timing.loadEventEnd&&(window.ptc?window.ptc===e.timing.loadEventEnd&&1===e.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):l()))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPageLoadTime` メソッドでは引数を使用しません。このメソッドは呼び出されても、何も返されません。代わりに、次の変数を設定します。

* `s._pltPreviousPage`：前のページ（読み込み時間を関連付けできます）。
* `s._pltLoadTime`：前のページの読み込みに要した時間（秒）。

getPageLoadTime プラグインは、2 つのファーストパーティ Cookie を作成します。

* `s_plt`：前のページの読み込みにかかった時間（秒）。ブラウザーセッションの終了時に有効期限が切れます。
* `s_pltp` 以前の Adobe Analytics イメージリクエストで記録された `s.pageName` 変数の値。ブラウザーセッションの終了時に有効期限が切れます。

## 呼び出しの例

### 例 1

次のコードを実行すると...

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

以下が起こります。

* s.pageName が設定されている場合は、getPageLoadTime プラグインを実行します。
* s.prop10 を前のページの読み込み時間に設定します。
* s.prop11 と s.eVar10 を、前のページの名前（s.pageName に記録されているとおり）に設定します。
* カスタムの数値イベントになる event100 を、前のページの読み込み時間と同じに設定します。この場合、カスタムイベントを使用すると、前のページのすべてのページ読み込みに関する合計時間を（すべての訪問者／訪問から）取得でき、計算指標を使用して各ページの平均ページ読み込み時間を取得できます。

## バージョン履歴

### 2.0.1（2021年3月27日）

* プラグインがsオブジェクトの値を正しく設定できない問題を修正しました。

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 5 月 22 日（PT））

* 初回リリース。
