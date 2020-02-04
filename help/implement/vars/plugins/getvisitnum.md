---
title: getVisitNum
description: 訪問者の現在の訪問回数を追跡します。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobeプラグイン：getVisitNum

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

プラ `getVisitNum` グインは、目的の日数内にサイトに来訪したすべての訪問者の訪問回数を返します。 Analysis Workspaceには、同様の機能を提供する「訪問回数」ディメンションが用意されています。 訪問回数の増分方法をより詳細に制御する場合は、このプラグインを使用することをお勧めします。 Analysis Workspaceの組み込みの「訪問回数」ディメンションが、レポートのニーズに十分な場合、このプラグインは不要です。

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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getVisitNum` ッドでは、次の引数を使用します。

* **`rp`**（オプション、整数または文字列）:訪問回数カウンターがリセットされるまでの日数。  未設定の場`365`合はデフォルトです。
   * この引数が指定さ `"w"`れている場合、カウンターは週の終わり（この土曜日の午後11:59）にリセットされます。
   * この引数が指定さ `"m"`れている場合、カウンターは月末（今月の最終日）にリセットされます。
   * この引数が指定さ `"y"`れている場合、カウンターは年の終わり（12月31日）にリセットされます。
* **`erp`**（オプション、ブール値）:引数が数`rp`値の場合、この引数は訪問回数の有効期限を延長する必要があるかどうかを指定します。 に設定した場合、サ`true`イトへの後続のヒットによって訪問回数カウンターがリセットされます。 に設定した場合、サ`false`イトへの後続のヒットは、訪問回数カウンターがリセットされたときに延長されません。 初期設定はで`true`す。 この引数は、引数が文字列の場合`rp`は無効です。

訪問者がサイトに戻るたびに、30分間無操作状態が続くと訪問回数が増加します。 このメソッドを呼び出すと、訪問者の現在の訪問回数を表す整数が返されます。

このプラグインは、引数に渡される値を、と呼び `"s_vnc[LENGTH]"` 出すフ `[LENGTH]` ァーストパーティcookieを設定し `rp` ます。 For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. cookieの値は、週末、月末、365日間無操作状態が続いた後など、訪問カウンターがリセットされた日時を表すUnixタイムスタンプの組み合わせです。 また、現在の訪問回数も含まれます。 このプラグインは、30分間無操作状態が続くと有 `"s_ivc"` 効期限が切れ、に設 `true` 定された別のcookieを設定します。

## 呼び出しの例

### 例1

過去365日以内にサイトを訪問していない訪問者の場合、次のコードはs.prop1を1の値に設定します。

```js
s.prop1=s.getVisitNum();
```

### 例2

訪問者が初回訪問から364日以内にサイトに戻った場合、次のコードはs.prop1を2に設定します。

```js
s.prop1=s.getVisitNum(365);
```

この訪問者が2回目の訪問から364日以内にサイトに戻った場合、次のコードはs.prop1を3に設定します。

```js
s.prop1=s.getVisitNum(365);
```

### 例3

訪問者が初回訪問から179日以内にサイトに戻った場合、次のコードはs.prop1を2に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

ただし、この訪問者が2回目の訪問から1日以上サイトに戻った場合、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum(180,false);
```

呼び出しの2番目の引数がfalseの場合、訪問回数を「リセット」して1にする必要があるかを決定するルーチンは、訪問者がサイトを初めて訪問した後365日後の「x」日間（この例では365日間）を指定します。

2番目の引数がtrueの場合（または設定されていない場合）、プラグインは訪問者が無操作状態である（この例では365日間）の「x」日間の経過後にのみ訪問回数を1にリセットします。

### 例4

現在の週（日曜日から始まる）に初めてサイトを訪問したすべての訪問者に対して、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum("w");
```

### 例5

現在の月の中で初めてサイトを訪問したすべての訪問者（各月の初日から始まる）に対して、次のコードはs.prop1を1に設定します。

```js
s.prop1=s.getVisitNum("m");
```

getVisitNumプラグインでは、小売ベースのカレンダー（例：4-5-4、4-4-5など）は考慮されません。

### 例6

1月1日から始まる今年の中で初めてサイトを訪問したすべての訪問者に対して、次のコードはs.prop1を1に設定します。

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

### 4.11（2019年9月30日）

* 引数が明示的ににに設定さ `erp` れていた問題を修正しまし `false`た。

### 4.1（2018年5月22日）

* プラグイン `endOfDatePeriod` をv1.1に更新しました。

### 4.0（2018年4月18日）

* ポイントリリース（再コンパイル、コードサイズが小さい）。
* プラグインが引数に基づいて動的にcookieを生成するようになったので、cookieの引数が削除され `rp` ました)。

### 3.0（2016年6月6日）

* 完全なオーバーホール
* 様々なバージョンのプラグインで使用可能な以前のすべてのソリューシ `getVisitNum` ョンを組み合わせました。
