---
title: getTimeToComplete
description: タスクの完了に要した時間を測定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getTimeToComplete

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getTimeToComplete` プラグインは、ユーザーがサイト上でプロセスを完了するまでの時間を追跡します。「時計」は、`start` アクションが呼び出されると開始し、`stop` アクションが呼び出されると終了します。サイトに完了までに時間がかかるワークフローがあり、訪問者が完了するまでにかかる時間を知りたい場合は、このプラグインを使用することをお勧めします。精度は最高でも 1 秒なので、サイト上のワークフローが短時間（3 秒未満）しかかからない場合は、このプラグインを使用する必要はありません。

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
   * Action Type：Initialize getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeToComplete` メソッドでは、次の引数を使用します。

* **`sos`**（オプション、文字列）：`"start"` をタイマーを開始する時に設定します。`"stop"` をタイマーを停止する時に設定します。デフォルト値は `"start"` です。
* **`cn`**（オプション、文字列）：開始時間を保存する Cookie の名前です。デフォルト値は `"s_gttc"` です。
* **`exp`**（オプション、整数）：Cookie（およびタイマー）の有効期限が切れる日数です。デフォルトは `0` で、ブラウザーセッションの終わりを表します。

このメソッドを呼び出すと、`"start"` と `"stop"` の間にかかった日数、時間数、分数、秒数を含む文字列が返されます。

## 呼び出しの例

### 例 1

これらの呼び出しを使用して、訪問者がチェックアウトプロセスを開始してから購入するまでの時間を判断します。

訪問者がチェックアウトを開始したら、タイマーを開始します。

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

訪問者が購入をおこなったらタイマーを停止し、prop1 を停止と開始の時間差に設定します。

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 は、購入プロセスの完了に必要な時間を取り込みます。

### 例 2

複数のタイマーを同時に（異なるプロセスを測定するために）実行させたい場合は、cn Cookie 引数を手動で設定する必要があります。例えば、購入の完了に必要な時間を測定する場合は、次のコードを設定します。

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

ただし、登録フォームの記入に必要な時間を（同時に）測定する場合は、次のコードも実行します。

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

2 つ目の例では、event1 は登録プロセスの開始を取り込むためのもので、そのプロセスが完了するまでに最大 7 日かかる場合があります。event2 は、登録の完了を取り込むためのものです。s.prop2 は、登録プロセスの完了に必要な時間を取得します。

## バージョン履歴

### 3.1（2019 年 10 月 1 日）

* 最初の引数に「start」または「stop」の値を必要とするロジックを追加しました。渡された他のすべての値は、プラグインの実行を停止します。
* `inList 2.0` プラグインを `inList 2.1` に更新しました。

### 3.0（2018 年 8 月 24 日）

* `formatTime v1.0` プラグインを `formatTime v1.1` に更新しました。

### 3.0（2018 年 4 月 18 日）

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* マイナーな問題を修正しました。

### 2.0（2016 年 6 月 22 日）

* `p_fo` プラグインへの依存を排除しました。
* H コードおよび AppMeasurement との互換性を追加しました。
* コンソールログを追加しました。
