---
title: getPreviousValue
description: 変数に渡された最後の値を取得します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getPreviousValue

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getPreviousValue` ラグインを使用すると、変数を以前のヒットに設定された値に設定できます。 このプラグインは、現在のヒットに必要な値がすべて含まれている場合は不要です。

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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getPreviousValue` ッドでは、次の引数を使用します。

* **`v`**（文字列、必須）:次のイメージリクエストに渡す値を持つ変数。 一般的な変数は、前のペ`s.pageName`ージ値を取得するために使用されます。
* **`c`**（文字列、オプション）:値を格納するcookieの名前。  この引数を設定しない場合、デフォルトはになりま`"s_gpv"`す。

このメソッドを呼び出すと、cookieに含まれる文字列値が返されます。 その後、プラグインはcookieの有効期限をリセットし、引数から変数値を割り当て `v` ます。 cookieは、無操作状態が30分間続くと有効期限が切れます。

## 呼び出しの例

### 例1

次のコード…

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 最初に、s.prop7を前のイメージリクエストのs.pageNameに渡された値（つまり、「gpv_Page」cookieに保存された値）と同じ値に設定します。
* 次に、コードは「gpv_Page」 cookieをリセットし、s.pageNameの現在の値と等しくなります
* このコードの実行時にs.pageNameが設定されていない場合、コードはcookieの現在の値の有効期限をリセットします

### 例2

次のコードは、s.prop7をs.pageNameに渡された最後の値と等しく設定しますが、呼び出しが行われた時点で、inListプラグインを介して決定された、event1がs.events内に含まれている場合にのみ有効です。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例3

次のコードは、s.prop7をs.pageNameに渡された最後の値に設定しますが、s.pageNameが現在ページに設定されている場合にのみ設定します。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例4

次のコードは、s.eVar10を、前のイメージリクエストのs.eVar1に渡された値と同じ値に設定します。   以前のeVar1の値は、「s_gpv」 cookieに含まれていました。  次に、「s_gpv」 cookieをs.eVar1の現在の値と等しく設定します。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## 万が一

v引数に関連付けられた変数が新しい値に設定され、getPreviousValueプラグインが実行され、Analyticsサーバー呼び出しが同時に送信されない場合、新しいv引数の値は、次回プラグインが実行されたときに「以前の値」と見なされます。
例えば、次のコードが訪問の最初のページで実行されるとします。

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

このコードでは、pageName引数が&quot;home&quot;で、p7 (prop7)引数が設定されていないサーバーコールが生成されます。  ただし、s.getPreviousValueを呼び出すと、s.pageNameの値(&quot;home&quot;)を呼び出しで指定したcookie（つまり、&quot;gpv_Page&quot; cookie）内に置き換えます。
次に、同じページ上で次のコードが実行されたと仮定します（何らかの理由で）。

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

s.t()関数はこのコードブロックで実行されないので、別のイメージリクエストは作成されません。  ただし、s.getPreviousValue()関数コードを今回実行すると、s.prop7はs.pageNameの以前の値(つまり、「home」)をクリックし、s.pageNameの新しい値(つまり、「happy value」)を「gpv_Page」 cookieに置き換えます。
訪問者が別のページに移動し、このページで次のコードが実行されるとします。

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

s.t()呼び出し関数を実行すると、s.pageName=&quot;page 2&quot;とs.prop7が&quot;happy value&quot;に等しいイメージリクエストが作成されます。この値は、getPreviousValueの最後の呼び出しが行われたときのs.pageNameの値です。   s.pageNameに最初に渡された値が「home」であったにもかかわらず、「home」のs.prop7値が実際のイメージリクエストに含まれることはありませんでした。

## バージョン履歴

### v2.0（2019年10月8日）

* ポイントリリース（完全な論理書き換え）。
