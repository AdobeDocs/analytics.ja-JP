---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---



# s.doPlugins

 変数は 関数への参照です。この変数を使用すると、JavaScript ファイル内の適切な場所で 関数を呼び出すことができます。

次のいずれかが発生するたびに *`s_doPlugins`* 関数が呼び出されます。

* *`t()`* 関数が呼び出されます。
* *`tl()`* 関数が呼び出されます。
* 離脱リンクまたはダウンロードリンクがクリックされた
* 訪問者クリックマップによって追跡されているページ要素がクリックされた

*`doPlugins`* 関数は、データの収集や変更のためのカスタマイズされたルーチンを実行するために使用します。「s」以外のオブジェクト名を使用する場合は、*`s_doPlugins`* の名前が適切に変更されていることを確認してください。例えば、オブジェクト名がs_mcの場合、*`s_doPlugins`* 関数の名前は「s_mc_doPlugins」です。

## 構文と可能な値

*`s_doPlugins`* 関数は引用符で囲まないでください。（関数名が変更された場合）*`doPlugins`**には常に`s_doPlugins`* 関数の正確な名前に割り当てる必要があります。

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

* オブジェクト名を（s から s_mc などに）変更するのは、他の顧客とコンテンツを共有するか他の顧客のコンテンツを取り込む場合のみです。*`s_doPlugins`* 関数の名前を [!UICONTROL s_mc_doPlugins] に変更することで、別のクライアントの JavaScript によって *`doPlugins`* 関数が上書きされるのを防ぎます。

* 別のアドビの顧客から意図せずにコンテンツの取り込みを開始し、*`s_doPlugins`* 関数が上書きされる場合は、オブジェクト名を変更せずに、*`s_doPlugins`* 関数の名前を変更するだけで済みます。同じページ上の他の JavaScript ファイルとは異なるオブジェクト名を使用することが最善策ですが、これは必須ではありません。
