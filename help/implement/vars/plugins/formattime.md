---
title: formatTime
description: 秒数を分単位、時間単位などで同等の値に変換します。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobeプラグイン：formatTime

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `formatTime` ラグインを使用すると、任意の秒数を費やして、目的のベンチマーク値に丸めてグループ形式で表示できます。 秒単位で時間値を取得し、バケット形式（分、日、週など）に変換する場合は、このプラグインを使用することをお勧めします。 2番目の値を時間で四捨五入したい場合は、このプラグインは不要です。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
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
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

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

* **`ns`**（必須、整数）:変換または書式設定する秒数
* **`tf`**（オプション、文字列）:秒を返す形式のタイプ。デフォルトは秒です。
   * 日単位の時 `"d"` 間を求める場合に設定します（デフォルトで最も近い1/4日のベンチマークに丸められます）。
   * 時間単位 `"h"` で時間を計算する場合に設定します（デフォルトで最も近い1/4時間のベンチマークに丸められます）。
   * 時間を分 `"m"` 単位で指定する場合に設定します（デフォルトで最も近い1/2分のベンチマークに丸められます）。
   * 時間を秒単位 `"s"` で指定する場合に設定します（デフォルトで最も近い5秒のベンチマークに丸められます）。
* **`bml`**（オプション、数値）:丸めベンチマークの長さ。 デフォルトでは、引数にリストされたベンチマー`tf`ク

このメソッドは、引数で指定した単位を使用して形式設定された秒数を返し `tf` ます。 引数が設定さ `tf` れていない場合：

* 1分未満の値は、最も近い5秒のベンチマークに丸められます。
* 1分から1時間の間のものは、最も近い1/2分のベンチマークに丸められます。
* 1時間から1日の間のものは、最も近い四半期のベンチマークに丸められます。
* 1日より大きい値は、最も近い日のベンチマークに丸められます。

## 例

### 例1

次のコード…

```js
s.eVar1 = s.formatTime(38242);
```

...はs.eVar1を「10.5時間」に設定します。

渡される引数（38242秒）は、10時間、37分、22秒です。  tf引数がこの呼び出しに設定されておらず、経過秒数が1時間から1日の間にあるので、プラグインは最も近い四半期のベンチマークに変換された秒数を返します。

### 例2

次のコード…

```js
s.eVar1 = s.formatTime(38250);
```

...は、s.eVar1を「10.75時間」に設定します。渡される引数（38250秒）は、10時間、37分、30秒に等しくなります。  この場合、最も近い四半期 — 時間ベンチマークに渡された秒数を丸めると、最終値は10.75時間に設定されます

### 例3

次のコード…

```js
s.eVar1 = s.formatTime(38242, "m");
```

...はs.eVar1を「637.5分」に設定します。

この場合、&quot;m&quot;引数は、プラグインが最も近い1/2分のベンチマークに秒を変換するように強制します

### 例4

次のコード…

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...はs.eVar1を「640分」に設定します。

tf引数値(&quot;m&quot;)は、プラグインに秒を強制的に分に変換させますが、bml引数値(20)も、プラグインに最も近い20分のベンチマークに分を強制的に変換させます。

### 例5

次のコード…

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...は、s.eVar1を「126秒」に設定します。これは、125秒に最も近い2秒のベンチマークです。

### 例6

次のコード…

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...は、s.eVar1を「3分」に設定します。これは、125秒に最も近い3分のベンチマークです。

### 例7

次のコード…

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...は、s.eVar1を「2.4分」に設定します。これは、最も近い2/5分のベンチマーク(例：.4 = 2/5) ～ 145秒

## バージョン履歴

### 1.1（2018年5月22日）

* 丸めの柔軟性 `bml` を高める引数を追加しました。

### 1.0（2018年4月16日）

* 初期リリース。
