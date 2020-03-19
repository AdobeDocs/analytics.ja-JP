---
title: pt
description: 変数のリストで関数を実行します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：pt

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

プラグイン `pt` は、Analytics変数のリストで関数またはメソッドを実行します。 例えば、メソッドを毎回手動で呼び出すこ [`clearVars`](../functions/clearvars.md) となく、複数の変数に対して選択的にメソッドを実行できます。 その他のプラグインの一部は、このコードに依存して正しく実行されます。 一度に複数のAnalytics変数で特定の関数を実行する必要がない場合や、依存するプラグインを使用していない場合は、このプラグインは不要です。

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
   * アクションタイプ：初期化pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `pt` ッドでは、次の引数を使用します。

* **`l`** （必須、文字列）:引数に含まれる関数が実行できる変数 `cf` のリストです。
* **`de`** （オプション、文字列）:引数内の変数のリストを区切る区切り `l` 文字。 デフォルトはコンマ(`,`)です。
* **`cf`** （必須、文字列）:引数に含まれる各変数に対して呼び出される、AppMeasurementオブジェクトに含まれるコールバック関数の名 `l` 前。
* **`fa`** （オプション、文字列）:引数の関数が実行時に `cf` 追加の引数を呼び出す場合は、ここに含めます。 初期設定はで `undefined`す。

このメソッドを呼び出すと、（引数内の）コールバック関数が値を返 `cf` す場合に値が返されます。

## 呼び出しの例

### 例1

次のコードは、getQueryParamプラグインの一部です。  URLのクエリ文字列(fullQueryString)に含まれる各キーと値のペアに対して、getParameterValueヘルパー関数を実行します。  また、各キーと値のペアを抽出するには、fullQueryStringをアンパサンド(&amp;)で区切って、分割する必要があります。 parameterKeyは、プラグインがクエリ文字列から抽出しようとしているクエリ文字列パラメーターを参照します

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

上記の行は、次のようなコードを実行するためのショートカットです。

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## バージョン履歴

### 2.01（2019年9月24日）

* 全体的なサイズを小さくするためにコードを少し変更

### 2.0（2018年4月18日）

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。
* HコードとAppMeasurementの両方のサポートを追加しました。

### 1.0（2013年9月24日）

* 初回リリース。
