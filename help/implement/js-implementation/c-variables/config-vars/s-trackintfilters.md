---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
