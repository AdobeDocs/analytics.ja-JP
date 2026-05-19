---
description: ユーザー操作なしで、ブラウザーを新しい場所にリダイレクトします。 リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。
keywords: Analytics の実装
title: リダイレクトとエイリアス
feature: Implementation Basics
exl-id: 0ed2aa9b-ab42-415d-985b-2ce782b6ab51
TQID: https://experienceleague.adobe.com/iDwKqSKsjzEvgVCNKdTwDZHN2cPDmsuM1SV7PLisw3g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 1139
ht-degree: 73%

---

# リダイレクトとエイリアス

ユーザー操作なしで、ブラウザーを新しい場所にリダイレクトします。 リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。

## リダイレクトとエイリアス {#aliases}

ユーザー操作なしで、ブラウザーを新しい場所にリダイレクトします。 リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。

リダイレクトはユーザーの操作を必要としないため、リダイレクトはユーザーに気づかれることなく実行されることがよくあります。 リダイレクトが発生したことを示す唯一のものは、ブラウザーのアドレスバーです。 アドレスバーには、ブラウザーが最初に要求したリンクとは異なるURLが表示されます。

リダイレクトには2種類しかありませんが、多くの方法で実装できます。 例えば、クライアント側のリダイレクトは、ユーザーがブラウザーを指定したweb ページに、ブラウザーを別のURLにリダイレクトするスクリプトまたは特殊なHTML コードが含まれている場合に発生する可能性があります。 サーバーサイドリダイレクトは、ページにサーバーサイドスクリプトが含まれているか、web サーバーがユーザーを別のURLに誘導するように設定されているために発生する可能性があります。

## Analytics とリダイレクト {#aa-redirects}

[!DNL Analytics] では、一部のデータをブラウザーから収集し、特定のブラウザープロパティを使用します。 これらのプロパティのうち、「参照URL」（または「リファラー」）と「現在のURL」の2つは、サーバーサイドのリダイレクトで変更できます。 ブラウザーは、1つのURLがリクエストされたが、別のURLが返されたことを認識しているため、参照URLをクリアします。 結果として参照 URL は空白になり、[!DNL Analytics] では、ページのリファラーが存在しないと報告される場合があります。

## 例：リダイレクトを使用しない場合のブラウザーでの表示 {#browse-without}

次に示す仮定のシナリオについて検討してください。このシナリオでは、ユーザーがリダイレクトされることはありません。

