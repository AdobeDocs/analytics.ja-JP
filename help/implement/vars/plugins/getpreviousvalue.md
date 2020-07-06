---
title: getPreviousValue
description: 変数に渡された最後の値を取得します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 100%

---


# アドビプラグイン：getPreviousValue

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getPreviousValue` プラグインを使用すると、変数を以前のヒットに設定された値に設定できます。このプラグインは、現在のヒットに必要な値がすべて含まれている場合は不要です。

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
   * Action Type：Initialize getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPreviousValue` メソッドでは、次の引数を使用します。

* **`v`**（文字列、必須）：次のイメージリクエストに渡す値を持つ変数。一般的な変数は、前のページ値を取得するために使用される `s.pageName` です。
* **`c`**（文字列、オプション）：値を格納する Cookie の名前。この引数を設定しない場合、デフォルトは `"s_gpv"` になります。

このメソッドを呼び出すと、Cookie に含まれる文字列値が返されます。その後、プラグインは Cookie の有効期限をリセットし、`v` 引数から変数値を割り当てます。Cookie は、無操作状態が 30 分間続くと有効期限が切れます。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 最初に、s.prop7 を前のイメージリクエストの s.pageName に渡された値（つまり、「gpv_Page」Cookie に保存された値）と同じ値に設定します。
* 次に、コードは「gpv_Page」Cookie をリセットし、値は s.pageName の現在の値と等しくなります。
* このコードの実行時に s.pageName が設定されていない場合、コードは Cookie の現在の値の有効期限をリセットします。

### 例 2

次のコードは、s.prop7 を s.pageName に渡された最後の値と等しく設定しますが、呼び出しがおこなわれた時点で、inList プラグインを介して決定されたように、event1 が s.events 内に含まれている場合にのみ有効です。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例 3

次のコードは、s.pageName が現在ページに設定されている場合にのみ、s.prop7 を s.pageName に渡された最後の値に設定します。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例 4

次のコードは、s.eVar10 を、前のイメージリクエストの s.eVar1 に渡された値と同じ値に設定します。以前の eVar1 の値は、「s_gpv」Cookie に含まれていました。次に、「s_gpv」Cookie を s.eVar1 の現在の値と等しく設定します。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 万が一の場合

v 引数に関連付けられた変数が新しい値に設定され、getPreviousValue プラグインが実行され、Analytics サーバー呼び出しが同時に送信されない場合、新しい v 引数の値は、次回プラグインが実行されたときに「以前の値」と見なされます。
例えば、次のコードが訪問の最初のページで実行されるとします。

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

このコードでは、pageName 引数が「home」で、p7（prop7）引数が設定されていないサーバーコールが生成されます。ただし、s.getPreviousValue を呼び出すと、呼び出しで指定した Cookie（「gpv_Page」Cookie）内に s.pageName の値（「home」）を格納します。
次に、同じページ上で次のコードが直後に実行されたと仮定します（何らかの理由で）。

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

s.t() 関数はこのコードブロックで実行されないので、別のイメージリクエストは作成されません。ただし、s.getPreviousValue() 関数コードを今回実行すると、s.prop7 は s.pageName の以前の値（「home」）に設定され、s.pageName の新しい値（「happy value」）を「gpv_Page」Cookie に格納します。
訪問者が別のページに移動し、このページで次のコードが実行されるとします。

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

s.t() の呼び出し関数を実行すると、s.pageName が「page 2」で s.prop7 が「happy value」に等しいイメージリクエストが作成されます。この値は、getPreviousValue の最後の呼び出しがおこなわれたときの s.pageName の値です。s.pageName に最初に渡された値が「home」であったにもかかわらず、「home」の s.prop7 値が実際のイメージリクエストに含まれることはありませんでした。

## バージョン履歴

### v2.0（2019 年 10 月 8 日）

* ポイントリリース（完全な論理書き換え）。
