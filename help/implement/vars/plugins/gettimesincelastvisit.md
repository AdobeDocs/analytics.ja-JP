---
title: getTimeSinceLastVisit
description: 2回の訪問の間の経過時間を測定します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getTimeSinceLastVisit

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getTimeSinceLastVisit` ラグインを使用すると、訪問者が最後の訪問後にサイトに戻ってきた時間を追跡できます。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. プラグインを使用する起動ルールに対して、次の設定を含むアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEvarの初期化
1. ルールへの変更を保存して発行します

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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメ `getTimeSinceLastVisit` ソッドでは引数を使用しません。 訪問者が最後にサイトに来てから経過した時間を次の形式でグループ化して返します。

* 最後の訪問から30分から1時間までの時間は、最も近い30分のベンチマークに設定されます。 For example, `"30.5 minutes"`, `"53 minutes"`
* 1時間と1日の間の時間は、直近の四半期のベンチマークに丸められます。 For example, `"2.25 hours"`, `"7.5 hours"`
* 1日を超える時間は、最も近い日のベンチマークに丸められます。 For example, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* 訪問者が訪問しなかった場合、または経過時間が2年を超える場合、値はに設定されます `"New Visitor"`。

> [!NOTE] このプラグインは、訪問の最初のヒット時にのみ値を返します。

このプラグインは、Unixの現在の時刻のタイムスタンプに設定される `"s_tslv"` 、ファーストパーティcookieを作成します。 cookieは、無操作状態が2年間続くと有効期限が切れます。

## 呼び出しの例

### 例1

新規訪問者がサイトを訪問し、次のコードが訪問の最初のページで実行される場合…

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...s.prop1の値は「新しい訪問者」に設定されます。

同じコードが35分間操作が行われなかった後に同じドメインで実行される場合、s.prop1の値は「35分」に設定されます。

同じコードが4日間無操作状態が続いた後に同じドメインで実行される場合、s.prop1の値は「4日間」に設定されます。

## バージョン履歴

### 1.0（2018年4月17日）

* ポイントリリース（再コンパイルされたコードと小さいサイズ）。
* プラグインから派生し `getDaysSinceLastVisit` たコード（現在は廃止され、名前が変更されています）。
* 戻り値に `formatTime` とプ `inList` ラグインを使用するようになりました。
