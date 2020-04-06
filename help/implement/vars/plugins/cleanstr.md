---
title: cleanStr
description: 文字列から不要な文字をすべて削除または置換します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：cleanStr

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`cleanStr` プラグインは、HTML タグ文字、余分なホワイトスペース、タブ、改行／キャリッジリターンなど、不要な文字をすべて文字列から削除または置換します。It also replaces left/right single quotes (`‘` and `’`) with straight single quotes (`'`). Launch の「テキストをクリーン」機能が変数の値から不要な文字を削除する実装のニーズを満たさない場合は、このプラグインを使用することをお勧めします。このプラグインは、収集したデータに不要な文字が含まれていない場合や、Launch の「テキストをクリーン」機能で十分な場合は必要ありません。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize cleanStr
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`cleanStr` メソッドでは、次の引数を使用します。

* **`str`**（必須、文字列）：HTML エンコーディング、余分な空白、タブ、またはその他の不要な文字を消去する値です。

このメソッドは、不要な文字をすべて削除した `str` 引数の値を返します。

## 例

### 例 1

次を想定します（点はスペースを表し、矢印はタブ文字を表します）。

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

次のコードを実行すると

```js
s.eVar1 = cleanStr(s.eVar1)
```

eVar1 は「this is a messystring」に等しく設定されます（余分なスペースとタブ文字はすべて削除されます）。

### 例 2

以下で、

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

次のコードが実行された場合、

```js
cleanStr(s.eVar1)
```

s.eVar1 の最終値は、次のとおりです。

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

プラグインを単独で（変数に戻り値を割り当てずに）実行しても、str 引数を介して渡された変数は実際には「リセット」されません。

## バージョン履歴

### 1.0（2018 年 4 月 16 日）

* 初回リリース。
