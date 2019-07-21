---
description: リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアント側のリダイレクト）または Web サーバー（サーバー側のリダイレクト）で実行されます。
keywords: Analytics の導入
seo-description: リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアント側のリダイレクト）または Web サーバー（サーバー側のリダイレクト）で実行されます。
seo-title: リダイレクトとエイリアス
solution: Analytics
subtopic: リダイレクト
title: リダイレクトとエイリアス
topic: 開発者と導入
uuid: 11f9ad7a-5c45-410f-86dd- b7d2cec2aae3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# リダイレクトとエイリアス

リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアント側のリダイレクト）または Web サーバー（サーバー側のリダイレクト）で実行されます。

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

リダイレクトとは、ユーザーの介入なしでブラウザーを新しい場所に転送することです。リダイレクトは Web ブラウザー（クライアントサイドのリダイレクト）または Web サーバー（サーバーサイドのリダイレクト）で実行されます。

リダイレクトにはユーザーの介入が不要なので、多くの場合、実行の際にユーザーに通知されることはありません。リダイレクトがおこなわれたかどうかを判断する唯一の方法は、ブラウザーのアドレスバーを確認することです。アドレスバーには、ブラウザーが最初に要求したリンクとは異なる URL が表示されます。

リダイレクトのタイプは 2 つのみですが、実装方法は様々です。例えば、ユーザーがブラウザーの転送先として指定した Web ページに、ブラウザーを別の URL にリダイレクトするスクリプトや特殊な HTML コードが含まれている場合は、クライアントサイドのリダイレクトをおこなうことができます。サーバーサイドのスクリプトがページに含まれている場合や、ユーザーを別の URL に転送するように Web サーバーが設定されている場合は、サーバーサイドのリダイレクトをおこなうことができます。

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] では、一部のデータをブラウザーから収集し、特定のブラウザープロパティを使用します。これらのプロパティのうちの 2 つである「参照 URL」（リファラー）と「現在の URL」は、サーバーサイドのリダイレクトによって変更できます。ブラウザーは、ある URL が要求されたにもかかわらず別の URL が返されたことを認識しているので、参照 URL をクリアします。結果として参照 URL は空白になり、[!DNL Analytics] では、ページのリファラーが存在しないと報告される場合があります。

<!-- 

redirects_sc.xml

 -->

次の例は、リダイレクトを使用する場合と使用しない場合に、ブラウザーでの表示にどのような影響があるかを示しています。

* [例：リダイレクトを使用しない場合のブラウザーでの表示](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [例：リダイレクトを使用する場合のブラウザーでの表示](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## 例：リダイレクトを使用しない場合のブラウザーでの表示 {#section_5C835A4D665A4625A23333C2C21F152D}

次に示す仮定のシナリオについて検討してください。このシナリオでは、ユーザーがリダイレクトされることはありません。

1. ユーザーがブラウザーで `www.google.com`**を参照し、検索フィールドに「discount airline tickets」と入力して、「[!UICONTROL 検索]」ボタンをクリックします。**
1. サイト [!DNL https://www.flywithus.com/] / へのリンクを含む検索結果がブラウザーに表示されます。After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). 検索語句は、`https://www.google.com/search?` ? の後に続く URL クエリ文字列パラメーターに含まれます。
1. ユーザーが仮想サイト [!DNL https://www.flywithus.com/] / へのリンクをクリックします。When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] は、このインタラクション中に収集された情報を様々なレポート（ [!UICONTROL 参照ドメイン]、 [!UICONTROL 検索エンジン]、およびなど）で報告 [!DNL Search Keywords]します。

## 例：リダイレクトを使用する場合のブラウザーでの表示 {#section_921DDD32932847848C4A901ACEF06248}

リダイレクトを使用すると、ブラウザーで実際の参照 URL を空白にすることができます。次のシナリオについて検討してください。

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. 検索語句は、`https://www.google.com/search?` ? の後に続く URL クエリ文字列パラメーターに含まれます。また、ブラウザーには、いずれかのドメイン名へのリンク（[!DNL https://www.flytohawaiiforfree.com/]/）が記載された検索結果を含むページが表示されます。この「バニティ」ドメインは、ユーザーを */ にリダイレクトするように設定されます。*`https://www.flywithus.com/`
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. このリダイレクトが発生すると、ブラウザーが参照 URL をクリアするので、[!DNL Analytics] のデータ収集にとって重要なデータが失われます。したがって、[!DNL Analytics] レポートで使用されるオリジナルの検索情報（[!UICONTROL 参照ドメイン]、[!UICONTROL 検索エンジン]、[!UICONTROL 検索キーワード]など）が失われます。

[リダイレクトの導入](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7)では、[!DNL Analytics] 変数を利用して、リダイレクトで失われたデータを取り込む方法について説明しています。特に、上記の「discount airline tickets」の問題の修正方法について説明している節を参照してください。

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

リダイレクトから [!DNL Analytics][!DNL AppMeasurement] データを取り込むには、リダイレクトを生成するコードと JavaScript 版 ファイルに、4 つの小規模な変更をおこなう必要があります。

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. このコードは、リダイレクトの最終的なランディングページに配置します。

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
>Set *`s.referrer`* only once on the page. トラッキングコールごとに、またはトラッキングされるリンククリックごとに複数回設定すると、リファラーおよび関連するディメンション（検索エンジンとキーワードなど）が二重カウントされる原因になります。

## getQueryParam を使用したリダイレクト {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

[!UICONTROL getQueryParam] を使用すると [!DNL Analytics] 変数にクエリ文字列の値を容易に設定できますが、クエリ文字列が空の場合に正規のリファラーが上書きされないように、一時変数と共にそのプラグインを導入する必要があります。[!UICONTROL getQueryParam] を使用する最善の方法は、次の擬似コードで説明するとおりに、[!UICONTROL getValue] プラグインと組み合わせることです。

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

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

ブラウザーによって参照元 URL が取り除かれるので、リダイレクトをおこなうメカニズム（Web サーバー、サーバーサイドのコード、クライアントサイドのコードなど）で、オリジナルリファラーの情報が渡されるように設定する必要があります。エイリアスリンクの URL も記録したい場合、この URL も最終的なランディングページに渡す必要があります。また、*`s_pageURL`* 変数を使用して、現在の URL に優先させます。

リダイレクトの実装には多くの方法があるので、Web オペレーショングループやオンライン広告パートナーと協力して、貴社の Web サイトでリダイレクトが実行されるメカニズムを特定する必要があります。

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

通常、[!DNL Analytics] はブラウザーの [!UICONTROL document.referrer] プロパティから参照元 URL を取得し、[!UICONTROL document.location] プロパティから現在の URL を取得します。By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. referrer 変数に値を渡すと、[!DNL Analytics]document.referrer[!UICONTROL  プロパティのリファラー情報を無視し、指定した別の値を使用するよう ] に指示することになります。

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

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL またはクエリ文字列の値</b> </th> 
   <th class="entry"> <b>DigitalPulse Debugger に表示される値</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>オリジナルリファラー </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3Fhl%3Den%26ie%3DUTF826q%3Ddiscount%2Bairline%2Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF-8&amp; q= discount+ airline+ tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ページ URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p><span class="varname"> pageURL </span> 変数を使用すると、この値がDigitalPulse Debuggerに表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最終的なランディングページ URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p><span class="varname"> pageURL </span> 変数が使用されている場合、この値はDigitalPulse Debuggerには表示されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

デバッガーに表示されるテキストは次の例のようになります。

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
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

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.
