---
title: formatTime
description: 秒数を分単位、時間単位などで同等の値に変換します。
feature: Variables
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 97%

---

# アドビプラグイン：formatTime

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`formatTime` プラグインを使用すると、任意の秒数を、目的のベンチマーク値に丸めてグループ形式で表示できます。秒単位で時間値を取得し、バケット形式（分、日、週など）に変換する場合は、このプラグインを使用することをお勧めします。秒単位の値を時間で丸める場合は、このプラグインは不要です。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize formatTime
1. Save and publish the changes to the rule.-->

## カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
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

`formatTime` 関数は次の引数を使用します。

* **`ns`**（必須、整数）：変換または書式設定する秒数です。
* **`tf`**（オプション、文字列）：秒を返す形式のタイプで、デフォルトは秒です。
   * 日単位の時間を求める場合には `"d"` に設定します（デフォルトでは最も近い 0.25 日刻みのベンチマーク値に丸められます）。
   * 時間単位の時間を求める場合には `"h"` に設定します（デフォルトでは最も近い 0.25 時間刻みのベンチマーク値に丸められます）。
   * 分単位の時間を求める場合には `"m"` に設定します（デフォルトでは最も近い 0.5 分刻みのベンチマーク値に丸められます）。
   * 秒単位の時間を求める場合には `"s"` に設定します（デフォルトでは最も近い 5 秒刻みのベンチマーク値に丸められます）。
* **`bml`**（オプション、数値）：丸めベンチマークの長さです。デフォルトでは、`tf` 引数にリストされたベンチマークです。

この関数は、`tf` 引数で指定した単位を使用して形式設定された秒数を返します。`tf` 引数が設定されていない場合：

* 1 分未満の値は、最も近い 5 秒刻みのベンチマーク値に丸められます。
* 1 分～1 時間の値は、最も近い 0.5 分刻みのベンチマーク値に丸められます。
* 1 時間～1 日の値は、最も近い 0.25 時間刻みのベンチマーク値に丸められます。
* 1 日を超える値は、最も近い 1 日刻みのベンチマーク値に丸められます。

## 例

```js
// Sets eVar1 to "10.5 hours".
// 38242 seconds equals 10 hours, 37 minutes, and 22 seconds. Since the tf argument is not set, the value returned is the number of seconds converted to the nearest quarter-hour benchmark.
s.eVar1 = formatTime(38242);

// Sets eVar4 to "10.75 hours".
// 38250 seconds equals 10 hours, 37 minutes, and 30 seconds. This value rounds up to the nearest quarter hour.
s.eVar4 = formatTime(38250);

// Sets eVar9 to "637.5 minutes".
s.eVar9 = formatTime(38242, "m");

// Sets eVar14 to "640 minutes".
// The tf argument forces the returned value to minutes, while the bml argument forces the value to the nearest 20-minute increment.
s.eVar14 = formatTime(38242, "m", 20);

// Sets eVar2 to "126 seconds", the closest 2-second benchmark to 125 seconds.
s.eVar2 = formatTime(125, "s", 2);

// Sets eVar7 to "3 minutes", the closest 3-minute benchmark to 125 seconds.
s.eVar7 = formatTime(125, "m", 3);

// Sets eVar55 to "2.4 minutes, the closest 2/5-minute benchmark to 145 seconds.
s.eVar55 = formatTime(145, "m", .4);
```

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.1（2018 年 5 月 21 日（PT））

* 丸めの柔軟性を高める `bml` 引数を追加しました。

### 1.0（2018 年 4 月 15 日（PT））

* 初回リリース。
