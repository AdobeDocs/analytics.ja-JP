---
description: Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。
title: リンクトラッキングの FAQ
topic: Activity map
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '522'
ht-degree: 100%

---


# リンクトラッキングの FAQ

Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。

>[!CAUTION]
>
>Activity Map トラッキングをオンにすると、**個人を特定できる情報（PII）のデータを収集できます。**&#x200B;このデータは、そのまま使用するか、その他の情報と共に使用して、個人を特定および検索したり、個人と連絡を取ったり、コンテキスト内で個人を特定したりすることができます。

Activity Map トラッキングによって PII データが収集される可能性がある既知のケースには次のようなものがあります。

* `Mailto` リンク。mailto リンクは、メールを送信するためにコンピューター上のデフォルトのメールクライアントを起動するの HTML リンクです。
* `User ID` リンク。ユーザーがログインすると、Web サイトのヘッダー／フッターに表示される場合があります。
* 金融機関では、口座番号がリンクとして表示されている場合があります。そのリンクをクリックすると、リンクのテキストが収集されます。
* また、医療関連の Web サイトでも、PII データがリンクとして表示されている場合があります。これらのリンクをクリックすると、リンクのテキストが収集されるので、PII データが収集されることになります。

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>質問：リンクトラッキングはいつおこなわれますか。</b> <p> </p> </td> 
   <td colname="col2"> 回答：Activity Map のリンクと領域の識別は、ユーザーがページをクリックしたときに行われます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>質問：デフォルトでは何が追跡されますか。</b> <p> </p> </td> 
   <td colname="col2"> 回答：要素に関してクリックイベントが発生した場合、その要素はいくつかのチェックに合格し、AppMeasurement によってリンクとして処理されるかどうかを特定する必要があります。チェックは以下のとおりです。 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">HREF プロパティを含む &lt;A&gt; タグまたは &lt;AREA&gt; タグかどうか </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">s_objectID 変数を設定するオンクリック属性があるかどうか </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">値または子テキストを持つ INPUT タグまたは SUBMIT ボタンかどうか </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">タイプが IMAGE で src プロパティを持つ INPUT タグかどうか </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">&lt;Button&gt; かどうか </li> 
    </ul> <p>上記のいずれかの質問に対する答が<b>はい</b>の場合、要素はリンクとして処理され、追跡されます。 </p> <p>重要：AppMeasurement では、属性 type="button" を含む button タグは、リンクと見なされません。button タグから "type='button'" を削除して、代わりに role="button" または submit="button" を追加することを検討してください。 </p> <p>重要：AppMeasurement では、「#」で開始する href を含むアンカータグは、リンクではなく、内部のターゲット場所と見なされます（ページを離れないので）。デフォルトでは、Activity Map は、これらの内部のターゲット場所を追跡しません。ユーザーを新しいページにナビゲートするリンクのみを追跡します。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>質問：Activity Map では、その他の視覚的 HTML 要素をどのように追跡しますか。</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b><code> s.tl() </code> 関数を使用</b> <p>s.tl 呼び出し経由でクリックが発生した場合、Activity Map もこのクリックイベントを受け取り、linkName 文字列値が見つかったかどうかを特定します。s.tl の実行中に、その linkName が Activity Map のリンク ID として設定されます。クリックされた、s.tl() 呼び出しを起源とする要素は、領域を特定するために使用されます。例： </p> <p> 
       <code>
         &lt;img&amp;nbsp;onclick="s.tl(true,'o','abc')"&amp;nbsp;src="someimageurl.png"/&gt; 
       </code> </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b><code> s_objectID </code> 変数を使用</b> <p>例： </p> <p> 
       <code>
         &lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt; &lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;Link&nbsp;Text&nbsp;Here&lt;/a&gt;
       </code> </p> <p>重要：Activity Map で s_objectID を使用する場合、末尾のセミコロン（;）は必須です。 </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>質問：追跡されるリンクの例をいくつか示してください。</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>
        &lt;a&amp;nbsp;href="/home"&gt;Home&lt;/a&gt; 
      </code> </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>
        &lt;input&amp;nbsp;type="submit"&amp;nbsp;value="Submit"/&gt; 
      </code> </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>
        &lt;input&amp;nbsp;type="image"&amp;nbsp;src="submit-button.png"/&gt; 
      </code> </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>
        &lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>
        &lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/div&gt;
      </code> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>質問：追跡されないリンクの例をいくつか示してください。</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">理由：アンカータグに有効な href が含まれていない 
      <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">理由：<code> s_ObjectID </code> も <code> s.tl() </code> も存在しない
      <code>
        &lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">理由：<code> s_ObjectID </code> も <code> s.tl() </code> も存在しない
      <code>
        &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">理由：src プロパティにフォーム入力要素がない 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
