---
title: ナンバースイート
description: 他のJavaScript変数で使用する数値を生成および操作します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：ナンバースイート

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

数値スイートは一連のJavaScript関数です。 次のプラグインが含まれます。

* **`zeroPad`**:数の先頭に特定の数のゼロを追加します。 このプラグインは、変数が特定の桁数を必要とする場合に便利です。例えば、JavaScriptの日付オブジェクトを使用し、日付の月と日を1桁ではなく2桁の数値でフォーマットする場合などです。 例えば、の代わ `01/09/2020` りにを使用しま `1/9/2020`す。
* **`randomNumber`**:特定の桁数の乱数を生成します。 このプラグインは、サードパーティタグをデプロイし、キャッシュバスティングの乱数を使用する場合に役立ちます。
* **`twoDecimals`**:数値をクローゼットの100番目に丸めます。 このプラグインは、数値を有効な通貨値に丸めるのに便利です。

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
   * アクションタイプ：Numbers Suiteの初期化
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `zeroPad` ッドでは、次の引数を使用します。

* **num** （必須、整数）:埋め込む数値です。 この引数に小数が含まれる場合は、その値を切り捨てます。
* **nod** （必須、整数）:最後の戻り値の桁数。 padの桁数がpadの桁数より小さい場合は、引数の先頭に0を追加しま `num` す。

このメソ `randomNumber` ッドでは、次の引数を使用します。

* **nod** （オプション、整数）:生成する乱数の桁数。 最大値は17桁です。 デフォルト値は10桁です。

このメソ `twoDecimals` ッドでは、次の引数を使用します。

* **val** （必須、数値）:最も近い100分の1に丸める数値（文字列またはnumberオブジェクトで表されます）。

## 戻り値

* 0Pad **メソッドは**`num` 、引数と同じ文字列を返しますが、値の先頭には特定の数の0が追加され、戻り値の桁数が正しいことを確認します。
* randomNumber **メソッドは** 、任意の桁数の乱数と等しい文字列を返します。
* twoDecimalsメソッ **ドは** 、最も近い100分の1に丸められた数値オブジェクトを返します。

## 呼び出しの例

### zeroPadの例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumberの例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimalsの例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## バージョン履歴

### 1.0（2019年5月25日）

* 初回リリース。
