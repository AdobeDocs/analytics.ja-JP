---
title: getVisitNum
description: 訪問者の現在の訪問回数を追跡します。
translation-type: tm+mt
source-git-commit: fb1cdcb53732be46037a79587fc2541e629496e3
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 99%

---


# アドビプラグイン：getVisitNum

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getVisitNum` プラグインは、目的の日数内にサイトに来訪したすべての訪問者の訪問回数を返します。Analysis Workspace には、同様の機能を提供する「訪問回数」ディメンションが用意されています。訪問回数の増分方法をより詳細に制御する場合は、このプラグインを使用することをお勧めします。Analysis Workspace 組み込みの「訪問回数」ディメンションがレポートのニーズに十分な場合、このプラグインは不要です。

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
   * Action Type：Initialize getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
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

### 4.2（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 4.11（2019 年 10 月 1 日）

* `erp` 引数が明示的に `false` に設定されていた問題を修正しました。

### 4.1（2018 年 5 月 22 日）

* `endOfDatePeriod` プラグインを v1.1 に更新しました。

### 4.0（2018 年 4 月 18 日）

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* プラグインが `rp` 引数に基づいて動的に Cookie を生成するようになったので、cookie 引数を削除しました。

### 3.0（2016 年 6 月 6 日）

* 完全なオーバーホール。
* `getVisitNum` プラグインの様々なバージョンで使用可能な以前のすべてのソリューションを組み合わせました。
