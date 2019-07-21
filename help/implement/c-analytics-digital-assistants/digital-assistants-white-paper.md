---
description: 'null'
seo-description: 'null'
seo-title: デジタルアシスタント用のAnalyticsの実装
title: デジタルアシスタント用のAnalyticsの実装
uuid: c61e6a1a- ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# デジタルアシスタント用のAnalyticsの実装

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

昨今のクラウドコンピューティング、機械学習および自然言語処理の発展により、デジタルアシスタントは、「Clippy」に象徴されるような暗黒時代から抜け出し、私たちの日常の一部になっています。消費者が「Alexa、リビングの電気を点けて」、「オーケー Google、今日の天気はどう」といった言葉でデバイスに語りかけると、デバイスはそれを聞いて理解し、人間のように自然に返答してくれます。

こうしたプラットフォームが普及したことで、ブランドは、これと同様の生身の人間のような応対でサービスを消費者に提示できるようになりました。例えば消費者は、次のような質問を投げかけることができます。

* 「Alexa、車のオイル交換が必要な時期を調べて」
* 「Cortana、当座預金口座の残高は？」
* 「Siri、昨夜のディナー代として、ジョンにバンキングアプリから 20 ドル送金して」

このホワイトペーパーでは、Adobe Analytics Cloud を活用して、この種のエクスペリエンスの効果を測定および最適化する方法について説明します。

## デジタルエクスペリエンスのアーキテクチャの概要 {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

現代のデジタルアシスタントのほとんどでは、大まかなアーキテクチャは同様です。

1. **デバイス：**&#x200B;マイク搭載のデバイス（Amazon Echo や携帯電話）によって、ユーザーが質問を投げかけることができます。
1. **デジタルアシスタント：**&#x200B;そのデバイスが、デジタルアシスタントの基盤のサービスと通信します。このサービスで様々な処理がおこなわれます。音声が機械で認識できる目的に変換され、要求の詳細が解析されます。ユーザーの目的が認識されたら、デジタルアシスタントがその目的と要求の詳細をアプリに渡し、アプリがその要求を処理します。
1. **「アプリ」：**&#x200B;携帯電話のアプリまたは音声アプリです。このアプリが要求に対処し、デジタルアシスタントに返答してから、デジタルアシスタントがユーザーに答えを伝えます。

## Analytics を導入する場所 {#concept_F53A0566589042658DEA5B86B22C10CB}

Analytics を導入する場所として特に効果的なのはアプリです。アプリは、ユーザーの[目的](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A)とその詳細をデジタルアシスタントから受け取り、対処方法を導き出します。

要求が処理されるプロセスの中には、Analytics Cloud の呼び出しが効果的なタイミングが 2 つあります。

1. 「アプリ」に要求が送信されたとき：要求に応答する前に、ユーザーについての追加のコンテキストデータが必要な場合は、Audience Manager の機能を活用して、ユーザーが属するセグメントの情報を取得することをお勧めします。
1. アプリから応答が送られたとき。今後の最適化のために、顧客の状況についての記録のみが必要な場合は、応答が返された後に Adobe Analytics に要求を送信します。これにより、どのような要求があり、システムがどのように返答したのかについての詳細なコンテキストを取得できます。

## 新規インストール {#section_FD63267479DB47C2A081244A3E65A0CC}

一部のデジタルアシスタントでは、ユーザーがスキルをインストールしたときに通知が届きます。特に認証が関係するケースがこれに該当します。このときにアドビに&#x200B;*`Install`*&#x200B;イベントを送信することをお勧めします（コンテキストデータを `a.InstallEvent=1` に設定します）。この方法は、利用できないプラットフォームもありますが、可能な場合はリテンションを確認するのに便利です。次のコードのサンプルでは、*`Install`*、 *`Install Date`*&#x200B;および *`AppID`*、

**コードサンプル**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## 複数のアシスタントまたは複数のアプリ {#section_81740741752E4142BE42DA4C9DDEEDF5}

複数のプラットフォーム用のアプリを開発することもよくあります。各要求にアプリ ID を含めることをお勧めします。これは `a.AppID` のコンテキストデータで設定できます。Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**コードサンプル**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## ユーザー／訪問者の識別 {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. ほとんどのケースでは、この値は ECID サービスとして渡す必要があります。一部のプラットフォームは、Analytics の上限である 100 文字を超える *`userID`*&#x200B;を返します。If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

そのために ECID サービスを使用できますが、ECID サービスを使用すると、異なるデバイス間で ECID をマッピングする場合（Web からデジタルアシスタントなど）のみ値が提供されます。アプリがモバイルアプリの場合（ディープリンクなど）は、SDK をそのまま使用して情報を送信します。"*`userID`*&#x200B;は、setCustomerID メソッドを使用して ECID サービスに関連付け、デバイスのスティッチングを改善できます。However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. これにより、デジタルアシスタントの使用状況の推移を確認できます。

**コードサンプル**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## セッション数 {#section_BA4F996F976043B8993F2F7D24FE27FB}

