---
description: リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。
keywords: Analytics の実装
subtopic: Redirects
title: リダイレクトとエイリアス
topic: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 100%

---


# リダイレクトとエイリアス

リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。

## リダイレクトとエイリアス {#concept_F4F1D53D473947FE8554897332545763}

リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。

リダイレクトにはユーザーの介入が不要なので、多くの場合、実行の際にユーザーに通知されることはありません。リダイレクトがおこなわれたかどうかを判断する唯一の方法は、ブラウザーのアドレスバーを確認することです。アドレスバーには、ブラウザーが最初に要求したリンクとは異なる URL が表示されます。

リダイレクトのタイプは 2 つのみですが、実装方法は様々です。例えば、ユーザーがブラウザーの転送先として指定した Web ページに、ブラウザーを別の URL にリダイレクトするスクリプトや特殊な HTML コードが含まれている場合は、クライアントサイドのリダイレクトをおこなうことができます。サーバーサイドのスクリプトがページに含まれている場合や、ユーザーを別の URL に転送するように Web サーバーが設定されている場合は、サーバーサイドのリダイレクトをおこなうことができます。

## Analytics とリダイレクト {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] では、一部のデータをブラウザーから収集し、特定のブラウザープロパティを使用します。これらのプロパティのうちの 2 つである「参照 URL」（リファラー）と「現在の URL」は、サーバーサイドのリダイレクトによって変更できます。ブラウザーは、ある URL が要求されたにもかかわらず別の URL が返されたことを認識しているので、参照 URL をクリアします。結果として参照 URL は空白になり、[!DNL Analytics] では、ページのリファラーが存在しないと報告される場合があります。

## 例：リダイレクトを使用しない場合のブラウザーでの表示 {#section_5C835A4D665A4625A23333C2C21F152D}

次に示す仮定のシナリオについて検討してください。このシナリオでは、ユーザーがリダイレクトされることはありません。