1. ユーザーがブラウザーで `www.google.com` を参照し、検索フィールドに「discount airline tickets」と入力して、「**[!UICONTROL 検索]**」ボタンをクリックします。
1. サイト [!DNL https://www.example.com/] へのリンクを含む検索結果がブラウザーに表示されます。 検索結果が表示された後、ブラウザーのアドレスバーには、ユーザーが検索フィールドに入力した検索語句が表示されます（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）。 検索語句は、`https://www.google.com/search?` の後に続く URL クエリ文字列パラメーターに含まれます。
1. ユーザーが仮想サイト [!DNL https://www.example.com/] へのリンクをクリックします。 ユーザーがこのリンクをクリックして Web サイト [!DNL example.com] を参照すると、[!DNL Analytics] では JavaScript を使用して参照 URL（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）および現在の URL（`https://www.example.com/`）を収集します。
1. [!DNL Analytics] は、この処理で収集した情報を様々なレポート（[!UICONTROL 参照ドメイン]、[!UICONTROL 検索エンジン]、[!DNL Search Keywords]）で報告します。

## 例：リダイレクトを使用する場合のブラウザーでの表示 {#browse-with}

リダイレクトにより、ブラウザーで真の参照URLが空白になる場合があります。 次のシナリオについて検討してください。

1. ユーザーがブラウザーで `https://www.google.com` を参照し、検索フィールドに「*discount airline tickets*」と入力して、「**[!UICONTROL 検索]**」ボタンをクリックします。
1. ブラウザーウィンドウのアドレスバーには、ユーザーが検索フィールドに入力した検索語句が表示されます（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）。 検索語句は、`https://www.google.com/search?` の後に続く URL クエリ文字列パラメーターに含まれます。 また、ブラウザーには、いずれかのドメイン名へのリンク （[!DNL https://www.flytohawaii.example/]） が記載された検索結果を含むページが表示されます。 この「*バニティ*」ドメインは、ユーザーを `https://www.example.com/` にリダイレクトするように設定されます。
1. ユーザーがリンク `https://www.flytohawaii.example/` をクリックすると、サーバーによってメインサイト `https://www.example.com` にリダイレクトされます。 このリダイレクトが発生すると、ブラウザーが参照 URL をクリアするので、[!DNL Analytics] のデータ収集にとって重要なデータが失われます。 したがって、[!DNL Analytics] レポートで使用されるオリジナルの検索情報（[!UICONTROL 参照ドメイン]、[!UICONTROL 検索エンジン]、[!UICONTROL 検索キーワード]など）が失われます。

## リダイレクトの実装 {#implement}

リダイレクトから [!DNL Analytics] データを取り込むには、リダイレクトを生成するコードと JavaScript 版 ファイル用 [!DNL AppMeasurement] に、4 つの小規模な変更をおこなう必要があります。

以下の手順を実行すると、オリジナルリファラー（前述のシナリオでは `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）からサイトに渡される情報が保持されます。

## リファラーに優先する JavaScript コードの設定 {#override}

以下のコードスニペットには、`s.referrer` と `s.pageURL` という 2 つの JavaScript 変数が含まれています。 このコードは、リダイレクトの最終的なランディングページに配置します。

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>ページで 1 回だけ *`s.referrer`* を設定します。 トラッキングコールごとに、またはトラッキングされるリンククリックごとに複数回設定すると、リファラーおよび関連するディメンション（検索エンジンとキーワードなど）が二重カウントされる原因になります。

## getQueryParam を使用したリダイレクト {#getqueryparam}

[!UICONTROL getQueryParam] を使用すると [!DNL Analytics] 変数にクエリ文字列の値を容易に設定できますが、クエリ文字列が空の場合に正規のリファラーが上書きされないように、一時変数と共にそのプラグインを導入する必要があります。 [!UICONTROL getQueryParam] を使用する最善の方法は、次の擬似コードで説明するとおりに、[!UICONTROL getValue] プラグインと組み合わせることです。

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## リダイレクトのメカニズムの変更 {#modify}

ブラウザーは参照URLを取り除くため、リダイレクトを処理するメカニズム（web サーバー、サーバーサイドコード、クライアントサイドコードなど）を設定して、元のリファラー情報を渡す必要があります。 エイリアスリンク URLも記録する場合は、これを最終的なランディングページにも渡す必要があります。 現在のURLを上書きするには、*`s_pageURL`*&#x200B;変数を使用します。

リダイレクトの実装には多くの方法があるので、Web オペレーショングループやオンライン広告パートナーと協力して、貴社の Web サイトでリダイレクトが実行されるメカニズムを特定する必要があります。

## オリジナルリファラーの取り込み {#original}

通常、[!DNL Analytics] はブラウザーの [!UICONTROL document.referrer] プロパティから参照元 URL を取得し、[!UICONTROL document.location] プロパティから現在の URL を取得します。 *`referrer`* および *`pageURL`* 変数に値を渡すことで、デフォルトの処理を上書きできます。 referrer 変数に値を渡すと、[!UICONTROL document.referrer] プロパティのリファラー情報を無視し、指定した別の値を使用するよう [!DNL Analytics] に指示することになります。

したがって、「discount airline tickets」のシナリオで示される問題を修正するには、最終バージョンのランディングページに次のコードを含める必要があります。

```js
<script language="JavaScript" src="AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaii.example"
```

## Adobe Debugger によるリファラーの確認 {#verify}

リファラー、発信元 URL（*`s_server`*）およびキャンペーン変数が取り込まれていることを確認するために、テストを実行します。

これらの変数は、[CX Enterprise Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)で次のパラメーターとして表されます。

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL またはクエリ文字列の値</b> </th> 
   <th class="entry"> DigitalPulse Debuggerに表示されている<b>値</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>オリジナルリファラー </p> </td> 
   <td> <p> <span class="filepath">https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Btickets</span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=discount+airline+tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ページ URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaii.example </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaii.example </span> </p> <p><span class="varname"> pageURL</span> 変数を使用している場合、この値は DigitalPulse Debugger に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最終的なランディングページ URL </p> </td> 
   <td> <p> <span class="filepath">https://www.example.com</span> </p> </td> 
   <td> <p><span class="varname"> pageURL</span> 変数を使用している場合、この値は DigitalPulse Debugger に表示されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

デバッガーに表示されるテキストは次の例のようになります。

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/20XX 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaii.example 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

これらの変数が Adobe [!UICONTROL Debugger] に表示されていることを確認したら、検索語句および（リダイレクト前の）オリジナルの参照ドメインがレポートにトラフィックを登録していることを確認すると有用です。
