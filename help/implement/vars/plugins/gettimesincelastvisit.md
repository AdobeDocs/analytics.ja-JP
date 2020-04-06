---
title: getTimeSinceLastVisit
description: 2 回の訪問の間の経過時間を測定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getTimeSinceLastVisit

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getTimeSinceLastVisit` プラグインを使用すると、訪問者が最後の訪問後にサイトに戻ってきた時間を追跡できます。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getTimeSinceLastVisit
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeSinceLastVisit` メソッドでは引数を使用しません。訪問者が最後にサイトに来てから経過した時間を次の形式でグループ化して返します。

* 最後の訪問から 30 分～1 時間の時間は、最も近い 0.5 分のベンチマークに設定されます。例：`"30.5 minutes"`、`"53 minutes"`。
* 1 時間～1 日の時間は、最も近い 0.25 時間刻みのベンチマーク値に丸められます。例：`"2.25 hours"`、`"7.5 hours"`。
* 1 日を超える時間は、最も近い 1 日刻みのベンチマーク値に丸められます。例：`"1 day"`、`"3 days"`、`"9 days"`、`"372 days"`。
* 訪問者が訪問しなかった場合、または経過時間が 2 年を超える場合、値は `"New Visitor"` に設定されます。

>[!NOTE] このプラグインは、訪問の最初のヒット時にのみ値を返します。

このプラグインは、Unix の現在の時刻のタイムスタンプに設定される、ファーストパーティ Cookie「`"s_tslv"`」を作成します。この Cookie は、無操作状態が 2 年間続くと有効期限が切れます。

## 呼び出しの例

### 例 1

新規訪問者がサイトを訪問し、次のコードが訪問の最初のページで実行される場合、

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

s.prop1 の値は「新規訪問者」に設定されます。

無操作状態が 35 分間続いた後に同じコードが同じドメインで実行された場合、s.prop1 の値は「35 分」に設定されます。

無操作状態が 4 日間続いた後に同じコードが同じドメインで実行された場合、s.prop1 の値は「4 日間」に設定されます。

## バージョン履歴

### 1.0（2018 年 4 月 17 日）

* ポイントリリース（コードの再コンパイルとコード縮小）。
* `getDaysSinceLastVisit` プラグインから派生したコード（現在は廃止され、名前が変更されています）。
* 戻り値に `formatTime` と `inList` プラグインを使用するようになりました。
