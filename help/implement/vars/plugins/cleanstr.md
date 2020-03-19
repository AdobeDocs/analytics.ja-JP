---
title: cleanStr
description: 文字列から不要な文字をすべて削除または置換します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：cleanStr

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

プラグイ `cleanStr` ンは、HTMLタグ文字、余分な空白、タブ、改行/キャリッジリターンなど、不要な文字をすべて文字列から削除または置換します。 また、左右の一重引用符（および）を`‘` 直線の一 `’`重引用符(`'`)に置き換えます。 変数の値から不要な文字を削除し、起動の「テキストをクリーン」機能が実装のニーズを満たさない場合は、このプラグインを使用することをお勧めします。 このプラグインは、収集したデータに不要な文字が含まれていない場合や、「起動」の「テキストをクリーン」機能で十分な場合は必要ありません。

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
   * アクションタイプ：cleanStrの初期化
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `cleanStr` ッドでは、次の引数を使用します。

* **`str`** （必須、文字列）:HTMLエンコーディング、余分な空白、タブ、またはその他の不要な文字を消去する値。

このメソッドは、不要な文字をすべ `str` て削除した引数の値を返します。

## 例

### 例1

次の点（ドットはスペースを表し、矢印はタブ文字を表す）を想定します。

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

次のコードを実行する場合

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1は「this is a messystring」に等しく設定されます（余分なスペースとタブ文字はすべて削除されます）。

### 例2

...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...次のコードが実行されます。

```js
cleanStr(s.eVar1)
```

...s.eVar1の最終的な値は、次のとおりです。

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

プラグインを（変数に戻り値を割り当てずに）単独で実行しても、実際にはstr引数を通じて渡された変数は「リセット」されません。

## バージョン履歴

### 1.0（2018年4月16日）

* 初回リリース。
