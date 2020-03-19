---
title: getPageLoadTime
description: ページの読み込みにかかる時間を追跡します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getPageLoadTime

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getPageLoadTime` ラグインは、JavaScriptパフォーマンスオブジェクトを使用して、ページの読み込みが完了するまでの時間を測定できます。 ページの読み込みに要する時間を測定する場合は、このプラグインを使用することをお勧めします。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最もよく使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、ボタンをクリックしま [!UICONTROL Catalog] す。
1. 拡張機能のインストールと公 [!UICONTROL Common Analytics Plugins] 開
1. まだ設定していない場合は、「Initialize Plug-ins」というラベルの付いたルールを次の設定で作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：getPageLoadTimeの初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

次のコードを、Analyticsトラッキングオブジェクトのインスタンス化（を使用）後に、AppMeasurementファイルの任意の場所にコピーして貼り付 [`s_gi`](../functions/s-gi.md)けます。 導入時にコードのコメントとバージョン番号を保持すると、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageLoadTime v1.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires p_fo plug-in) */
s.getPageLoadTime=function(){var a=this;if("undefined"!==typeof performance&&a.p_fo("performance")){var b=performance; b.clearResourceTimings();""!==a.c_r("s_plt")&&(0<b.timing.loadEventEnd&&clearInterval(a.pi),a._pltLoadTime=a.c_r("s_plt"),a._pltPreviousPage=a.c_r("s_pltp"),a.c_w("s_plt",""),a.c_w("s_pltp",""));0===b.timing.loadEventEnd?a.pi=setInterval(function(){a.performanceWriteFull()},250):0<b.timing.loadEventEnd&&(a.ptc?a.ptc===b.timing.loadEventEnd&&1===b.getEntries().length&&(a.pwp=setInterval(function(){a.performanceWritePart()},500)):a.performanceWriteFull())}};
s.performanceWriteFull=function(){var s=this,a=performance.timing;0<a.loadEventEnd&&(clearInterval(s.pi),""===s.c_r("s_plt")&& (s.c_w("s_plt",s.performanceCheck(a.loadEventEnd,a.navigationStart)),s.c_w("s_pltp",s.pageName)));s.ptc=a.loadEventEnd};
s.performanceWritePart=function(){var s=this,a=performance;0<a.getEntries().length&&(s.ppfe===a.getEntries().length? clearInterval(s.pwp):s.ppfe=a.getEntries().length);""===s.c_r("s_plt")&&(s.c_w("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),s.c_w("s_pltp",s.pageName))};
s.performanceCheck=function(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

メソッド `getPageLoadTime` は引数を使用しません。 このメソッドを呼び出すと、何も返されません。 代わりに、次の変数が設定されます。

* `s._pltPreviousPage`:読み込み時間を前のページに関連付けるための前のページ
* `s._pltLoadTime`:前のページの読み込みに要した時間（秒）

getPageLoadTimeプラグインは、2つのファーストパーティcookieを作成します。

* `s_plt`:前のページの読み込みにかかった時間（秒）。 ブラウザーセッションの終了時に期限切れになります。
* `s_pltp` 以前のAdobe Analyticsイメ `s.pageName` ージリクエストで記録された変数の値。 ブラウザーセッションの終了時に期限切れになります。

## 呼び出しの例

### 例1

次のコードを実行しています…

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

...は、次の処理を行います。

* s.pageNameが設定されている場合は、getPageLoadTimeプラグインを実行します。
* s.prop10を前のページの読み込み時間と同じに設定します。
* s.prop11とs.eVar10を前のページの名前（s.pageNameで記録されている）と同じに設定します。
* カスタムの数値イベントであるevent100を、前のページの読み込み時間と同じに設定します。   この場合、カスタムイベントを使用すると、前のページのすべてのページ読み込みの合計時間を（すべての訪問者/訪問から）取得でき、計算指標を使用して各ページの平均ページ読み込み時間を取得できます

## バージョン履歴

### 1.0（2018年5月23日）

* 初回リリース。
