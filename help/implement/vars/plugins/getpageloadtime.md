---
title: getPageLoadTime
description: ページの読み込みにかかる時間を追跡します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 100%

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

### 1.0（2018 年 5 月 23 日）

* 初回リリース。
