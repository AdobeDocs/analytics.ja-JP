---
description: この表は、マーケティングチャネルの処理ルールページで選択可能なフィールド、オプションおよびヒット属性を定義しています。
seo-description: この表は、マーケティングチャネルの処理ルールページで選択可能なフィールド、オプションおよびヒット属性を定義しています。
seo-title: マーケティングチャネルの処理ルール - 定義
solution: Analytics
subtopic: マーケティングチャネル
title: マーケティングチャネルの処理ルール - 定義
topic: Reports & Analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# マーケティングチャネルの処理ルール - 定義

この表は、マーケティングチャネルの処理ルールページで選択可能なフィールド、オプションおよびヒット属性を定義しています。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>用語 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>すべて </p> </td> 
   <td colname="col2"> <p>番号付きルール内のすべてのルールが真の時にのみ、このチャネルをアクティブにします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>いずれか </p> </td> 
   <td colname="col2"> <p>ルールセット内のいずれかのルールが真のときに、このチャネルをアクティブにします。このオプションは、番号付きルール内に 2 つ以上ルールが存在している場合にのみ利用可能です。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p>Advertising cloudとAdvertising Analyticsの統合で使用される主なトラッキングコード。 これらの統合の1つが有効な場合、トラッキングコードプレフィックスを使用してAdvertising cloud固有のチャネルを識別できます。 「AMO ID」は、検索には「AL」、表示には「AC」、Socialには「AO」で始まる名前を使用します。 AMO IDをマーケティングチャネルで使用する場合、クリック/コスト/インプレッション指標を正しいチャネルに関連付けることができます（設定されていない場合、これらの指標は直接またはなしになります）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>Advertising cloudで使用されるセカンダリトラッキングコード。 このトラッキングコードの主な目的は、Ad cloudにデータを返送する際の鍵となることです。 ただし、2つの異なるマーケティングチャネルとして表示したい場合は、表示クリックスルー数と表示ビュースルーを識別するためにも使用できます。 これは、「表示クリックスルー」の場合は「AMO EF ID」のマーケティングチャネルロジックを「:d」で終わるように設定し、「表示ビュースルー」の場合は「:i」で終わるように設定することで可能です。 「表示」を2つのチャネルに分割しない場合は、代わりにAMO IDディメンションを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンバージョン変数 </p> </td> 
   <td colname="col2"> <p>このレポートスイート用に有効になっている eVar から構成され、これらの変数がページ上の Adobe コード経由で設定された場合にのみ適用されます。 </p> <p>『<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf" scope="external" format="html">導入マニュアル</a>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>存在する </p> </td> 
   <td colname="col2"> <p>以下のオプションを選択できます。 </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">が存在しない</span>：ヒット属性がリクエストに存在しないことを示します。たとえば、参照ドメインで、ユーザーが URL を入力するかブックマークをクリックすると、その参照ドメイン属性は存在しません。 </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol">が空である</span>：ヒット属性（通常は eVar またはクエリ文字列パラメーター）は存在しますが、そのヒット属性に関連付けられた値がないことを示します。 </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> 次を含まない </span>:例えば、参照ドメインに特定の値を含めない（「次を含む」を選択するのとは異なる）ように指定で <span class="term"> きます </span>。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネルを %s として特定している </p> </td> 
   <td colname="col2"> <p><span class="wintitle">マーケティングチャネルマネージャー</span>ページに追加したマーケティングチャネルにルールを関連付けます。 </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03" type="task" format="dita" scope="local"> Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>有料検索の検出ルールに一致 </p> </td> 
   <td colname="col2"> <p>アドビによって検出された有料検索。有料検索とは、会社が自社サイトが検索結果リストに優先的に載せられるように検索エンジンに料金を支払った検索キーワードを指します。有料検索のキーワードは通常検索結果の上部または右側に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自然検索の検出ルールに一致 </p> </td> 
   <td colname="col2"> <p>アドビのレポートによって検出された無料検索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リファラーが内部 URL フィルターに一致する </p> </td> 
   <td colname="col2"> <p> 管理ツールのレポートスイートで定義されている内部 URL フィルターに一致するページ URL からのアクセス。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リファラーが内部 URL フィルターに一致しない </p> </td> 
   <td colname="col2"> <p>管理ツールにあるレポートスイートで定義されたとおり、参照 URL が内部 URL フィルターに一致しません。この設定を「ページの URL」および「存在する」と共に使用して <span class="term"> Page URL </span> and <span class="term"> Exists </span> to set up a catch-all rule, so that no visits land in the <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section" format="dita" scope="local"> No Channel Identified </a> section of the report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>内部 URL フィルターに一致するヒットを無視する </p> </td> 
   <td colname="col2"> <p>（リファラーに対して）外部参照サイトからのヒットのみをトラッキングします。内部トラフィックを含める場合以外、通常はこの設定を有効にしておきます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問の最初のページ </p> </td> 
   <td colname="col2"> <p>アドビのレポートで検出された訪問の最初のページ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページ </p> </td> 
   <td colname="col2"> <p>アドビのWebビーコンを使用してタグ付けされた、サイト上のWebページのページ名。 This value is equivalent to <span class="varname"> s.pageName </span>. 例としては、ホ <span class="varname"> ームページ </span> や会社 <span class="varname"> 案内がありま </span>す。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページドメイン </p> </td> 
   <td colname="col2"> <p><span class="filepath">products.example.co.uk</span> など、訪問者が到着したページのドメイン。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページドメインとパス </p> </td> 
   <td colname="col2"> <p>ドメインとパス（例：<span class="filepath">products.example.co.uk/mens/pants/overview.html</span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページルートドメイン（TLD+1） </p> </td> 
   <td colname="col2"> <p><span class="filepath">example.co.uk</span> など、訪問者が到着したページのルートドメイン。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページ URL </p> </td> 
   <td colname="col2"> <p>サイトの Web ページの URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照ドメイン </p> </td> 
   <td colname="col2"> <p>サイトにアクセスする前に訪問者が来たドメイン。例えば、<span class="filepath">abcsite.com</span> から来たリファラーや <span class="filepath">xyzsite.com</span> から来たリファラーなどです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クエリ文字列パラメーター </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>１ つのルールセットにつき 1 つだけクエリ文字列パラメーターを指定できます。クエリ文字列パラメーターをさらに追加するには、「<span class="uicontrol">いずれか</span>」演算子を使用して、ルールに新しいクエリ文字列パラメーターを追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リファラー </p> </td> 
   <td colname="col2"> <p>サイトにアクセスする前に訪問者が閲覧していた Web ページの場所（フル URL）。リファラーは、定義ドメインの外側に存在します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照ドメインとパス </p> </td> 
   <td colname="col2"> <p>参照ドメインと URL パスを短縮したもの。次のような例があります。 </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照パラメーター </p> </td> 
   <td colname="col2"> <p>リファラー URL のクエリ文字列パラメーター。例えば、訪問者が <span class="filepath">example.com/?page=12345&amp;cat=1</span> から来訪した場合、page と cat が参照パラメーターとなります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照ドメインのルート </p> </td> 
   <td colname="col2"> <p>リファラーのルートドメイン。リファラーは、定義ドメインの外側に存在します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>検索エンジン </p> </td> 
   <td colname="col2"> <p>訪問者をサイトに導いた Google や Yahoo! などの検索エンジン。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>検索キーワード </p> </td> 
   <td colname="col2"> <p>検索エンジンでの検索に使用された単語。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>検索エンジン + キーワード </p> </td> 
   <td colname="col2"> <p>検索エンジンを一意に識別するために検索キーワードと検索エンジンを連結したもの。例えば、computer という単語を検索した場合、検索エンジンとキーワードは次のように特定されます。 </p> 
    <code>
      Search&nbsp;Tracking&nbsp;Code&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"&lt;search_type&gt;:&lt;search&nbsp;engine&gt;:&lt;search&nbsp;keyword&gt;"&nbsp;where &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;search_type&nbsp;=&nbsp;"n"&nbsp;or&nbsp;"p",&nbsp;search_engine&nbsp;=&nbsp;"Google",&nbsp;and&nbsp;search_keyword&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"computer" 
    </code> <p><b></b> 注意：n = natural;p =有料 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネルの値を次の値に設定する </p> </td> 
   <td colname="col2"> <p>どのマーケティングチャネルが訪問者をサイトに導くかを知るだけでなく、チャネル内のどのバナー広告、検索キーワードまたは電子メールキャンペーンが訪問者のサイトアクティビティのクレジットを受け取っているかを知ることができます。 この ID は、チャネルと共に保存されるチャネル値です。この値には、ランディングページや参照 URL に埋め込まれているキャンペーン ID、検索エンジンと検索キーワードの組み合わせ、特定チャネルからの訪問者と最も正確に識別する参照 URL などがよく使用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>



