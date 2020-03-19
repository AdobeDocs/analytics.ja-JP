---
title: formatTime
description: 秒数を分、時間などの単位で同等の値に変換します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：formatTime

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `formatTime` ラグインを使用すると、任意の秒数を費やして、目的のベンチマーク値に丸められたグループ形式で表示できます。 秒単位で時間値を取り込み、バケット形式（分、日、週など）に変換する場合は、このプラグインを使用することをお勧めします。 2番目の値を時間で四捨五入したい場合は、このプラグインは不要です。

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
   * アクションタイプ：formatTimeの初期化
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `formatTime` ッドでは、次の引数を使用します。

* **`ns`** （必須、整数）:変換または形式設定する秒数
* **`tf`** （オプション、文字列）:秒を返す形式のタイプ。のデフォルトは秒です。
   * 日単位の時 `"d"` 間を求める場合に設定します（デフォルトで最も近い1/4日のベンチマークに丸められます）。
   * 時間単位 `"h"` で時間を計算する場合に設定します（デフォルトで最も近い1/4時間のベンチマークに丸められます）。
   * 時間を分 `"m"` 単位で指定する場合に設定します（デフォルトで最も近い1/2分のベンチマークに丸められます）。
   * 秒単位で時 `"s"` 間を計算する場合に設定します（デフォルトで最も近い5秒のベンチマークに丸められます）。
* **`bml`** （オプション、数値）:丸めベンチマークの長さ。 デフォルトでは、引数にリストされたベンチマークが使用されま `tf` す。

このメソッドは、引数で指定した単位を使用して形式設定された秒数を返し `tf` ます。 引数が設定さ `tf` れていない場合：

* 1分未満の場合は、最も近い5秒のベンチマークに丸められます。
* 1分から1時間の間にあるものは、最も近い1/2分のベンチマークに丸められます。
* 1時間から1日の間のものは、最も近い四半期のベンチマークに丸められます。
* 1日より大きいものは、最も近い日のベンチマークに丸められます。

## 例

### 例1

次のコード…

```js
s.eVar1 = s.formatTime(38242);
```

...はs.eVar1を「10.5時間」に設定します。

渡される引数（38242秒）は、10時間、37分、22秒に等しくなります。  tf引数がこの呼び出しに設定されておらず、渡される秒数が1時間と1日の間にあるので、プラグインは最も近い四半期のベンチマークに変換された秒数を返します。

### 例2

次のコード…

```js
s.eVar1 = s.formatTime(38250);
```

...は、s.eVar1を「10.75時間」に設定します。渡される引数（38250秒）は、10時間、37分、30秒です。  この場合、最も近い四半期のベンチマークに渡された秒数を丸めると、最終値は10.75時間に設定されます

### 例3

次のコード…

```js
s.eVar1 = s.formatTime(38242, "m");
```

...はs.eVar1を「637.5分」に設定します。

この場合、&quot;m&quot;引数は、プラグインに最も近い1/2分のベンチマークに秒を強制的に変換させます。

### 例4

次のコード…

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...は、s.eVar1を「640分」に設定します。

tf引数の値(&quot;m&quot;)は、プラグインに秒を強制的に分に変換させますが、bml引数の値(20)も、プラグインによって最も近い20分のベンチマークに分の変換が強制的に丸められます。

### 例5

次のコード…

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...は、s.eVar1を「126秒」に設定します。これは、最も近い2秒のベンチマークで125秒になります。

### 例6

次のコード…

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...は、s.eVar1を「3分」に設定します。これは、最も近い3分のベンチマークで125秒になります。

### 例7

次のコード…

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...は、s.eVar1を「2.4分」に設定します。これは、最も近い2/5分のベンチマーク(例：.4 = 2/5 ～ 145秒

## バージョン履歴

### 1.1（2018年5月22日）

* 丸めの柔軟性 `bml` を高めるために、引数を追加しました。

### 1.0（2018年4月16日）

* 最初のリリース。