デジタルアシスタントは会話型なので、多くの場合はセッションの概念が採り入れられています。次に例を示します。

**消費者：**「オーケー Google、タクシーを呼んで」

**Google：**:「わかりました。何時に来てもらいますか？」

**消費者：** 「午後 8 時半」

**Google：**「了解しました。午後 8 時半までに運転手が到着します」

こうしたセッションは、コンテキストから逸脱しないために大事な要素であり、より詳細な情報を収集し、デジタルアシスタントの対応を円滑化するのに役立ちます。

会話に Analytics を導入する場合は、新規セッションを開始する際にやるべきことが 2 つあります。

1. **Audience Manager にアクセスする：**&#x200B;返答をカスタマイズするために、ユーザーが属する適切なセグメントを取得します（このユーザーは現在、マルチチャネルの割り引きの利用条件を満たしているなど）。
1. **新規セッションまたは開始イベントを送信する：**&#x200B;最初の応答を Analytics に送信する際に、開始イベントを含めます。一般的には、`a.LaunchEvent=1` のコンテキストデータを設定することで、このイベントを送信できます。

**コードサンプル[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 目的 {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

デジタルアシスタントには、目的を検知してから、対処方法を導き出すためにその目的を「アプリ」に渡すためのアルゴリズムがあります。こうした目的は、要求を簡潔に表現するもので、

例えばユーザーが「Siri、昨夜のディナー代として、ジョンにバンキングアプリから 20 ドル送金して」と言った場合は、その目的は *`sendMoney`*（名前をつけて保存）する必要があります。

これらの各要求を eVar として送信することで、会話アプリの各目的に関するパスレポートを作成できます。「アプリ」が目的なしでも要求を処理できるよう設定することもできます。その場合は値を空白にするのではなく、*`No Intent Specified`*&#x200B;を渡すことをお勧めします。

**コードサンプル**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

 または

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## パラメーター／スロット／エンティティ {#section_041CD1730F9E4096BE75DFF2CC810852}

デジタルアシスタントは多くの場合、目的だけでなく、目的の詳細を示すキーと値のペアのセットも保持します。これらはスロット、エンティティまたはパラメーターと呼ばれます。次に例を示します。

「Siri、昨夜のディナー代として、ジョンにバンキングアプリから 20 ドル送金して」のパラメーターは次のようになります。

* 誰 = ジョン
* 金額 = 20
* 理由 = ディナー

アプリのこうしたパラメーターの数には、限りがあるのが一般的です。Analytics でこうしたパラメーターを追跡するためには、コンテキストデータに送信してから、各パラメーターを eVar にマッピングします。

**コードサンプル**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## セッション {#section_17D69D6B298E46E88E175F62F1ACD831}

収益を生み出すことが目的ではないアプリもありますが、どのような状況になったら成功と見なせるのかを考え、そのための測定指標を含めることが大事です。Adobe Analytics では、ユーザー行動とともに、収益、広告インプレッション数などの形式の成果を測定できます。

## エラー状態 {#section_E8EFF8D610B24DC899C34E50B058864D}

デジタルアシスタントが、対処方法がわからない入力情報をアプリに送ることもあります。次に例を示します。

「Siri、昨夜のディナー代として、ジョンにバンキングアプリから石炭 20 袋を送っておいて」

このようなケースでは、アプリは確認を求める必要があります。また、このような要求に応答する際は、アプリがエラー状態になっていることを示すイベントと、発生したエラーのタイプを指定する evar を Analytics に送信する必要があります。

入力情報に間違いがある場合のエラーと、「アプリ」に問題が生じた場合のエラーを必ず含めます。

**コードサンプル**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## デバイスの機能 {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

ほとんどのプラットフォームは、ユーザーが話しかけた実際のデバイスの情報は渡しませんが、利用可能なインターフェイスとしてデバイスの機能の情報を渡します（Audio、Screen、Video など）。この情報は、ユーザーとの対話の中で使用できるコンテンツのタイプを定義するので有用です。インターフェイスを測定する際は、それらをアルファベット順で連結する方法が最も効果的です。

例: `:Audio:Camera:Screen:Video:`

先頭と末尾のコロンに注意してください。These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Amazon の機能：[https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Google の機能：[https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## デジタルアシスタント向け Analytics レポート {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

デジタルアシスタントアプリを導入したら、Adobe Analytics を有効活用できます。Analytics の活用方法の主な例は次のとおりです。

## 目的の監視 {#section_6632D9F2EF9045A7A1A4263D3561C78F}

ほとんどのアプリには複数の目的があり、複数の用途があります。You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

これにより、最も使用頻度が高い機能や、新機能の導入状況を把握できます。

## エラーが発生した要求 {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

エラーを監視し、問題が頻繁に発生する場所がないか確認できます。

<!-- 

<p>--- Image of Errors --- </p>

 -->

## イベント間のフロー {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

特に強力な機能の 1 つは、目的の変遷を分析できることです。これは 2 つの点で便利です。1 点目は、特定のセッション内で、会話の中でのユーザーの目的の変遷を分析できることです。2 点目は、より長い期間でユーザーの目的の変遷を分析し、「アプリ」の利用方法がどのように変わっているのかを把握できることです。

## 例 {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**インストール済みのアプリ**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユーザー </th> 
   <th colname="col2" class="entry"> デバイスの応答 </th> 
   <th colname="col3" class="entry"> アクション／目的 </th> 
   <th colname="col4" class="entry"> GET 要求 </th> 
   <th colname="col5" class="entry"> Analytics データ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Spoofify を起動して </p> </td> 
   <td colname="col2"> <p> 「了解、Spoofify を起動します」 </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. a. LaunchEvent=1&amp; c. intent= Play&amp; pageName= playApp HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">訪問者 ID </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">アプリのバージョン </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">起動回数 </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">目的 </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 楽曲を変更して </p> </td> 
   <td colname="col2"> <p> 「了解、どの楽曲にしますか？」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changeOnSong&amp; pageName= ASForSong HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">訪問者 ID </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">アプリのバージョン </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">目的 </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">* 空の再生リスト </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> セリーヌディオンの「My Heart Will Go On」を再生して </p> </td> 
   <td colname="col2"> <p> 「了解、セリーヌディオンの「My Heart Will Go On」を再生します」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= ActionPlaysong&amp; c. SoninId=[012345] HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">訪問者 ID </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">アプリのバージョン </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">目的 </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">楽曲 ID </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 再生リストを変更して </p> </td> 
   <td colname="col2"> <p> 「了解、どの再生リストにしますか？」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= askForPlaylist HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">訪問者 ID </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">アプリのバージョン </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">目的 </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">* 空の再生リスト </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Usher を再生して </p> </td> 
   <td colname="col2"> <p> 「了解、Usher を再生します」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= ActionPlayPlaylist&amp; c.プレイリスト= Usher HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">訪問者 ID </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">アプリのバージョン </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">目的 </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">再生リスト </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 音楽を切って </p> </td> 
   <td colname="col2"> <p> * 応答なし、音楽がオフ </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= Off&amp; pageName= turnOFFMusic HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">訪問者 ID </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">アプリのバージョン </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">目的 </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">応答 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**ユーザーがアプリをインストールする必要がある**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ユーザー </th> 
   <th colname="col2" class="entry"> デバイスの応答 </th> 
   <th colname="col3" class="entry"> アクション／目的 </th> 
   <th colname="col4" class="entry"> GET 要求 </th> 
   <th colname="col5" class="entry"> Analytics データ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Spoofify をインストールして </p> </td> 
   <td colname="col2"> <p> * 応答なし </p> </td> 
   <td colname="col3"> <p> Install </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[userId]&amp; amp;amp;c. a. instalEvent=1&amp; c. a. InstallDate=2017-04-24&amp; c. a. AppID= Spofify1.0&amp; c. autoType= Alexa&amp; c. intent= Install&amp; pageName= install HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">訪問者 ID </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">日付 </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">目的 </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">OS バージョン </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Spoofify を起動して </p> </td> 
   <td colname="col2"> <p> 「了解、Spoofify を起動します」 </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. a. LaunchEvent=1&amp; c. intent= Play&amp; pageName= playApp HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">訪問者 ID </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">アプリのバージョン </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">起動回数 </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">目的 </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 楽曲を変更して </p> </td> 
   <td colname="col2"> <p> 「了解、どの楽曲にしますか？」 </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changeOnSong&amp; pageName= ASForSong HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">訪問者 ID </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">アプリのバージョン </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">目的 </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">* 空の再生リスト </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> セリーヌディオンの「My Heart Will Go On」を再生して </p> </td> 
   <td colname="col2"> <p> 「了解、セリーヌディオンの「My Heart Will Go On」を再生します」 </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= ActionPlaysong&amp; c. SoninId=[012345] HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">訪問者 ID </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">アプリのバージョン </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">目的 </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">楽曲 ID </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 再生リストを変更して </p> </td> 
   <td colname="col2"> <p> 「了解、どの再生リストにしますか？」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= askForPlaylist HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">訪問者 ID </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">アプリのバージョン </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">目的 </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">* 空の再生リスト </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Usher を再生して </p> </td> 
   <td colname="col2"> <p> 「了解、Usher を再生します」 </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= changePlaylist&amp; pageName= ActionPlayPlaylist&amp; c.プレイリスト= Usher HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">訪問者 ID </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">アプリのバージョン </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">目的 </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">再生リスト </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">応答 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 音楽を切って </p> </td> 
   <td colname="col2"> <p> * 応答なし、音楽がオフ </p> </td> 
   <td colname="col3"> <p> Off </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0?vid=[UserId]&amp; c. a. AppID= Spofify1.0&amp; c. intent= Off&amp; pageName= turnOFFMusic HTTP/1.1
ホスト:sc. omtrdc. net
Cache- Control:キャッシュなし </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">訪問者 ID </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">アプリのバージョン </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">目的 </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">応答 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

