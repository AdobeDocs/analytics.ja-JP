---
title: getTimeBetweenEvents
description: 2 つのイベントの間隔を測定します。
translation-type: tm+mt
source-git-commit: e8c6f4bbc72f7edfd966d698b8e4678e5eaa739e
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 99%

---


# アドビプラグイン：getTimeBetweenEvents

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getTimeBetweenEvents` プラグインを使用すると、買い物かごやカスタムイベントを含む、2 つの Analytics イベントの間の時間を追跡できます。これは、チェックアウトプロセスの完了に要する時間や、時間を測定する他のプロセスを追跡する場合に役立ちます。このプラグインは、時間を測定する必要があるコンバージョンプロセスがない場合には、必要ありません。

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
   * Action Type：Initialize getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeBetweenEvents` メソッドでは、次の引数を使用します。

* **`ste`**（必須、文字列）：タイマー開始イベント。Analytics「タイマー開始」イベントのコンマ区切りの文字列。
* **`rt`**（必須、ブール値）：タイマーの再開オプション。`events` 変数にタイマー開始イベントが含まれるたびにタイマーを再開する場合には、`true` に設定します。タイマー開始イベントが発生したときにタイマーを再開しない場合には、`false` に設定します。
* **`stp`**（必須、文字列）：タイマー停止イベント。Analytics「タイマー停止」イベントのコンマ区切りの文字列。
* **`res`**（必須、ブール値）：タイマーのリセットオプション。タイマーが開始してからの時間を記録し、停止した後にタイマーをリセットする場合には、`true` に設定します。時間を記録するが、タイマーを停止しない場合には、`false` に設定します。`false` に設定した場合、イベント変数が停止イベントを記録した後もタイマーは引き続き実行されます。

   >[!TIP]
   >
   > この引数を `false` に設定する場合は、`rte` 引数を設定することを強くお勧めします。
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
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
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
s.eVar1 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
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
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true);
```

上の最初の例と同じ結果をもたらします。ただし、eVar1 の値は、タイマーの最終的な長さに応じて、秒、分、時間または日で返されます。また、このタイマーは、訪問者がブラウザーを閉じた時点ではなく、最初に設定された 1 日後に有効期限が切れます。

## バージョン履歴

### 3.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 2.1（2018 年 5 月 27 日）

* 新しいバージョンの `formatTime` プラグインに対しておこなわれた変更に対応します。

### 2.0（2018 年 4 月 7 日）

* プラグインの完全な書き換えと再分析。
