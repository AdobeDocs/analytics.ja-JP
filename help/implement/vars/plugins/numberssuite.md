---
title: ナンバーズスイート
description: 他のJavaScript変数で使用する数値を生成および操作します。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobeプラグイン：ナンバーズスイート

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

Numbers suiteは一連のJavaScript関数です。 これには、次のプラグインが含まれます。

* **`zeroPad`**:数値の先頭に特定の数のゼロを追加します。 このプラグインは、JavaScriptの日付オブジェクトを使用し、日付の月と日を1桁ではなく2桁でフォーマットする場合など、変数に特定の桁数が必要な場合に役立ちます。 例えば、の代`01/09/2020`わりに`1/9/2020`。
* **`randomNumber`**:特定の桁数で乱数を生成します。 このプラグインは、サードパーティタグを導入し、キャッシュバスティングの乱数が必要な場合に役立ちます。
* **`twoDecimals`**:数字をクローゼットの100分の1に丸めます。 このプラグインは通貨の目的で役立ち、数値を有効な通貨値に丸めることができます。

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

* **num** （必須、整数）:埋め込む数値です。 このメソッドは、この引数に小数が含まれる場合、その値を切り捨てます。
* **nod** （必須、整数）:最終戻り値の桁数。 padの桁数がpadの桁数より小さい場合、プラグインは引数の先頭に0を追加し `num` ます。

このメソ `randomNumber` ッドでは、次の引数を使用します。

* **nod** （オプション、整数）:生成する乱数の桁数。 最大値は17桁です。 デフォルト値は10桁です。

このメソ `twoDecimals` ッドでは、次の引数を使用します。

* **val** （必須、数値）:最も近い100分の1に丸める数値（文字列オブジェクトまたはnumberオブジェクトで表されます）。

## 戻り値

* 0Pad **メソッドは、引数と同じ**`num` 、値の先頭に特定の数のゼロを追加した文字列を返します。これにより、戻り値の桁数が正しくなります。
* randomNumber **メソッドは** 、任意の桁数の乱数と等しい文字列を返します。
* twoDecimalsメソッ **ドは** 、最も近い100分の1に四捨五入した数値オブジェクトを返します。

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
