---
title: getTimeToComplete
description: タスクの完了に要した時間を測定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getTimeToComplete

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getTimeToComplete` ラグインは、ユーザーがサイト上でプロセスを完了するまでに要する時間を追跡します。 「時計」は、アクションが呼び出さ `start` れた時点で始まり、アクションが呼び出さ `stop` れた時点で終わります。 サイトに完了までに少し時間がかかるワークフローがあり、訪問者が完了するまでにかかる時間を知りたい場合は、このプラグインの使用をお勧めします。 精度が1秒にまで下がるので、サイトのワークフローに短い時間（3秒未満）がかかる場合は、このプラグインを使用する必要はありません。

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
   * アクションタイプ：getTimeToCompleteの初期化
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getTimeToComplete` ッドでは、次の引数を使用します。

* **`sos`** （オプション、文字列）:タイマーを `"start"` 開始するタイミングに設定します。 タイマーを `"stop"` 停止するタイミングに設定します。 初期設定はで `"start"`す。
* **`cn`** （オプション、文字列）:開始時間を保存するCookieの名前。 初期設定はで `"s_gttc"`す。
* **`exp`** （オプション、整数）:cookie（およびタイマー）の有効期限が切れる日数。 初期設定 `0`は、ブラウザーセッションの終わりを表します。

このメソッドを呼び出すと、との間にかかった日数、時間数、分数、秒数を含む文字列が返さ `"start"` れ `"stop"` ます。

## 呼び出しの例

### 例1

これらの呼び出しを使用して、訪問者がチェックアウトプロセスを開始してから購入するまでの時間を判断します。

訪問者がチェックアウトを開始した時点でタイマーを開始します。

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

訪問者が購入を行ったらタイマーを停止し、prop1を停止と開始の時間差に設定します。

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1は、購入プロセスの完了に必要な時間を取り込みます。

### 例2

複数のタイマーを同時に（異なるプロセスを測定するために）実行したい場合は、cn cookie引数を手動で設定する必要があります。  例えば、購入の完了に必要な時間を測定する場合は、次のコードを設定します。

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...ただし、登録フォームの記入に必要な時間を（同時に）測定する場合は、次のコードも実行します。

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

2つ目の例では、event1は登録プロセスの開始を取り込むためのもので、このプロセスが完了するまでに最長7日かかり、どのような理由であれ、event2は登録の完了を取り込むためのものです。  s.prop2は、登録プロセスの完了に必要な時間を取り込みます。

## バージョン履歴

### 3.1（2019年9月31日）

* 最初の引数に「start」または「stop」の値を必要とするロジックを追加しました。  渡された他のすべての値は、プラグインの実行を停止します。
* にプラグ `inList 2.0` インを更新しまし `inList 2.1`た。

### 3.0（2018年8月24日）

* にプラグイ `formatTime v1.0` ンを更新しまし `formatTime v1.1`た。

### 3.0（2018年4月18日）

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。
* マイナーな問題を修正しました。

### 2.0 2016年6月22日)

* プラグインへの依存 `p_fo` を排除。
* HコードおよびAppMeasurementとの互換性を追加しました。
* コンソールログを追加しました。
