---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

 変数は、コンマで区切られたファイル拡張子のリストです。

サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | トラフィック／サイトトラフィック／ファイルのダウンロード数 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

*`linkDownloadFileTypes`* 変数は、*`trackDownloadLinks`* が「True」に設定されている場合にのみ関係します。

リンク上でマウスを左クリックした場合にのみ、[!UICONTROL ファイルのダウンロード数]レポートでカウントされます。ページが読み込まれたときに自動的に開始されるファイルダウンロード、またはリダイレクトの後で実行されるファイルダウンロードはすべて、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。ファイルを右クリックし「対象をファイルに保存」オプションを選択した場合も、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。

*`linkDownloadFileTypes`* 変数は、RSS フィードに対するクリック数を追跡するために使用することができます。.xml または他の拡張子を持つ RSS フィードへのリンクがある場合は、*`linkDownloadFileTypes`* リストに「,xml」を追加すると、各 RSS リンクのクリック回数を確認できます。

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
* 一般的なファイル拡張子を  *`linkDownloadFileTypes`* に含めると、Adobe のサーバーに送信されるサーバーコール総数が大幅に増えることがあります。
* サーバーサイドでのリダイレクトへのリンクやファイルのダウンロードを自動的に開始する HTML ページはカウントされません（ファイル拡張子が *`linkDownloadFileTypes`* の場合を除く）。
* JavaScript（javascript:openLink( ) など）を使用するリンクは、ファイルのダウンロード数にはカウントされません。

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