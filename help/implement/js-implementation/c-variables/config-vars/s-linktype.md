---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkType

自動的に決定されたリンクタイプがある場合はその値を含みます。次のいずれかに設定できます。

    * `d` （ダウンロード）
    * `e` （終了）
    * `o` （カスタム/その他）

これはイメージリクエストの `pe` パラメーターです。`linkURL` または `linkName` と共に設定される場合、サーバーコールはダウンロードリンク、カスタムリンクまたは離脱リンクとして送信されます。

*注意：各リンクタ[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)イプがページビューではなく、関連するページ名を持たないので、ファイルのダウンロード数、離脱リンクまたはカスタムリンクに対して変数を設定することはできません。*


**例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```
