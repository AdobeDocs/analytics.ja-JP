---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

 変数は、コンマで区切られたファイル拡張子のリストです。

サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | トラフィック／サイトトラフィック／ファイルのダウンロード数 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

Folio Builder *`linkDownloadFileTypes`* 変数は、*`trackDownloadLinks`* が「True」に設定されている場合にのみ関係します。

リンク上でマウスを左クリックした場合にのみ、[!UICONTROL ファイルのダウンロード数]レポートでカウントされます。ページが読み込まれたときに自動的に開始されるファイルダウンロード、またはリダイレクトの後で実行されるファイルダウンロードはすべて、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。ファイルを右クリックし「対象をファイルに保存」オプションを選択した場合も、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。

Folio Builder *`linkDownloadFileTypes`* 変数は、RSS フィードに対するクリック数を追跡するために使用することができます。.xml または他の拡張子を持つ RSS フィードへのリンクがある場合は、*`linkDownloadFileTypes`* リストに「,xml」を追加すると、各 RSS リンクのクリック回数を確認できます。

## 構文と可能な値

ファイル拡張子のみ含めます（スペースなし）。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

リストにはどのようなファイル拡張子でも含めることができます。htm や aspx のような一般的なファイル拡張子は、*`linkDownloadFileTypes`* と呼ばれる iFrame を読み込みます。これらの拡張子を含めると、クリックごとに余分なイメージリクエストが送信されることになり、これはプライマリサーバーコールとして請求されます。

## 例

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## 設定*

なし

## 注意事項、質問、ヒント

* ダウンロードファイルを左クリックした場合のみ、URL が[!UICONTROL ファイルのダウンロード数レポート]に表示されます。
* 共通のファイル拡張子を&#x200B;*`linkDownloadFileTypes`* に一般的なファイル拡張子を含めると、Adobe のサーバーに送信されるサーバーコール総数が大幅に増えることがあります。
* サーバーサイドでのリダイレクトへのリンクやファイルのダウンロードを自動的に開始する HTML ページはカウントされません（ファイル拡張子が *`linkDownloadFileTypes`* の場合を除く）。
* JavaScript（javascript:openLink( ) など）を使用するリンクは、ファイルのダウンロード数にはカウントされません。

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