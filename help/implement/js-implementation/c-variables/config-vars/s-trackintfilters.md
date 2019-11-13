---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.linkInternalFilters

 変数は、サイトのどのリンクが離脱リンクであるかを判別するために使用されます。

これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク |  |

> [!NOTE]以前までは、linkInternalFilters を javascript: に設定することを推奨していましたが、この方法では、タグが設定されている現在のドメインを含め、すべてのドメインが外部と認識されます。一部のドメインが内部と認識されるようにする場合は、以下の例のように、それらのドメインを追加できます。

*`linkInternalFilters`* 変数は、リンクが離脱リンクであるかどうかを判別するために使用されます。離脱リンクとは、訪問者がサイトから出て行くリンクとして定義されます。離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。離脱リンクは、*`trackExternalLinks`* が `"true"` に設定されている場合に、スウォッチ選択の変更を発生させる秒単位の時間遅延です。（DTM による離脱リンクの処理方法について詳しくは、Dynamic Tag Management のドキュメントの[リンクトラッキング](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)を参照してください）*`linkInternalFilters`* のフィルターでは、大文字と小文字が区別されません。

*`linkInternalFilters`* のフィルターのリストは、デフォルトではリンクのドメインとパスに適用されます。*`linkLeaveQueryString`* が `"true"` に設定されている場合、フィルターは URL 全体（ドメイン、パス、クエリ文字列）に適用されます。これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

貴社のサイトのすべてのドメイン（および貴社の JavaScript ファイルを使用しているすべてのパートナー）は、*`linkInternalFilters`* と呼ばれる iFrame を読み込みます。すべてのドメインをリストに含めていない場合、それらのドメイン上にあるリンクとそれらのドメインへのリンクはすべて、離脱リンクであると見なされ、送信されるサーバーコールの数が増加します。複数のドメインまたは会社で単一の JavaScript 版 [!DNL AppMeasurement] ファイルを使用する場合は、JavaScript ファイルで指定された値を上書きして、ページに *`linkInternalFilters`* を入力することを検討してください。直ちにメインドメインへリダイレクトされるバニティドメインがある場合、それらのバニティドメインをリストに含める必要はありません。

次の例では、この変数の使用方法を示します。この例では、ページの URL は `https://www.mysite.com/index.html` です。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## 構文と可能な値

*`linkInternalFilters`* 変数は、ASCII 文字のコンマ区切りリストです。スペースは使用できません。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## 例

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## 設定

なし

## 注意事項、質問、ヒント

* フィルターリストには、JavaScript 版 [!DNL AppMeasurement] ファイルを使用する可能性があるすべてのドメインを含めてください。
* [!UICONTROL パス]／[!UICONTROL 入口と出口]／[!UICONTROL 離脱]リンクのレポートを定期的に調べて、レポートに含まれるエントリがすべて正しいことを確認してください。

* 定期的にパートナー契約を調べて、契約にリンクトラッキングに関する制限が含まれているかどうかを確認してください。例えば、パートナーのディスプレイ広告に表示されるリンクのトラッキングが禁止されている場合があります。次のようにパートナーのドメインを  *`linkInternalFilters`* に追加してパートナーのリンクをフィルタリングしまｍす。

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

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
