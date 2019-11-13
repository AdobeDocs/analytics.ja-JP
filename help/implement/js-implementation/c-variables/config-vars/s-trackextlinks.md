---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.trackExternalLinks

「true」の場合、 および を使用して、クリックされたリンクが離脱リンクかどうかを判別します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackExternalLinks`*&#x200B;サイトに離脱リンクがない場合、または離脱リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。if *`trackExternalLinks`* が「true」の場合、離脱リンクをクリックすると、トラッキングデータが直ちに送信されます。離脱リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackExternalLinks`* が「false」の場合は、サイト上の離脱リンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

## 構文と可能な値

*`trackExternalLinks`変数には、「true」または「false」を設定する必要があります。*

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

* *`trackExternalLinks`* が「true」の場合、訪問者が離脱リンクをクリックするたびに、（リンクターゲットが読み込まれる前に）データが送信されます。

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