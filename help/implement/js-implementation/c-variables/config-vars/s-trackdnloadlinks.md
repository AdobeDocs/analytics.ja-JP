---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackDownLoadLinks

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

*`trackDownloadLinks`* が「true」の場合は、どのリンクがダウンロード可能ファイルかを判断するために *`linkDownloadFileTypes`* を使用します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

*`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。*`trackDownloadLinks`* が「true」の場合は、ファイルのダウンロードリンクがクリックされると、データが直ちに [!DNL Analytics] に送信されます。ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。*`trackDownloadLinks`* が「false」の場合は、サイト上のダウンロード可能ファイルへのリンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

## 構文と可能な値

*`trackDownloadLinks`* 変数には、「true」または「false」を設定する必要があります。

## 例

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## 設定

なし

## 注意事項、質問、ヒント

* *`trackDownloadLinks`* が「false」の場合は、ユーザーがサイト上でファイルのダウンロードに使用するリンクの数が、訪問者クリックマップでのレポートで少なくカウントされることがあります。

* *`trackDownloadLinks`* が「true」の場合は、訪問者がファイルのダウンロードリンクをクリックするたびにデータが送信されます。

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

パラメーター  `trackDownloadLinks` および `trackExternalLinks` によって、ファイルのダウンロードと出口リンクの自動トラッキングが有効かどうかを指定します。有効にすると、`linkDownloadFileTypes` の値のいずれかに一致するファイルタイプを持つリンクは、自動的にファイルのダウンロードとして追跡されます。`linkInternalFilters` の値を含まない URL を使用するリンクは、出口リンクとして自動的に追跡されます。

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