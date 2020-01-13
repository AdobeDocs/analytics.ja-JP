---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---



# s.linkInternalFilters

 変数は、サイトのどのリンクが出口リンクであるかを判別するために使用されます。

これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク |  |

> [!NOTE]以前までは、linkInternalFilters を javascript: に設定することを推奨していましたが、この方法では、タグが設定されている現在のドメインを含め、すべてのドメインが外部と認識されます。一部のドメインが内部と認識されるようにする場合は、以下の例のように、それらのドメインを追加できます。

*`linkInternalFilters`* 変数は、リンクが出口リンクであるかどうかを判別するために使用されます。出口リンクとは、訪問者がサイトから出て行くリンクとして定義されます。出口リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが出口リンクレポートに表示されるかどうかに影響しません。出口リンクは、*`trackExternalLinks`* が `"true"` に設定されている場合に、スウォッチ選択の変更を発生させる秒単位の時間遅延です。（DTM による出口リンクの処理方法について詳しくは、Dynamic Tag Management のドキュメントの[リンクトラッキング](https://marketing.adobe.com/resources/help/ja_JP/dtm/link_tracking.html)を参照してください）*`linkInternalFilters`* のフィルターでは、大文字と小文字が区別されません。

*`linkInternalFilters`* のフィルターのリストは、デフォルトではリンクのドメインとパスに適用されます。*`linkLeaveQueryString`* が `"true"` に設定されている場合、フィルターは URL 全体（ドメイン、パス、クエリー文字列）に適用されます。これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

貴社のサイトのすべてのドメイン（および貴社の JavaScript ファイルを使用しているすべてのパートナー）は、*`linkInternalFilters`* と呼ばれる iFrame を読み込みます。すべてのドメインをリストに含めていない場合、それらのドメイン上にあるリンクとそれらのドメインへのリンクはすべて、出口リンクであると見なされ、送信されるサーバーコールの数が増加します。複数のドメインまたは会社で単一の JavaScript 版 [!DNL AppMeasurement] ファイルを使用する場合は、JavaScript ファイルで指定された値を上書きして、ページに *`linkInternalFilters`* を入力することを検討してください。直ちにメインドメインへリダイレクトされるバニティドメインがある場合、それらのバニティドメインをリストに含める必要はありません。

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
* [!UICONTROL パス]／[!UICONTROL 入口と出口]／[!UICONTROL 出口リンク]のレポートを定期的に調べて、レポートに含まれるエントリがすべて正しいことを確認してください。

* 定期的にパートナー契約を調べて、契約にリンクトラッキングに関する制限が含まれているかどうかを確認してください。例えば、パートナーのディスプレイ広告に表示されるリンクのトラッキングが禁止されている場合があります。次のようにパートナーのドメインを&#x200B;*`linkInternalFilters`* に追加してパートナーのリンクをフィルタリングしまｍす。

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

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