1. ユーザーがブラウザーで `www.google.com` を参照し、検索フィールドに「discount airline tickets」と入力して、「**[!UICONTROL 検索]**」ボタンをクリックします。
1. サイト [!DNL https://www.example.com/] へのリンクを含む検索結果がブラウザーに表示されます。検索結果が表示された後、ブラウザーのアドレスバーには、ユーザーが検索フィールドに入力した検索語句が表示されます（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）。検索語句は、`https://www.google.com/search?` の後に続く URL クエリー文字列パラメーターに含まれます。
1. ユーザーが仮想サイト [!DNL https://www.example.com/] へのリンクをクリックします。ユーザーがこのリンクをクリックして Web サイト [!DNL example.com] を参照すると、[!DNL Analytics] では JavaScript を使用して参照 URL（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）および現在の URL（`https://www.example.com/`）を収集します。
1. [!DNL Analytics] は、この処理で収集した情報を様々なレポート（[!UICONTROL 参照ドメイン]、[!UICONTROL 検索エンジン]、[!DNL Search Keywords]）で報告します。

## 例：リダイレクトを使用する場合のブラウザーでの表示 {#section_921DDD32932847848C4A901ACEF06248}

リダイレクトを使用すると、ブラウザーで実際の参照 URL を空白にすることができます。次のシナリオについて検討してください。

1. ユーザーがブラウザーで `https://www.google.com` を参照し、検索フィールドに「*discount airline tickets*」と入力して、「**[!UICONTROL 検索]**」ボタンをクリックします。
1. ブラウザーウィンドウのアドレスバーには、ユーザーが検索フィールドに入力した検索語句が表示されます（`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）。検索語句は、`https://www.google.com/search?` の後に続く URL クエリー文字列パラメーターに含まれます。また、ブラウザーには、いずれかのドメイン名へのリンク （[!DNL https://www.flytohawaiiforfree.com/]） が記載された検索結果を含むページが表示されます。この「*バニティ*」ドメインは、ユーザーを `https://www.example.com/` にリダイレクトするように設定されます。
1. ユーザーがリンク `https://www.flytohawaiiforfree.com/` をクリックすると、サーバーによってメインサイト `https://www.example.com` にリダイレクトされます。このリダイレクトが発生すると、ブラウザーが参照 URL をクリアするので、[!DNL Analytics] のデータ収集にとって重要なデータが失われます。したがって、[!DNL Analytics] レポートで使用されるオリジナルの検索情報（[!UICONTROL 参照ドメイン]、[!UICONTROL 検索エンジン]、[!UICONTROL 検索キーワード]など）が失われます。

## リダイレクトの実装 {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

リダイレクトから [!DNL Analytics] データを取り込むには、リダイレクトを生成するコードと JavaScript 版 ファイル用 [!DNL AppMeasurement] に、4 つの小規模な変更をおこなう必要があります。

<!-- 

redirects_implement.xml

 -->

以下の手順を実行すると、オリジナルリファラー（前述のシナリオでは `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`）からサイトに渡される情報が保持されます。

## リファラーに優先する JavaScript コードの設定 {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

以下のコードスニペットには、*`s_referrer`* と *`s_pageURL`* という 2 つの JavaScript 変数が含まれています。このコードは、リダイレクトの最終的なランディングページに配置します。

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
>ページで 1 回だけ *`s.referrer`* を設定します。トラッキングコールごとに、またはトラッキングされるリンククリックごとに複数回設定すると、リファラーおよび関連するディメンション（検索エンジンとキーワードなど）が二重カウントされる原因になります。

## getQueryParam を使用したリダイレクト {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

[!UICONTROL getQueryParam] を使用すると [!DNL Analytics] 変数にクエリー文字列の値を容易に設定できますが、クエリー文字列が空の場合に正規のリファラーが上書きされないように、一時変数と共にそのプラグインを導入する必要があります。[!UICONTROL getQueryParam] を使用する最善の方法は、次の擬似コードで説明するとおりに、[!UICONTROL getValue] プラグインと組み合わせることです。

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

## リダイレクトのメカニズムの変更 {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

ブラウザーによって参照元 URL が取り除かれるので、リダイレクトをおこなうメカニズム（Web サーバー、サーバーサイドのコード、クライアントサイドのコードなど）で、オリジナルリファラーの情報が渡されるように設定する必要があります。エイリアスリンクの URL も記録したい場合、この URL も最終的なランディングページに渡す必要があります。その場合は、*`s_pageURL`* 変数を使用して、現在の URL に優先させます。

リダイレクトの実装には多くの方法があるので、Web オペレーショングループやオンライン広告パートナーと協力して、貴社の Web サイトでリダイレクトが実行されるメカニズムを特定する必要があります。

## オリジナルリファラーの取り込み {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

通常、[!DNL Analytics] はブラウザーの [!UICONTROL document.referrer] プロパティから参照元 URL を取得し、[!UICONTROL document.location] プロパティから現在の URL を取得します。*`referrer`* および *`pageURL`* 変数に値を渡すことで、デフォルトの処理を上書きできます。referrer 変数に値を渡すと、[!UICONTROL document.referrer] プロパティのリファラー情報を無視し、指定した別の値を使用するよう [!DNL Analytics] に指示することになります。

したがって、「discount airline tickets」のシナリオで示される問題を修正するには、最終バージョンのランディングページに次のコードを含める必要があります。

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Adobe Debugger によるリファラーの確認 {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

リファラー、発信元 URL（*`s_server`*）およびキャンペーン変数が取り込まれていることを確認するために、テストを実行します。

[Experience Cloud デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja-JP)では、これらの変数が次のパラメーターで表されます。

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL またはクエリー文字列の値</b> </th> 
   <th class="entry"> <b>DigitalPulse Debugger に表示される値</b> </th> 
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
   <td> <p> <span class="filepath">https://www.flytohawaiiforfree.com</span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p><span class="varname"> pageURL</span> 変数を使用している場合、この値は DigitalPulse Debugger に表示されます。 </p> </td> 
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
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
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
