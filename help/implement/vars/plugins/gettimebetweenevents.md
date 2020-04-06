---
title: getTimeBetweenEvents
description: 2 つのイベントの間隔を測定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getTimeBetweenEvents

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getTimeBetweenEvents` プラグインを使用すると、買い物かごやカスタムイベントを含む、2 つの Analytics イベントの間の時間を追跡できます。これは、チェックアウトプロセスの完了に要する時間や、時間を測定する他のプロセスを追跡する場合に役立ちます。このプラグインは、時間を測定する必要があるコンバージョンプロセスがない場合には、必要ありません。

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
   * Action Type：Initialize getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeBetweenEvents` メソッドでは、次の引数を使用します。

* **`ste`**（必須、文字列）：タイマー開始イベント。Analytics「タイマー開始」イベントのコンマ区切りの文字列。
* **`rt`**（必須、ブール値）：タイマーの再開オプション。`events` 変数にタイマー開始イベントが含まれるたびにタイマーを再開する場合には、`true` に設定します。タイマー開始イベントが発生したときにタイマーを再開しない場合には、`false` に設定します。
* **`stp`**（必須、文字列）：タイマー停止イベント。Analytics「タイマー停止」イベントのコンマ区切りの文字列。
* **`res`**（必須、ブール値）：タイマーのリセットオプション。タイマーが開始してからの時間を記録し、停止した後にタイマーをリセットする場合には、`true` に設定します。時間を記録するが、タイマーを停止しない場合には、`false` に設定します。`false` に設定した場合、イベント変数が停止イベントを記録した後もタイマーは引き続き実行されます。
   > [!TIP] この引数を `false` に設定する場合は、`rte` 引数を設定することを強くお勧めします。
* **`cn`**（オプション、文字列）：最初のイベントの時刻が保存される Cookie 名。デフォルト値は `"s_tbe"` です。
* **`etd`**（オプション、整数）：Cookie の有効期限（日数）。ブラウザーセッションの終了時に期限切れにするには `0` に設定します。設定されていない場合のデフォルトは 1 日です。
* **`fmt`**（オプション、文字列）：秒数を返す時間の形式（デフォルトは何も返さない）
   * `"s"` 秒
   * `"m"` 分
   * `"h"` 時間
   * `"d"` 日
   * 設定されていない場合、戻り値の形式は次のルールに基づきます。
      * 1 分未満の値は、最も近い 5 秒刻みのベンチマーク値に丸められます。例：10 秒、15 秒
      * 1 分～1 時間の値は、最も近い 0.5 分刻みのベンチマーク値に丸められます。例：30.5 分、31 分
      * 1 時間～1 日の値は、最も近い 0.25 時間刻みのベンチマーク値に丸められます。例：2.25 時間、3.5 時間
      * 1 日を超える値は、最も近い 1 日刻みのベンチマーク値に丸められます。例：1 日、3 日、9 日
* **`bml`**（オプション、数値）：`fmt` 引数の形式に従った丸めベンチマークの長さ。例えば、`fmt` 引数が `"s"` でこの引数が `2` である場合、戻り値は最も近い 2 秒刻みのベンチマーク値に丸められます。`fmt` 引数が `"m"` でこの引数が `0.5` である場合、戻り値は最も近い 0.5 分刻みのベンチマーク値に丸められます。
* **`rte`**（オプション、文字列）：タイマーを削除または削除する Analytics イベントのコンマ区切りの文字列。デフォルト値は何もありません。

このメソッドを呼び出すと、タイマー開始イベントとタイマー停止イベントの間の時間を表す整数が目的の形式で返されます。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

次のように動作するように設定されています。

* タイマーは、s.events が event1 を含むと開始します。
* タイマーは、s.events が event1 を含むたびに再開します。
* タイマーは、s.events が event2 を含むと停止します。
* タイマーは、s.events が event2 を含むたびにリセット（0 秒に戻る）されます。
* タイマーは、s.events が event3 を含む場合や訪問者がブラウザーを閉じた場合にもリセットされます。
* event1 から event2 までの実際の時間が記録されると、プラグインは eVar1 を設定中の 2 つのイベントの間の秒数と同じ値に設定し、最も近い 2 秒のベンチマーク（0 秒、2 秒、4 秒、10 秒、184 秒など）に丸めます。
* タイマーが開始する前に s.events が event2 を含む場合、eVar1 は設定されません。

### 例 2

次のコードは...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

次のように動作するように設定されています。

* タイマーは、s.events が event1 を含むと開始します。
* タイマーは、s.events が event1 を含むたびに再開することはなく、元のタイマーが引き続き実行されます。
* タイマーは、s.events が event2 を含む場合に停止しませんが、プラグインは元の event1 設定が記録されてからの時間を記録します。
* タイマーは「s_20」という名前の Cookie に保存されます。
* タイマーは、s.events が event3 を含む場合、またはタイマーが開始してから 20 日が経過した場合にのみリセットされます。
* （元の）event1 から event2 までの時間が記録されると、プラグインは eVar1 を設定中の 2 つのイベントの間の時間数と同じ値に設定し、最も近い 1.5 時間のベンチマーク（0 時間、1.5 時間、3 時間、7.5 時間、478.5 時間など）に丸めます。

### 例 3

次のコードは...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

上の最初の例と同じ結果をもたらします。ただし、eVar1 の値は、タイマーの最終的な長さに応じて、秒、分、時間または日で返されます。また、このタイマーは、訪問者がブラウザーを閉じた時点ではなく、最初に設定された 1 日後に有効期限が切れます。

## バージョン履歴

### 2.1（2018 年 5 月 27 日）

* 新しいバージョンの `formatTime` プラグインに対しておこなわれた変更に対応します。

### 2.0（2018 年 4 月 7 日）

* プラグインの完全な書き換えと再分析。
