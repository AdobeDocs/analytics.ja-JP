---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s_objectID

変数は、リンクの [!UICONTROL onClick] イベントに設定する必要があるグローバル変数です。


<!-- 

s_objectID.xml

 -->

リンクまたはページのリンクの場所に対して固有のオブジェクト ID を作成することにより、訪問者のアクティビティのトラッキングを向上したり、[!UICONTROL Activity Map] を使用して、リンク URL ではなく、リンクタイプやリンクの場所について報告します。

> [!NOTE] s_objectIDを [Activity Mapで使用する場合は、末尾にセミコロン(;)が必要です](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html)。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | OID | [!UICONTROL Activity Map]、[!UICONTROL ClickMap] | クリックされたリンクの絶対 URL |

3 つの一般的な理由で  *`s_objectID`* を使用します。

* 1 日のうちに頻繁に変化する訪問者のアクティビティを集計するため。
* [!UICONTROL Activity Map] が組み合わせるリンクアクティビティを分類するため。
* [!UICONTROL Activity Map] データレポートの精度を向上させるため。

**非常に動的なリンクに対するクリック数を集計する** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

サイトが非常に動的で、一部のページ上のリンクが 1 日を通して変化する場合は、*`s_objectID`* を使用してページ上のリンクの場所を特定できます。たとえば、*`s_objectID`*&#x200B;が、ページjの左上の最初のリンクを示す「top left 1」や「top left 2」に設定されている場合、その場所に表示される（または *`s_objectID`* を同じ変数に設定している）すべてのリンクは、訪問者クリックマップと共に報告されます。*`s_objectID`* を使用しない場合は、特定のリンクがクリックされた回数が表示されますが、その場所にある他のすべてのリンクがサイトの訪問者によってどのように使用されたかを理解することはできなくなります。

**合算されるクリック数を分解する** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

訪問者が閲覧している特定のページではなく、訪問者が閲覧しているセクションまたはテンプレートを表示するためにサイトの *`pageName`* 変数を使用する場合は、*`s_objectID`* を使用して、そのページテンプレートの複数のバージョンに表示されるリンクを分類できます。例えば、1 つのテンプレートページでサイト上のすべての製品に対応している場合、すべてのページに、そのテンプレートからホームページおよび検索ボックスへ移動するリンクが表示される可能性があります。これらのリンクが、テンプレートごとではなく、個々の製品ごとにどのように使用されているかを確認する場合は、*`s_objectID`* に、「prod 123789 home page」や「prod 123789 search」などの製品固有の値を入力できます。一旦完了すると、それらのリンクの [!UICONTROL Activity Map] レポートは個々の製品単位になります。

**[!UICONTROL Activity Map]の精度の向上** {#section_08B3406821294DCCABEEB99C90CF5C52}

Internet Explorer、Firefox、Netscape、Opera、Safari 以外のブラウザーはレポートされないことがあります。このような状況が発生する割合が小さくても、クリック数やその他の指標に影響することがあります。*`s_objectID`* を使用して、それらを一意に識別することで、ブラウザーのレポートに関する問題を解決します。*`s_objectID`* を使用するためにリンクを更新する方法の例を次に示します。

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**構文と可能な値** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID にはテキストの識別子を含めることができます。

```js
s_objectID="unique_id" 
```

標準の変数の制限以外、*`s_objectID`* に対する制限はありません。

**例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**設定** {#section_95396657D55B41ECB66B83D0534EA827}

なし
