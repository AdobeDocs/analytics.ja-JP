---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

 変数は 関数への参照です。この変数を使用すると、JavaScript ファイル内の適切な場所で 関数を呼び出すことができます。

The *`s_doPlugins`* function is called each time any of the following occurs:

* 関数 *`t()`* が呼び出されます
* 関数 *`tl()`* が呼び出されます
* 離脱リンクまたはダウンロードリンクがクリックされた
* 訪問者クリックマップによって追跡されているページ要素がクリックされた

Folio Builder *`doPlugins`* 関数は、データの収集や変更のためのカスタマイズされたルーチンを実行するために使用します。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. 例えば、オブジェクト名がs_mcの場合、関 *`s_doPlugins`* 数の名前はs_mc_doPluginsです。

## 構文と可能な値

関数 *`s_doPlugins`* は引用符で囲まないでください。関数名 *`doPlugins`* が変更された場合は、常に関数名に正確な名前を *`s_doPlugins`* 割り当てる必要があります。

```js
s.doPlugins=s_doPlugins;
```

## 例

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## 設定

なし

## 注意事項、質問、ヒント

* オブジェクト名を（s から s_mc などに）変更するのは、他の顧客とコンテンツを共有するか他の顧客のコンテンツを取り込む場合のみです。名前の変更 *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* 別のアドビの顧客から意図せずにコンテンツの取り込みを開始し、関数が上書きされる場合は、オブジェクト名を変更せずに、単に関数の *`s_doPlugins`**`s_doPlugins`* 名前を変更するだけで済みます。 同じページ上の他の JavaScript ファイルとは異なるオブジェクト名を使用することが最善策ですが、これは必須ではありません。