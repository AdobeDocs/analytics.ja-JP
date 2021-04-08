---
title: formatTime
description: 秒数を分単位、時間単位などで同等の値に変換します。
translation-type: ht
source-git-commit: 56b21b6acb948c478d7b2a29c3e8375a8fe77ce2
workflow-type: ht
source-wordcount: '824'
ht-degree: 100%

---


# アドビプラグイン：formatTime

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`formatTime` プラグインを使用すると、任意の秒数を、目的のベンチマーク値に丸めてグループ形式で表示できます。秒単位で時間値を取得し、バケット形式（分、日、週など）に変換する場合は、このプラグインを使用することをお勧めします。秒単位の値を時間で丸める場合は、このプラグインは不要です。

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
   * Action Type：Initialize formatTime
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
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
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

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.1（2018 年 5 月 21 日（PT））

* 丸めの柔軟性を高める `bml` 引数を追加しました。

### 1.0（2018 年 4 月 15 日（PT））

* 初回リリース。
