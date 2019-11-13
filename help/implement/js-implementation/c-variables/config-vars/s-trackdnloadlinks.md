---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.trackDownLoadLinks

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

*`trackDownloadLinks`* が「true」の場合は、どのリンクがダウンロード可能ファイルかを判断するために *`linkDownloadFileTypes`* を使用します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。*`trackDownloadLinks`* が「true」の場合は、ファイルのダウンロードリンクがクリックされると、データが直ちに [!DNL Analytics] に送信されます。ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackDownloadLinks`* が「false」の場合は、サイト上のダウンロード可能ファイルへのリンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

## 構文と可能な値

*`trackDownloadLinks`変数には、「true」または「false」を設定する必要があります。*

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

## 離脱リンクとファイルのダウンロード数の自動トラッキング

ファイルのダウンロードのファイルタイプおよび離脱リンクを定義するパラメーターに基づき、ファイルのダウンロード数と離脱リンクを自動的に追跡するよう JavaScript ファイルを設定できます。

自動トラッキングを制御するパラメーターは、以下のとおりです。

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

パラメーター  `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. 有効にすると、の値のいずれかに一致するファイルタイプを持つリンクは、自動的にフ `linkDownloadFileTypes` ァイルのダウンロードとして追跡されます。 の値を含まないURLを含むリンクは、離脱リンクとし `linkInternalFilters` て自動的に追跡されます。

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### 例 1

ファイルタイプとは上 `.jpg` 記に含ま `.aspx` れていないので、フ `linkDownloadFileTypes` ァイルのクリック数は自動的にファイルのダウンロード数として追跡およびレポートされません。

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. `linkLeaveQueryString`=falseの場合、離脱リンクは、リンクURLのドメイン、パス、ファイル部分のみを使用して決定されます。 When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### 例 2

次の設定の場合、以下の例は離脱リンクとしてカウントされます。

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### 例 3

次の設定の場合、以下のリンクは離脱リンクとしてカウントされません。

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*注意：単一リンクはファイルのダウンロードまたは離脱リンクとしてのみ追跡できます（ファイルのダウンロードが優先されます）。リンクがパラメーターに基づいて離脱リンクとファイルのダウンロードの両方で、およびに基づいて`linkDownloadFileTypes``linkInternalFilters`いる場合、離脱リンクではなくファイルのダウンロードとして追跡およびレポートされます。*