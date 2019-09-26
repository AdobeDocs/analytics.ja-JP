---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.linkInternalFilters

 変数は、サイトのどのリンクが離脱リンクであるかを判別するために使用されます。

これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク |  |

>[!NOTE]
>
>以前は、linkInternalFiltersをjavascript：に設定することを推奨していました。 この方法では、タグが設定されている現在のドメインを含め、すべてのドメインが外部と認識されます。一部のドメインが内部と認識されるようにする場合は、以下の例のように、それらのドメインを追加できます。

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. 離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。離脱リンクは、*`trackExternalLinks`* が `"true"` に設定されている場合に、スウォッチ選択の変更を発生させる秒単位の時間遅延です。（DTM による離脱リンクの処理方法について詳しくは、Dynamic Tag Management のドキュメントの[リンクトラッキング](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)を参照してください）のフィルターでは、大 *`linkInternalFilters`* 文字と小文字が区別されません。

のフィルターのリストは、デ *`linkInternalFilters`* フォルトではリンクのドメインとパスに適用されます。 If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

貴社のサイトのすべてのドメイン（および貴社の JavaScript ファイルを使用しているすべてのパートナー）は、*`linkInternalFilters`* と呼ばれる iFrame を読み込みます。すべてのドメインをリストに含めていない場合、それらのドメイン上にあるリンクとそれらのドメインへのリンクはすべて、離脱リンクであると見なされ、送信されるサーバーコールの数が増加します。複数のドメインまたは会社で単一の [!DNL AppMeasurement] for javaScriptファイルを使用する場合は、JavaScriptファイルで指定された値を上書きして、ページに *`linkInternalFilters`* データを埋め込むことを検討してください。 直ちにメインドメインへリダイレクトされるバニティドメインがある場合、それらのバニティドメインをリストに含める必要はありません。

次の例では、この変数の使用方法を示します。In this example, the URL of the page is `https://www.mysite.com/index.html`.

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

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. スペースは使用できません。

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

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* [!UICONTROL パス]／[!UICONTROL 入口と出口]／[!UICONTROL 離脱]リンクのレポートを定期的に調べて、レポートに含まれるエントリがすべて正しいことを確認してください。

* 定期的にパートナー契約を調べて、契約にリンクトラッキングに関する制限が含まれているかどうかを確認してください。例えば、パートナーのディスプレイ広告に表示されるリンクのトラッキングが禁止されている場合があります。次のようにパートナーのドメインを  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
