---
title: getPreviousValue
description: 変数に渡された最後の値を取得します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getPreviousValue

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getPreviousValue` ラグインを使用すると、変数を以前のヒットに設定された値に設定できます。 このプラグインは、実装に現在のヒットに必要な値がすべて含まれている場合は不要です。

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
   * アクションタイプ：getPreviousValueの初期化
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getPreviousValue` ッドでは、次の引数を使用します。

* **`v`** （文字列、必須）:次のイメージリクエストに渡す値を持つ変数。 一般的な変数は、前のペ `s.pageName` ージ値を取得するために使用されます。
* **`c`** （文字列、オプション）:値を格納するcookieの名前。  この引数が設定されていない場合、デフォルトはになりま `"s_gpv"`す。

このメソッドを呼び出すと、cookieに含まれる文字列値が返されます。 次に、プラグインはcookieの有効期限をリセットし、引数から変数値を割り当て `v` ます。 cookieは、無操作状態が30分間続くと有効期限が切れます。

## 呼び出しの例

### 例1

次のコード…

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* 最初に、s.prop7を、前のイメージリクエストのs.pageNameに渡された値（「gpv_Page」cookieに保存された値）と同じ値に設定します。
* 次に、コードは「gpv_Page」 Cookieをリセットし、s.pageNameの現在の値と等しくなります
* このコードの実行時にs.pageNameが設定されていない場合、コードはcookieの現在の値の有効期限をリセットします

### 例2

次のコードは、s.prop7をs.pageNameに渡された最後の値と同じ値に設定しますが、呼び出しが行われた時点で、inListプラグインを介して決定されたevent1がs.eventsに含まれている場合にのみ有効です。

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例3

次のコードは、s.prop7をs.pageNameに渡された最後の値と同じ値に設定しますが、s.pageNameが現在同時にページ上で設定されている場合にのみ設定します。

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### 例4

次のコードは、s.eVar10を、前のイメージリクエストのs.eVar1に渡された値と同じ値に設定します。   以前のeVar1値は「s_gpv」Cookieに含まれていました。  次に、「s_gpv」 cookieをs.eVar1の現在の値と同じ値に設定します。

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## ありそうもないクイルク

v引数に関連付けられた変数が新しい値に設定され、getPreviousValueプラグインが実行され、Analyticsサーバーの呼び出しが同時に送信されない場合、新しいv引数の値は、次回プラグインが実行されたときに「以前の値」と見なされます。
例えば、次のコードが訪問の最初のページで実行されるとします。

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

このコードでは、pageName引数が&quot;home&quot;で、p7 (prop7)引数が設定されていないサーバーコールが生成されます。  ただし、s.getPreviousValueを呼び出すと、s.pageNameの値(&quot;home&quot;)を呼び出しで指定されたcookie(「gpv_Page」cookie)に含める必要があります。
次に、同じページ上で次のコードが（何らかの理由で）実行されたとします。

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

s.t()関数はこのコードブロックで実行されないので、別のイメージリクエストは作成されません。  ただし、s.getPreviousValue()関数コードを今回実行すると、s.prop7はs.pageNameの以前の値(&quot;home&quot;)に置き換え、s.pageNameの新しい値(&quot;happy value&quot;)を「gpv_Page」 Cookieに含める必要があります。
訪問者が別のページに移動し、次のコードがこのページで実行されたとします。

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

s.t()呼び出し関数を実行すると、s.pageName=&quot;page 2&quot;とs.prop7が&quot;happy value&quot;に等しいイメージリクエストが作成されます。この値は、getPreviousValueの最後の呼び出しが行われたときのs.pageNameの値です。   s.pageNameに最初に渡された値が「home」であっても、s.prop7の「home」の値が実際のイメージリクエストに含まれることはありませんでした。

## バージョン履歴

### v2.0（2019年10月8日）

* ポイントリリース（完全な論理書き換え）。
