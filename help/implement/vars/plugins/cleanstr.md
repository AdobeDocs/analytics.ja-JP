---
title: cleanStr
description: 文字列から不要な文字をすべて削除または置換します。
translation-type: ht
source-git-commit: c1a19f79eba3e992747a14146ca93306f84b355b
workflow-type: ht
source-wordcount: '529'
ht-degree: 100%

---


# アドビプラグイン：cleanStr

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`cleanStr` プラグインは、HTML タグ文字、余分なホワイトスペース、タブ、改行／キャリッジリターンなど、不要な文字をすべて文字列から削除または置換します。また、左右の一重引用符（`‘` および `’`）を直線の一重引用符（`'`）に置き換えます。Launch の「テキストをクリーン」機能が変数の値から不要な文字を削除する実装のニーズを満たさない場合は、このプラグインを使用することをお勧めします。このプラグインは、収集したデータに不要な文字が含まれていない場合や、Launch の「テキストをクリーン」機能で十分な場合は必要ありません。

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
   * Action Type：Initialize cleanStr
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
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
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

以下の条件が当てはまる場合：

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

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 4 月 15 日（PT））

* 初回リリース。
