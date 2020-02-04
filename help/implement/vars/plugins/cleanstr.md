---
title: cleanStr
description: 文字列から不要な文字をすべて削除または置換します。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobeプラグイン：cleanStr

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `cleanStr` ラグインは、HTMLタグ文字、余分なホワイトスペース、タブ、改行/キャリッジリターンなど、不要な文字をすべて文字列から削除または置換します。 また、左右の一重引用符(および`‘` )を `’`直線の一重引用符(`'`)に置き換えます。 変数の値から不要な文字を削除し、起動の「テキストをクリーン」機能が実装のニーズを満たさない場合は、このプラグインを使用することをお勧めします。 このプラグインは、収集したデータに不要な文字が含まれていない場合や、「起動」の「テキストをクリーン」機能で十分な場合は必要ありません。

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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `cleanStr` ッドでは、次の引数を使用します。

* **`str`**（必須、文字列）:HTMLエンコーディング、余分な空白、タブ、またはその他の不要な文字を消去する値です。

このメソッドは、不要な文字をすべて削除 `str` した引数の値を返します。

## 例

### 例1

次の点を想定します（点はスペースを表し、矢印はタブ文字を表します）。

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

次のコードを実行すると

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1は「this is a messystring」に等しく設定されます（余分なスペースとタブ文字はすべて削除されます）

### 例2

...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...次のコードが実行されます。

```js
cleanStr(s.eVar1)
```

...s.eVar1の最終値は、次のとおりです。

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

プラグインを単独で（変数に戻り値を割り当てずに）実行しても、実際にはstr引数を介して渡された変数は「リセット」されません。

## バージョン履歴

### 1.0（2018年4月16日）

* 初回リリース。
