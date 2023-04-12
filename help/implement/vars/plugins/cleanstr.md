---
title: cleanStr
description: 文字列から不要な文字をすべて削除または置換します。
feature: Variables
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 68%

---

# アドビプラグイン：cleanStr

{{plug-in}}

`cleanStr` プラグインは、HTML タグ文字、余分なホワイトスペース、タブ、改行／キャリッジリターンなど、不要な文字をすべて文字列から削除または置換します。また、左右の一重引用符を直線の一重引用符 (`'`) をクリックします。 Adobeは、変数の値から不要な文字を削除し、Adobe Experience Platformデータ収集の「テキストをクリーン」機能が実装のニーズを満たさない場合に、このプラグインを使用することをお勧めします。 このプラグインは、収集したデータに不要な文字が含まれていない場合や、Adobe Experience Platform Data Collection の「テキストをクリーン」機能で十分な場合は不要です。

## Web SDK または Web SDK 拡張機能を使用したプラグインのインストール

このプラグインは、Web SDK 内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用したプラグインのインストール

Adobeには、Adobe Analyticsで最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize cleanStr
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

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`cleanStr` 関数は次の引数を使用します。

* **`str`**（必須、文字列）：HTML エンコーディング、余分な空白、タブ、またはその他の不要な文字を消去する値です。

この関数は、不要な文字をすべて削除した `str` 引数の値を返します。

## 例

```js
// Returns the value "this is a messystring". Note that both tabs and extra spaces are present in the original string.
// Multiple spaces are reduced to one, while tabs are omitted entirely.
s.eVar1 = "  this  is a      messy  string    ";
s.eVar1 = cleanStr(s.eVar1)

// This function call does not do anything because the code does not assign the returned value to a variable.
s.eVar1 = "  this  is a      messy  string    ";
cleanStr(s.eVar1);
```

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 4 月 15 日（PT））

* 初回リリース。
