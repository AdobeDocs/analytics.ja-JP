---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkLeaveQueryString

デフォルトでは、クエリー文字列はすべてのレポートから除外されます。

一部の出口リンクやダウンロードリンクでは、次のサンプル URL に示すように、URL の重要な部分をクエリー文字列に含めることができます。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

ダウンロードファイル名をクエリー文字列内で定義することもあります。したがって、[!UICONTROL ファイルのダウンロード数]レポートをより正確にするためには、クエリー文字列が必要です。

*`linkLeaveQueryString`* 変数は、クエリー文字列が[!UICONTROL 出口リンク]と[!UICONTROL ファイルのダウンロード数]のレポートに含まれるかどうかを判別します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | 出口リンクファイルのダウンロード数 | false |

*注：`linkLeaveQueryString=true`を設定すると、すべての出口リンクとダウンロードリンク用のすべてのクエリ文字列パラメーターが含まれます。*

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

* `s.linkLeaveQueryString=true` を設定すると、すべての出口リンクとダウンロードリンク用のすべてのクエリー文字列パラメーターが含まれます。
* `linkLeaveQueryString` 変数は、記録されたページの URL、訪問者クリックマップ、または[!UICONTROL パス]レポートに影響を与えません。

## 出口リンクとファイルのダウンロード数の自動トラッキング

ファイルのダウンロードのファイルタイプおよび出口リンクを定義するパラメーターに基づき、ファイルのダウンロード数と出口リンクを自動的に追跡するよう JavaScript ファイルを設定できます。

自動トラッキングを制御するパラメーターは、以下のとおりです。

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

パラメーター   `trackDownloadLinks` および `trackExternalLinks` によって、ファイルのダウンロードと出口リンクの自動トラッキングが有効かどうかを指定します。有効にすると、`linkDownloadFileTypes` の値のいずれかに一致するファイルタイプを持つリンクは、自動的にファイルのダウンロードとして追跡されます。`linkInternalFilters` の値を含まない URL を使用するリンクは、出口リンクとして自動的に追跡されます。

JavaScript H.25.4（2013 年 2 月にリリース）での更新により、出口リンクの自動トラッキングで、`HREF` 属性が `#`、`about:`、または `javascript:` で始まるリンクが常に無視されるようになりました。

### 例 1

`.jpg` および `.aspx` ファイルタイプは上記の `linkDownloadFileTypes` に含まれていないので、ファイルのクリック数は自動的にファイルのダウンロード数として追跡およびレポートされません。

パラメーター `linkLeaveQueryString` によって、出口リンクの判定に使用するロジックが変更されます。`linkLeaveQueryString` が false の場合、出口リンクはリンク URL のドメイン、パス、ファイル部分のみを使用して判定されます。`linkLeaveQueryString` が true の場合、リンク URL のクエリー文字列部分も出口リンクの判定に使用されます。

### 例 2

次の設定の場合、以下の例は出口リンクとしてカウントされます。

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### 例 3

次の設定の場合、以下のリンクは出口リンクとしてカウントされません。

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*注意：単一リンクはファイルのダウンロードまたは出口リンクとしてのみ追跡できます（ファイルのダウンロードが優先されます）。リンクが出口リンクであるだけでなく、`linkDownloadFileTypes`および`linkInternalFilters`パラメーターに基づいたファイルのダウンロードでもある場合、出口リンクではなくファイルのダウンロードとして追跡およびレポートされます。*