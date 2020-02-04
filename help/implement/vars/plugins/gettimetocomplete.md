---
title: getTimeToComplete
description: タスクの完了に要した時間を測定します。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobeプラグイン：getTimeToComplete

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getTimeToComplete` ラグインは、ユーザーがサイト上でプロセスを完了するまでの時間を追跡します。 「時計」は、アクションが呼び出さ `start` れると開始し、アクションが呼び出され `stop` ると終了します。 サイトに完了までに時間がかかるワークフローがあり、訪問者が完了するまでにかかる時間を知りたい場合は、このプラグインを使用することをお勧めします。 精度が1秒にまで下がるので、サイト上のワークフローが短時間（3秒未満）かかる場合は、このプラグインを使用する必要はありません。

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

* **`sos`**（オプション、文字列）:タイマー`"start"`を開始するタイミングに設定します。 タイマー`"stop"`を停止する場合にに設定します。 初期設定はで`"start"`す。
* **`cn`**（オプション、文字列）:開始時間を保存するCookieの名前。 初期設定はで`"s_gttc"`す。
* **`exp`**（オプション、整数）:cookie（およびタイマー）の有効期限が切れる日数。 デフォルト`0`は、ブラウザーセッションの終わりを表します。

このメソッドを呼び出すと、との間にかかった日数、時間数、分数、秒数を含む文字列が返 `"start"` され `"stop"` ます。

## 呼び出しの例

### 例1

これらの呼び出しを使用して、訪問者がチェックアウトプロセスを開始してから購入するまでの時間を判断します。

訪問者がチェックアウトを開始したら、タイマーを開始します。

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

訪問者が購入を行ったらタイマーを停止し、prop1を停止と開始の時間差に設定します。

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1は、購入プロセスの完了に必要な時間を取り込みます。

### 例2

複数のタイマーを同時に（異なるプロセスを測定するために）実行させたい場合は、cn cookie引数を手動で設定する必要があります。  例えば、購入の完了に必要な時間を測定する場合は、次のコードを設定します。

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...ただし、登録フォームの記入に必要な時間を（同時に）測定する場合は、次のコードも実行します。

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

2つ目の例では、event1は登録プロセスの開始を取り込むためのもので、そのプロセスが完了するまでに最大7日かかる場合があります。event2は、登録の完了を取り込むためのものです。  s.prop2は、登録プロセスの完了に必要な時間を取得します。

## バージョン履歴

### 3.1（2019年9月30日）

* 最初の引数に「start」または「stop」の値を必要とするロジックを追加しました。  渡された他のすべての値は、プラグインの実行を停止します。
* プラグ `inList 2.0` インがに更新されまし `inList 2.1`た。

### 3.0（2018年8月24日）

* プラグイン `formatTime v1.0` がに更新されまし `formatTime v1.1`た。

### 3.0（2018年4月18日）

* ポイントリリース（再コンパイル、コードサイズが小さい）。
* マイナーな問題を修正しました。

### 2.0 2016年6月22日)

* プラグインへの依存 `p_fo` を排除。
* HコードおよびAppMeasurementとの互換性が追加されました。
* コンソールログを追加しました。
