---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkLeaveQueryString

デフォルトでは、クエリ文字列はすべての レポートから除外されます。

一部の離脱リンクやダウンロードリンクでは、次のサンプル URL に示すように、URL の重要な部分をクエリ文字列に含めることができます。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

ダウンロードファイル名をクエリ文字列内で定義することもあります。したがって、[!UICONTROL ファイルのダウンロード数]レポートをより正確にするためには、クエリ文字列が必要です。

*`linkLeaveQueryString`* 変数は、クエリ文字列が[!UICONTROL 離脱リンク]と[!UICONTROL ファイルのダウンロード数]のレポートに含まれるかどうかを判別します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | 離脱リンクファイルのダウンロード数 | false |

> [!NOTE]`linkLeaveQueryString=true` を設定すると、すべての離脱リンクとダウンロードリンク用のすべてのクエリ文字列パラメーターが含まれます。

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

* `s.linkLeaveQueryString=true` を設定すると、すべての離脱リンクとダウンロードリンク用のすべてのクエリ文字列パラメーターが含まれます。
* `linkLeaveQueryString` 変数は、記録されたページの URL、訪問者クリックマップ、または[!UICONTROL パス]レポートに影響を与えません。
