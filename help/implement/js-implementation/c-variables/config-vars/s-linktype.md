---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

自動的に決定されたリンクタイプがある場合はその値を含みます。次のいずれかに設定できます。

    * `d`（ダウンロード）
    * `e`（終了）
    * `o`（カスタム/その他）

これはイメージリクエストの `pe` パラメーターです。[`linkURL`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html) または [`linkName`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html) と共に設定される場合、サーバーコールはダウンロードリンク、カスタムリンクまたは出口リンクとして送信されます。

*メモ：[`pageName`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)変数はファイルのダウンロード、出口リンク、カスタムリンクに対して設定することはできません。これは、それぞれのリンクタイプがページビューではないので、関連するページ名を持たないからです。*


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
