---
title: pt
description: 変数のリストで関数を実行します。
feature: Appmeasurement Implementation
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
role: Admin, Developer
TQID: https://experienceleague.adobe.com/HDWCcJZX1RDz8zzGrXU44ECjrav-x-RpPxG1w2K4Dl4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 619
ht-degree: 88%

---

# アドビプラグイン：pt

{{plug-in}}

`pt` プラグインは、Analytics 変数のリストで関数またはメソッドを実行します。 例えば、[`clearVars`](../functions/clearvars.md) 関数を毎回手動で呼び出すことなく、複数の変数に対して選択的に実行できます。 その他のプラグインの一部は、正しく実行するために、このコードに依存しています。 一度に複数の Analytics 変数に対して特定の関数を実行する必要がない場合や、依存するプラグインを使用しない場合は、このプラグインは必要ありません。

## Web SDKまたはWeb SDK拡張機能を使用したプラグインのインストール

このプラグインは、Web SDK内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用したプラグインのインストール

Adobeには、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize pt
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。 実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`pt` 関数は次の引数を使用します。

* **`l`**（必須、文字列）：`cf` 引数に含まれる関数が実行できる変数のリストです。
* **`de`**（オプション、文字列）：`l` 引数内の変数のリストを区切る区切り文字です。 デフォルトはコンマ（`,`）です。
* **`cf`**（必須、文字列）：`l` 引数に含まれる各変数に対して呼び出される AppMeasurement オブジェクトに含まれるコールバック関数の名前です。
* **`fa`**（オプション、文字列）：`cf` 引数内の関数が実行時に追加の引数を呼び出す場合は、ここに含めます。 デフォルト値は `undefined` です。

この関数を呼び出すと、（`cf` 引数内の）コールバック関数が値を返す場合に値が返されます。

## 呼び出しの例

### 例 1

次のコードは getQueryParam プラグインの一部です。  URL のクエリー文字列（fullQueryString）に含まれる各キーと値のペアに対して、getParameterValue ヘルパー関数を実行します。  また、各キーと値のペアを抽出するには、fullQueryString をアンパサンド「&amp;」で区切る必要があります。 parameterKey は、プラグインがクエリ文字列から抽出しようとしているクエリ文字列パラメーターを参照します。

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

上記の行は、次のようなコードを実行するためのショートカットです。

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## バージョン履歴

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.01（2019 年 9 月 24 日（PT））

* 全体的なサイズを小さくするためにコードを少し変更しました。

### 2.0（2018 年 4 月 17 日（PT））

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* H コードと AppMeasurement の両方のサポートを追加しました。

### 1.0（2013 年 9 月 23 日（PT））

* 初回リリース。
