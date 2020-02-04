---
title: pt
description: 変数のリストで関数を実行します。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobeプラグイン：pt

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

プラグ `pt` インは、Analytics変数のリストで関数またはメソッドを実行します。 例えば、メソッドを毎回手動で呼び出すこ `clearVars` となく、複数の変数に対して選択的にメソッドを実行できます。 その他のプラグインの一部は、正しく実行するために、このコードに依存しています。 一度に複数のAnalytics変数に対して特定の関数を実行する必要がない場合や、依存するプラグインを使用しない場合は、このプラグインは必要ありません。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
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
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `pt` ッドでは、次の引数を使用します。

* **`l`**（必須、文字列）:引数に含まれる関数が実行できる変数`cf`のリストです。
* **`de`**（オプション、文字列）:引数内の変数のリストを区切る区切り`l`文字。 デフォルトはコンマ(`,`)です。
* **`cf`**（必須、文字列）:引数に含まれる各変数に対して呼び出されるAppMeasurementオブジェクトに含まれるコールバック関数の名`l`前。
* **`fa`**（オプション、文字列）:引数内の関数が実行時に`cf`追加の引数を呼び出す場合は、ここに含めます。 初期設定はで`undefined`す。

このメソッドを呼び出すと、（引数内の）コールバック関数が値を返 `cf` す場合に値が返されます。

## 呼び出しの例

### 例1

次のコードはgetQueryParamプラグインの一部です。  URLのクエリ文字列(fullQueryString)に含まれる各キーと値のペアに対して、getParameterValueヘルパー関数を実行します。  また、各キーと値のペアを抽出するには、fullQueryStringをアンパサンド「&amp;」で区切る必要があります。 parameterKeyは、プラグインがクエリ文字列から抽出しようとしているクエリ文字列パラメーターを参照します

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

* ポイントリリース（再コンパイル、コードサイズが小さい）。
* HコードとAppMeasurementの両方のサポートが追加されました。

### 1.0（2013年9月24日）

* 初回リリース。
