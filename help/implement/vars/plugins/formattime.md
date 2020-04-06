---
title: formatTime
description: 秒数を分単位、時間単位などで同等の値に変換します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：formatTime

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`formatTime` プラグインを使用すると、任意の秒数を、目的のベンチマーク値に丸めてグループ形式で表示できます。秒単位で時間値を取得し、バケット形式（分、日、週など）に変換する場合は、このプラグインを使用することをお勧めします。秒単位の値を時間で丸める場合は、このプラグインは不要です。

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
   * Action Type：Initialize formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`formatTime` メソッドでは、次の引数を使用します。

* **`ns`**（必須、整数）：変換または書式設定する秒数です。
* **`tf`**（オプション、文字列）：秒を返す形式のタイプで、デフォルトは秒です。
   * 日単位の時間を求める場合には `"d"` に設定します（デフォルトでは最も近い 0.25 日刻みのベンチマーク値に丸められます）。
   * 時間単位の時間を求める場合には `"h"` に設定します（デフォルトでは最も近い 0.25 時間刻みのベンチマーク値に丸められます）。
   * 分単位の時間を求める場合には `"m"` に設定します（デフォルトでは最も近い 0.5 分刻みのベンチマーク値に丸められます）。
   * 秒単位の時間を求める場合には `"s"` に設定します（デフォルトでは最も近い 5 秒刻みのベンチマーク値に丸められます）。
* **`bml`**（オプション、数値）：丸めベンチマークの長さです。デフォルトでは、`tf` 引数にリストされたベンチマークです。

このメソッドは、`tf` 引数で指定した単位を使用して形式設定された秒数を返します。`tf` 引数が設定されていない場合：

* 1 分未満の値は、最も近い 5 秒刻みのベンチマーク値に丸められます。
* 1 分～1 時間の値は、最も近い 0.5 分刻みのベンチマーク値に丸められます。
* 1 時間～1 日の値は、最も近い 0.25 時間刻みのベンチマーク値に丸められます。
* 1 日を超える値は、最も近い 1 日刻みのベンチマーク値に丸められます。

## 例

### 例 1

次のコードは...

```js
s.eVar1 = s.formatTime(38242);
```

は s.eVar1 を「10.5 時間」に設定します。

渡された引数（38242 秒）は、10 時間 37 分 22 秒です。tf 引数がこの呼び出しに設定されておらず、経過秒数が 1 時間から 1 日の間にあるので、プラグインは最も近い 0.25 時間のベンチマークに変換された秒数を返します。

### 例 2

次のコードは...

```js
s.eVar1 = s.formatTime(38250);
```

は、s.eVar1 を「10.75 時間」に設定します。渡された引数（38250 秒）は、10 時間 37 分 30 秒です。この場合、最も近い 0.25 時間のベンチマークに渡された秒数を丸めると、最終値は 10.75 時間に設定されます。

### 例 3

次のコードは...

```js
s.eVar1 = s.formatTime(38242, "m");
```

は s.eVar1 を「637.5 分」に設定します。

この場合、「m」引数は、プラグインが最も近い 0.5 分のベンチマークに秒を変換するように強制します。

### 例 4

次のコードは...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

は s.eVar1 を「640 分」に設定します。

tf 引数値（「m」）は秒の分への返還を強制し、bml 引数値（20）は分の最も近い 20 分のベンチマークへの丸めを強制します。

### 例 5

次のコードは...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

は、s.eVar1 を「126 秒」に設定します。これは、125 秒に最も近い 2 秒のベンチマークです。

### 例 6

次のコードは...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

は、s.eVar1 を「3 分」に設定します。これは、125 秒に最も近い 3 分のベンチマークです。

### 例 7

次のコードは...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

は、s.eVar1 を 「2.4 分」に設定します。これは、145 秒に最も近い 0.4 分のベンチマークです（0.4 = 2/5）。

## バージョン履歴

### 1.1（2018 年 5 月 22 日）

* 丸めの柔軟性を高める `bml` 引数を追加しました。

### 1.0（2018 年 4 月 16 日）

* 初回リリース。
