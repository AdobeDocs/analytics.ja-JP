---
title: getVisitNum
description: 訪問者の現在の訪問回数を追跡します。
feature: Appmeasurement Implementation
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 76%

---

# アドビプラグイン：getVisitNum

{{plug-in}}

`getVisitNum` プラグインは、目的の日数内にサイトに来訪したすべての訪問者の訪問回数を返します。Analysis Workspace には、同様の機能を提供する「訪問回数」ディメンションが用意されています。訪問回数の増分方法をより詳細に制御する場合は、このプラグインを使用することをお勧めします。Analysis Workspace のビルトインの「訪問回数」ディメンションがレポートのニーズに十分な場合、このプラグインは不要です。

## Web SDK拡張機能を使用したプラグインのインストール

Adobeには、web SDKで最も一般的に使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の **[!UICONTROL タグ]** をクリックしてから、目的のタグプロパティをクリックします。
1. 左側の **[!UICONTROL 拡張機能]** をクリックしてから、「**[!UICONTROL カタログ]**」タブをクリックします
1. **[!UICONTROL Common Web SDK Plugins]** 拡張機能を見つけてインストールします。
1. 左側の **[!UICONTROL データ要素]** をクリックしてから、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張機能：Common Web SDK Plugins
   * データ要素：`getVisitNum`
1. 必要なパラメーターを右側に設定します。
1. 変更を保存してデータ要素に公開します。

## Web SDKを手動で実装するプラグインのインストール

このプラグインは、web SDKの手動実装内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用してプラグインをインストールします

Adobeには、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getVisitNum
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getVisitNum` 関数は次の引数を使用します。

* **`rp`**（オプション、整数または文字列）：訪問回数カウンターがリセットされるまでの日数です。未設定の場合のデフォルト値は `365` です。
   * この引数を `"w"` にすると、カウンターは週末（この土曜日の午後 11:59）にリセットされます
   * この引数が `"m"` に指定されている場合、カウンターは月の終わり（今月の最終日）にリセットされます。
   * この引数が `"y"` に指定されている場合、カウンターは年の終わり（12 月 31 日）にリセットされます。
* **`erp`**（オプション、ブール値）：`rp` 引数が数値の場合、この引数は訪問回数の有効期限を延長する必要があるかどうかを指定します。`true` に設定した場合、サイトへの後続のヒットによって訪問回数カウンターがリセットされます。`false` に設定した場合、サイトへの後続のヒットは、訪問回数カウンターがリセットされたときに延長されません。デフォルト値は `true` です。この引数は、`rp` 引数が文字列の場合は無効です。

無操作状態が 30 分間続いたあとで訪問者がサイトに戻るたびに、訪問回数が増加します。この関数を呼び出すと、訪問者の現在の訪問回数を表す整数が返されます。

このプラグインは、「`"s_vnc[LENGTH]"`」というファーストパーティ Cookie を設定します。ここで、`[LENGTH]` は `rp` 引数に渡された値です。例：`"s_vncw"`、`"s_vncm"`、`"s_vnc365"`。Cookie の値は、週末、月末、無操作状態が 365 日間続いた後など、訪問カウンターがリセットされた日時を表す Unix タイムスタンプの組み合わせです。また、現在の訪問回数も含まれます。このプラグインは、無操作状態が 30 分間続くと `true` に設定されて有効期限が切れる、「`"s_ivc"`」Cookie を設定します。

## 例

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## バージョン履歴

### 4.2（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 4.11（2019 年 9 月 30 日（PT））

* `erp` 引数が明示的に `false` に設定されていた問題を修正しました。

### 4.1（2018 年 5 月 21 日（PT））

* `endOfDatePeriod` プラグインを v1.1 に更新しました。

### 4.0（2018 年 4 月 17 日（PT））

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* プラグインが `rp` 引数に基づいて動的に Cookie を生成するようになったので、cookie 引数を削除しました。

### 3.0（2016 年 6 月 5 日（PT））

* 完全なオーバーホール。
* `getVisitNum` プラグインの様々なバージョンで使用可能な以前のすべてのソリューションを組み合わせました。
