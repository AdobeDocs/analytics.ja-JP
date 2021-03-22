---
title: pt
description: 変数のリストで関数を実行します。
translation-type: tm+mt
source-git-commit: fc7e6953e69cdff7b326705a906687be634d9b5f
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 98%

---


# アドビプラグイン：pt

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`pt` プラグインは、Analytics 変数のリストで関数またはメソッドを実行します。例えば、[`clearVars`](../functions/clearvars.md) メソッドを毎回手動で呼び出すことなく、複数の変数に対して選択的に実行できます。その他のプラグインの一部は、正しく実行するために、このコードに依存しています。一度に複数の Analytics 変数に対して特定の関数を実行する必要がない場合や、依存するプラグインを使用しない場合は、このプラグインは必要ありません。

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
   * Action Type：Initialize pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`pt` メソッドでは、次の引数を使用します。

* **`l`**（必須、文字列）：`cf` 引数に含まれる関数が実行できる変数のリストです。
* **`de`**（オプション、文字列）：`l` 引数内の変数のリストを区切る区切り文字です。デフォルトはコンマ（`,`）です。
* **`cf`**（必須、文字列）：`l` 引数に含まれる各変数に対して呼び出される AppMeasurement オブジェクトに含まれるコールバック関数の名前です。
* **`fa`**（オプション、文字列）：`cf` 引数内の関数が実行時に追加の引数を呼び出す場合は、ここに含めます。デフォルト値は `undefined` です。

このメソッドを呼び出すと、（`cf` 引数内の）コールバック関数が値を返す場合に値が返されます。

## 呼び出しの例

### 例 1

次のコードは getQueryParam プラグインの一部です。URL のクエリー文字列（fullQueryString）に含まれる各キーと値のペアに対して、getParameterValue ヘルパー関数を実行します。また、各キーと値のペアを抽出するには、fullQueryString をアンパサンド「&amp;」で区切る必要があります。parameterKey は、プラグインがクエリー文字列から抽出しようとしているクエリー文字列パラメーターを参照します。

```javascript
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
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

### 3.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 2.01（2019 年 9 月 25 日）

* 全体的なサイズを小さくするためにコードを少し変更しました。

### 2.0（2018 年 4 月 18 日）

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* H コードと AppMeasurement の両方のサポートを追加しました。

### 1.0（2013 年 9 月 24 日）

* 初回リリース。
