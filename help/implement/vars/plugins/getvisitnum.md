---
title: getVisitNum
description: 訪問者の現在の訪問回数を追跡します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getVisitNum

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

プラ `getVisitNum` グインは、目的の日数内にサイトに来訪したすべての訪問者の訪問回数を返します。 Analysis Workspaceには、同様の機能を提供する「訪問回数」ディメンションが用意されています。 訪問回数の増加方法をより詳細に制御したい場合は、このプラグインを使用することをお勧めします。 Analysis Workspaceの組み込みの「訪問回数」ディメンションがレポートのニーズに十分な場合、このプラグインは不要です。

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
   * アクションタイプ：getVisitNumの初期化
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getVisitNum` ッドでは、次の引数を使用します。

* **`rp`** （オプション、整数または文字列）:訪問回数カウンターがリセットされるまでの日数。  未設定の場合 `365` の初期設定です。
   * この引数が指定さ `"w"`れている場合、カウンターは週の終わり（この土曜日の午後11:59）にリセットされます。
   * この引数が指定さ `"m"`れている場合、カウンターは月末（今月の最後の日）にリセットされます。
   * この引数が指定さ `"y"`れている場合、カウンターは年末（12月31日）にリセットされます。
* **`erp`** （オプション、ブール値）:引数が数 `rp` 値の場合、この引数は訪問回数の有効期限を延長する必要があるかどうかを指定します。 をに設定すると、サ `true`イトへの後続のヒットによって訪問回数カウンターがリセットされます。 をに設定すると、サ `false`イトへの後続のヒットは、訪問回数カウンターがリセットされたときに延長されません。 初期設定はで `true`す。 この引数は、引数が文字列の `rp` 場合は無効です。

訪問者がサイトに戻るたびに、30分間無操作状態が続くと訪問回数が増加します。 このメソッドを呼び出すと、訪問者の現在の訪問回数を表す整数が返されます。

このプラグインは、と呼ばれるファーストパーティCookieを設定し `"s_vnc[LENGTH]"` ます。 `[LENGTH]` は引数に渡される値を示し `rp` ます。 For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. cookieの値は、週末、月末、365日間の無操作状態の後など、訪問カウンターがリセットされた日を表すUnixタイムスタンプの組み合わせです。 また、現在の訪問回数も含まれます。 このプラグインは、という名前の別のcookieを設定し `"s_ivc"` ます。このcookieは、無操作状態が30分間続い `true` た後に有効期限切れになります。

## 呼び出しの例

### 例1

過去365日以内にサイトを訪問していない訪問者の場合、次のコードはs.prop1を1の値に設定します。

```js
s.prop1=s.getVisitNum();
```

### 例2

訪問者が最初の訪問から364日以内にサイトに戻った場合、次のコードではs.prop1を2に設定します。

```js
s.prop1=s.getVisitNum(365);
```

この訪問者が2回目の訪問から364日以内にサイトに戻った場合、次のコードはs.prop1を3に設定します。

```js
s.prop1=s.getVisitNum(365);
```

### 例3

訪問者が最初の訪問から179日以内にサイトに戻った場合、次のコードではs.prop1を2に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

ただし、この訪問者が2回目の訪問から1日以上経った後にサイトに戻った場合、次のコードではs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

呼び出しの2番目の引数がfalseの場合、訪問回数をいつ1にリセットするかを決定するルーチンは、訪問者がサイトを初めて訪問した後の「x」日間（この例では365日）を指定します。

2番目の引数がtrue（またはまったく設定されていない）の場合、プラグインは訪問者の無操作状態が「x」日間（この例では365日間）続いた後にのみ訪問回数を1にリセットします。

### 例4

現在の週（日曜日から始まる）の中で初めてサイトを訪問したすべての訪問者に対して、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum("w");
```

### 例5

現在の月の中で初めてサイトを訪問したすべての訪問者（各月の初日から始まる）に対し、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum("m");
```

getVisitNumプラグインでは、市販ベースのカレンダー（4-5-4、4-4-5など）は考慮されません。

### 例6

現在の年（1月1日から始まる）に初めてサイトを訪問したすべての訪問者に対して、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum("y");
```

### 例7

その週の訪問者の訪問回数、その月の訪問者の訪問回数、その年の訪問者の訪問回数を追跡する場合は、すべて異なるAnalytics変数内で、次のようなコードを使用する必要があります。

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

この場合、プラグインは3つの異なるcookie（異なる期間ごとに1つ）を作成し、期間ごとの個々の訪問回数を追跡します。

## バージョン履歴

### 4.11（2019年9月31日）

* 引数が明示的ににに設定さ `erp` れていた問題を修正しまし `false`た。

### 4.1（2018年5月22日）

* プラグイ `endOfDatePeriod` ンをv1.1に更新しました。

### 4.0（2018年4月18日）

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。
* プラグインが引数に基づいて動的にcookieを生成するようになったので、cookieの引数が削除され `rp` ました)。

### 3.0（2016年6月6日）

* 完全なオーバーホール
* 様々なバージョンのプラグインで使用可能な以前のすべてのソリューシ `getVisitNum` ョンを組み合わせました。
