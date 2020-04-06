---
title: getVisitNum
description: 訪問者の現在の訪問回数を追跡します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getVisitNum

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getVisitNum` プラグインは、目的の日数内にサイトに来訪したすべての訪問者の訪問回数を返します。Analysis Workspace には、同様の機能を提供する「訪問回数」ディメンションが用意されています。訪問回数の増分方法をより詳細に制御する場合は、このプラグインを使用することをお勧めします。Analysis Workspace 組み込みの「訪問回数」ディメンションがレポートのニーズに十分な場合、このプラグインは不要です。

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
   * Action Type：Initialize getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getVisitNum` メソッドでは、次の引数を使用します。

* **`rp`**（オプション、整数または文字列）：訪問回数カウンターがリセットされるまでの日数です。未設定の場合のデフォルト値は `365` です。
   * この引数が `"w"` に指定されている場合、カウンターは週の終わり（この土曜日の午後 11:59）にリセットされます。
   * この引数が `"m"` に指定されている場合、カウンターは月の終わり（今月の最終日）にリセットされます。
   * この引数が `"y"` に指定されている場合、カウンターは年の終わり（12 月 31 日）にリセットされます。
* **`erp`**（オプション、ブール値）：`rp` 引数が数値の場合、この引数は訪問回数の有効期限を延長する必要があるかどうかを指定します。`true` に設定した場合、サイトへの後続のヒットによって訪問回数カウンターがリセットされます。`false` に設定した場合、サイトへの後続のヒットは、訪問回数カウンターがリセットされたときに延長されません。デフォルト値は `true` です。この引数は、`rp` 引数が文字列の場合は無効です。

無操作状態が 30 分間続いたあとで訪問者がサイトに戻るたびに、訪問回数が増加します。このメソッドを呼び出すと、訪問者の現在の訪問回数を表す整数が返されます。

このプラグインは、「`"s_vnc[LENGTH]"`」というファーストパーティ Cookie を設定します。ここで、`[LENGTH]` は `rp` 引数に渡された値です。例：`"s_vncw"`、`"s_vncm"`、`"s_vnc365"`。Cookie の値は、週末、月末、無操作状態が 365 日間続いた後など、訪問カウンターがリセットされた日時を表す Unix タイムスタンプの組み合わせです。また、現在の訪問回数も含まれます。このプラグインは、無操作状態が 30 分間続くと `true` に設定されて有効期限が切れる、「`"s_ivc"`」Cookie を設定します。

## 呼び出しの例

### 例 1

過去 365 日以内にサイトを訪問していない訪問者の場合、次のコードは s.prop1 を 1 の値に設定します。

```js
s.prop1=s.getVisitNum();
```

### 例 2

訪問者が初回訪問から 364 日以内にサイトに戻った場合、次のコードは s.prop1 を 2 に設定します。

```js
s.prop1=s.getVisitNum(365);
```

この訪問者が 2 回目の訪問から 364 日以内にサイトに戻った場合、次のコードは s.prop1 を 3 に設定します。

```js
s.prop1=s.getVisitNum(365);
```

### 例 3

訪問者が初回訪問から 179 日以内にサイトに戻った場合、次のコードは s.prop1 を 2 に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

ただし、この訪問者が 2 回目の訪問から 1 日以上たってからサイトに戻った場合、次のコードは s.prop1 を 1 に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

呼び出しの 2 番目の引数が false の場合、訪問回数を「リセット」して 1 にするタイミングを決定するルーチンは、訪問者がサイトを初めて訪問した「x」日（この例では 365 日）後に、訪問回数を 1 にリセットします。

2 番目の引数が true の場合（または設定されていない場合）、訪問者が「x」日間（この例では 365 日間）で無操作状態であった後にのみ訪問回数を 1 にリセットします。

### 例 4

現在の週（日曜日から始まる）で初めてサイトを訪問したすべての訪問者に対して、次のコードは s.prop1 を 1 に設定します。

```js
s.prop1=s.getVisitNum("w");
```

### 例 5

今月（各月の初日から始まる）で初めてサイトを訪問したすべての訪問者に対して、次のコードは s.prop1 を 1 に設定します。

```js
s.prop1=s.getVisitNum("m");
```

getVisitNum プラグインでは、小売ベースのカレンダー（例：4-5-4、4-4-5 など）は考慮しません。

### 例 6

（1 月 1 日から始まる）今年初めてサイトを訪問したすべての訪問者に対して、次のコードは s.prop1 を 1 に設定します。

```js
s.prop1=s.getVisitNum("y");
```

### 例 7

その週の訪問者の訪問回数、その月の訪問者の訪問回数、その年の訪問者の訪問回数を追跡する場合は、すべて異なる Analytics 変数内で、次のようなコードを使用する必要があります。

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

この場合、プラグインは 3 つの異なる Cookie（異なる期間ごとに 1 つ）を作成し、期間ごとの個々の訪問回数を追跡します。

## バージョン履歴

### 4.11（2019 年 10 月 1 日）

* `erp` 引数が明示的に `false` に設定されていた問題を修正しました。

### 4.1（2018 年 5 月 22 日）

* `endOfDatePeriod` プラグインを v1.1 に更新しました。

### 4.0（2018 年 4 月 18 日）

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* プラグインが `rp` 引数に基づいて動的に Cookie を生成するようになったので、cookie 引数を削除しました。

### 3.0（2016 年 6 月 6 日）

* 完全なオーバーホール
* `getVisitNum` プラグインの様々なバージョンで使用可能な以前のすべてのソリューションを組み合わせました。
