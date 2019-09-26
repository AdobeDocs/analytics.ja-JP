---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkLeaveQueryString

デフォルトでは、クエリ文字列はすべての レポートから除外されます。

一部の離脱リンクやダウンロードリンクでは、次のサンプル URL に示すように、URL の重要な部分をクエリ文字列に含めることができます。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

ダウンロードファイル名をクエリ文字列内で定義することもあります。したがって、[!UICONTROL ファイルのダウンロード数]レポートをより正確にするためには、クエリ文字列が必要です。

The *`linkLeaveQueryString`* variable determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | 離脱リンクファイルのダウンロード数 | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

## 構文

```js
s.linkLeaveQueryString=[false/true]
```

## 例

```js
s.linkLeaveQueryString=false
```

## 可能な値

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## 設定

この変数では設定は必要ありません。

## 注意事項、質問、ヒント

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.
