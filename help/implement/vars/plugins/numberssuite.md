---
title: Numbers Suite
description: 他の JavaScript 変数で使用する数値を生成および操作します。
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# アドビプラグイン：Numbers Suite

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

Numbers Suite は一連の JavaScript 関数です。これには、次のプラグインが含まれます。

* **`zeroPad`**：数値の先頭に特定の数のゼロを追加します。このプラグインは、JavaScript の日付オブジェクトを使用し、日付の月と日を 1 桁ではなく 2 桁でフォーマットする場合など、変数に特定の桁数が必要な場合に役立ちます。例えば、`01/09/2020` の代わりに `1/9/2020` となります。
* **`randomNumber`**：特定の桁数で乱数を生成します。このプラグインは、サードパーティタグを導入し、キャッシュバスティングの乱数が必要な場合に役立ちます。
* **`twoDecimals`**：数字を小数点以下 2 桁に丸めます。このプラグインは通貨の目的で役立ち、数値を有効な通貨値に丸めることができます。

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
   * Action Type：Initialize Numbers Suite
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`zeroPad` メソッドでは、次の引数を使用します。

* **num**（必須、整数）：埋め込む数値です。このメソッドは、この引数に小数が含まれる場合、その値を切り捨てます。
* **nod**（必須、整数）：最終戻り値の桁数です。pad の桁数がパッド対象の桁数より小さい場合、プラグインは `num` 引数の先頭に 0 を追加します。

`randomNumber` メソッドでは、次の引数を使用します。

* **nod**（オプション、整数）：生成する乱数の桁数です。最大値は 17 桁です。デフォルト値は 10 桁です。

`twoDecimals` メソッドでは、次の引数を使用します。

* **val**（必須、数値）：最も近い小数点以下 2 桁に丸める数値（文字列オブジェクトまたは数値オブジェクトで表されます）です。

## 戻り値

* **zeroPad** メソッドは、`num` 引数と同じ、値の先頭に特定の数のゼロを追加した文字列を返します。これにより、戻り値の桁数が正しくなります。
* **randomNumber** メソッドは、任意の桁数の乱数と等しい文字列を返します。
* **twoDecimals** メソッドは、最も近い小数点以下 2 桁に丸めた数値オブジェクトを返します。

## 呼び出しの例

### zeroPad の例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber の例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals の例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## バージョン履歴

### 1.0（2019 年 5 月 26 日）

* 初回リリース。
