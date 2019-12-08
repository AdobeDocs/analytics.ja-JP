---
description: この表は、マーケティングチャネルの処理ルールページで選択可能なフィールド、オプションおよびヒット属性を定義しています。
subtopic: Marketing channels
title: マーケティングチャネルの処理ルール - 定義
topic: Reports and analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
   <td colname="col2"> <p>Advertising Cloud と Advertising Analytics の統合で使用されるプライマリトラッキングコード。これらの統合の 1 つが有効になっている場合、トラッキングコードプレフィックスを使用して Advertising Cloud 固有のチャネルを識別できます。「AMO ID」は、検索には「AL」、表示には「AC」、Social には「AO」で始まる名前を使用します。AMO ID をマーケティングチャネルで使用する場合、クリック／コスト／インプレッション指標を正しいチャネルに関連付けることができます（設定されていない場合、これらの指標は「直接」または「なし」になります）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>Advertising Cloud で使用されるセカンダリトラッキングコード。このトラッキングコードは、Ad Cloud にデータを返送する際の鍵となることを主な目的としています。ただし、2 つの異なるマーケティングチャネルとして表示したい場合は、表示クリックスルー数と表示ビュースルー数を識別するためにも使用できます。これは、「表示クリックスルー」の場合は「AMO EF ID」のマーケティングチャネルロジックを「:d」で終わるように設定し、「表示ビュースルー」の場合は「:i」で終わるように設定することで実現できます。「表示」を 2 つのチャネルに分割しない場合は、代わりに AMO ID ディメンションを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンバージョン変数 </p> </td> 
   <td colname="col2"> <p>このレポートスイート用に有効になっている eVar から構成され、これらの変数がページ上の Adobe コード経由で設定された場合にのみ適用されます。 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf"  >実装マニュアル</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>存在する </p> </td> 
   <td colname="col2"> <p>以下のオプションを選択できます。 </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">が存在しない</span>：ヒット属性がリクエストに存在しないことを示します。たとえば、参照ドメインで、ユーザーが URL を入力するかブックマークをクリックすると、その参照ドメイン属性は存在しません。 </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol">が空である</span>：ヒット属性（通常は eVar またはクエリ文字列パラメーター）は存在しますが、そのヒット属性に関連付けられた値がないことを示します。 </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol">次を含まない</span>：例えば参照ドメインに特定の値を含めないよう指定できます（「<span class="term">次を含む</span>」を選択する場合と逆）。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネルを %s として特定している </p> </td> 
   <td colname="col2"> <p><span class="wintitle">マーケティングチャネルマネージャー</span>ページに追加したマーケティングチャネルにルールを関連付けます。 </p> <p><a href="/help/components/c-marketing-channels/c-channels.md"   >マーケティングチャネルの追加</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>有料検索の検出ルールに一致 </p> </td> 
   <td colname="col2"> <p>アドビによって検出された有料検索。有料検索とは、自社サイトが検索結果リストに優先的に載せられるように会社が検索エンジンに料金を支払った検索キーワードを指します。有料検索のキーワードは通常検索結果の上部または右側に表示されます。 </p> </td> 
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
   <td colname="col2"> <p>管理ツールにあるレポートスイートで定義されたとおり、参照 URL が内部 URL フィルターに一致しません。この設定を「<span class="term">ページの URL</span>」および「<span class="term">存在する</span>」と共に使用して包括的ルールを設定できるので、訪問のランディングページがレポートの「<a href="/help/components/c-marketing-channels/c-faq.md#no-channel-identified" >チャネルが識別されませんでした</a>」セクションになることはありません。 </p> </td> 
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
   <td colname="col2"> <p>アドビの Web ビーコンを使ってタグ付けされた、サイト上の Web ページのページ名。<span class="varname"> s.pageName </span> と等しい値になります。例としては、<span class="varname">ホームページ</span>や<span class="varname">会社概要</span>などがあります。 </p> </td> 
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
   <td colname="col2"> <p>サイトのページ URL が <span class="filepath">https://example.com/?page=12345&amp;cat=1</span> であれば、page と cat は共にクエリ文字列パラメーターになります（<span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span> を参照してください。） </p> <p>１ つのルールセットにつき 1 つだけクエリ文字列パラメーターを指定できます。クエリ文字列パラメーターをさらに追加するには、「<span class="uicontrol">いずれか</span>」演算子を使用して、ルールに新しいクエリ文字列パラメーターを追加します。 </p> </td> 
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
    </code> <p><b>注意：</b>n = natural（自然検索）、p = paid（有料検索） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>チャネルの値を次の値に設定する </p> </td> 
   <td colname="col2"> <p>訪問者をサイトに導くマーケティングチャネルを特定することに加えて、訪問者のサイトのアクティビティに対してクレジットを受けるチャネル内のバナー広告、検索キーワードまたは電子メールキャンペーンを特定できます。この ID は、チャネルと共に保存されるチャネル値です。この値には、ランディングページや参照 URL に埋め込まれているキャンペーン ID、検索エンジンと検索キーワードの組み合わせ、特定チャネルからの訪問者と最も正確に識別する参照 URL などがよく使用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
