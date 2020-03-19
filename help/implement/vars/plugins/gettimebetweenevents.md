---
title: getTimeBetweenEvents
description: 2つのイベントの間隔を測定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getTimeBetweenEvents

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getTimeBetweenEvents` ラグインを使用すると、買い物かごやカスタムイベントを含む、2つのAnalyticsイベントの間の時間を追跡できます。 チェックアウトプロセスの完了に要する時間や、時間を測定する他のプロセスを追跡する場合に役立ちます。 このプラグインは、コンバージョンプロセスがない場合に、そのプロセスの時間を測定する必要がありません。

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
   * アクションタイプ：getTimeBetweenEventsの初期化
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getTimeBetweenEvents` ッドでは、次の引数を使用します。

* **`ste`** （必須、文字列）:タイマーイベントを開始します。 「タイマーを開始」するAnalyticsイベントのコンマ区切りの文字列。
* **`rt`** （必須、ブール値）:タイマーの再起動オプション。 変数に開始タ `true` イマーイベントが含まれるたびにタイマーを再 `events` 起動する場合にに設定します。 開始タイ `false` マーイベントが発生したときにタイマーを再起動しない場合にに設定します。
* **`stp`** （必須、文字列）:タイマーイベントを停止します。 「タイマーを停止」するAnalyticsイベントのコンマ区切りの文字列。
* **`res`** （必須、ブール値）:タイマーのリセットオプション。 タイマーが `true` 開始してからの時間を記録し、停止した後にタイマーをリセットする場合にに設定します。 時間を記録 `false` するが、タイマーを停止しない場合にに設定します。 に設定した場合、イベ `false`ント変数が停止イベントを記録した後もタイマーは引き続き実行されます。
   > [!TIP] この引数をに設定する場合は、 `false`以下の引数を `rte` 設定することを強くお勧めします。
* **`cn`** （オプション、文字列）:最初のイベントの時刻が保存されるcookieの名前。 初期設定はで `"s_tbe"`す。
* **`etd`** （オプション、整数）:cookieの有効期限（日数）。 ブラウザーセ `0` ッションの終了時に有効期限切れになるように設定します。 未設定の場合、デフォルトは1日です。
* **`fmt`** （オプション、文字列）:秒数が返される時間の形式（デフォルトは何も返されません）
   * `"s"` 数秒間
   * `"m"` 数分間
   * `"h"` 何時間も
   * `"d"` 何日も
   * 設定しない場合、戻り値の形式は次のルールに基づきます。
      * 1分未満の場合は、最も近い5秒のベンチマークに丸められます。 例：10秒、15秒
      * 1分から1時間の間の値は、最も近い1/2分のベンチマークに丸められます。 例：30.5分31分
      * 1時間から1日の間のすべての指標は、最も近い四半期のベンチマークに丸められます。 例：2.25時間、3.5時間
      * 1日より大きいものは、最も近い日のベンチマークに丸められます。 例：1日、3日、9日
* **`bml`** （オプション、数値）:引数の形式に従った丸めベンチマークの長 `fmt` さ。 例えば、引数がで、こ `fmt` の引数が `"s"` 指定されている場合、 `2`戻り値は最も近い2秒のベンチマークに丸められます。 引数が `fmt` で、こ `"m"` の引数が `0.5`指定されている場合、戻り値は最も近い半分のベンチマークに丸められます。
* **`rte`** （オプション、文字列）:タイマーを削除または削除するAnalyticsイベントのコンマ区切りの文字列。 初期設定はなしです。

このメソッドを呼び出すと、開始タイマーイベントと停止タイマーイベントの間の時間を目的の形式で表す整数が返されます。

## 呼び出しの例

### 例1

次のコード…

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...が次のように設定されている場合、

* タイマーは、s.eventsにevent1が含まれると開始します。
* タイマーは、s.eventsがevent1を含むたびに再起動します。
* s.eventsにevent2が含まれる場合、タイマーは停止します。
* タイマーは、s.eventsがevent2を含むたびにリセット（0秒に戻る）されます。
* また、s.eventsにevent3が含まれる場合、または訪問者がブラウザーを閉じた場合にも、タイマーがリセットされます
* event1からevent2までの実際の時間が記録されると、プラグインはeVar1を、2つのイベントの間の秒数と同じ値に設定し、最も近い2秒のベンチマーク（0秒、2秒、4秒、10秒、184秒など）に丸めます。
* タイマーが開始する前にs.eventsにevent2が含まれている場合、eVar1は設定されません。

### 例2

次のコード…

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...が次のように設定されている場合、

* タイマーは、s.eventsにevent1が含まれると開始します。
* s.eventsがevent1を含むたびにタイマーが再起動することはなく、元のタイマーは引き続き実行されます
* s.eventsにevent2が含まれている場合、タイマーは停止しませんが、プラグインは元のevent1設定が記録されてからの時間を記録します
* タイマーは「s_20」という名前のcookieに保存されます。
* タイマーは、s.eventsにevent3が含まれている場合、またはタイマーが起動してから20日が経過した場合にのみリセットされます
* （元の）event1とevent2の間の時間が記録されると、プラグインはeVar1を、2つのイベントの間の時間数と同じに設定し、最も近い1/2時間のベンチマーク（0時間、1.5時間、3時間、7.5時間、478.5時間など）に丸めます。

### 例3

次のコード…

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...上の最初の例と同じ結果が得られます。ただし、eVar1の値は、タイマーの最終的な長さに応じて、秒、分、時間または日単位で返されます。  また、訪問者がブラウザーを閉じた時点ではなく、最初に設定された日から1日間、タイマーの有効期限が切れます。

## バージョン履歴

### 2.1（2018年5月26日）

* 新しいバージョンのプラグインに対して行われた変 `formatTime` 更に対応します。

### 2.0（2018年4月6日）

* プラグインの完全な書き換え/再分析。
