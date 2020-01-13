---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackExternalLinks

「true」の場合、クリックされたリンクが出口リンクかどうかを判別します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

*`trackExternalLinks`*&#x200B;サイトに出口リンクがない場合、または出口リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。*`trackExternalLinks`* が「true」の場合、出口リンクをクリックすると、トラッキングデータが直ちに送信されます。出口リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。*`trackExternalLinks`* が「false」の場合は、サイト上の出口リンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

## 構文と可能な値

*`trackExternalLinks`* 変数には、「true」または「false」を設定する必要があります。

```
js
s.trackExternalLinks=true|false
```

## 例

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## 設定

なし

## 注意事項、質問、ヒント

* *`trackExternalLinks`* が「false」の場合、訪問者がサイトから出て行くリンクは、訪問者クリップマップでのレポートで少なくカウントされることがあります。

* *`trackExternalLinks`* が「true」の場合、訪問者が出口リンクをクリックするたびに、（リンクターゲットが読み込まれる前に）データが送信されます。

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

パラメーター`trackDownloadLinks` および `trackExternalLinks` によって、ファイルのダウンロードと出口リンクの自動トラッキングが有効かどうかを指定します。有効にすると、`linkDownloadFileTypes` の値のいずれかに一致するファイルタイプを持つリンクは、自動的にファイルのダウンロードとして追跡されます。`linkInternalFilters` の値を含まない URL を使用するリンクは、出口リンクとして自動的に追跡されます。

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