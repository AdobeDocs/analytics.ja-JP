---
description: アドビでは Cookie を使用して個別のブラウザーおよびデバイスを追跡しています。
keywords: Analytics Implementation
subtopic: Visitors
title: 個別訪問者数の識別
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 個別訪問者数の識別

アドビでは Cookie を使用して個別のブラウザーおよびデバイスを追跡しています。

## Analytics 訪問者 ID の順序 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analyticsには、ユーザーを識別するためのいくつかのメカニズムが用意されている訪問者があります。 次の表に、Analyticsで訪問者を識別する様々な方法（優先順）を示します。

| 使用注文 | クエリパラメータ（収集方法） | 次の場合に存在 |
|---|---|---|
| 1 | vid（s.visitorID） | s.visitorID が設定されている場合 |
| 2 | aid（s_vi Cookie） | 訪問者 ID サービスを展開する前に訪問者が既に s_vi cookie を持っていた、または訪問者 ID 猶予期間が設定済みである。 |
| 3 | mid（Experience Cloud 訪問者 ID サービスによって設定される AMCV_ Cookie） | 訪問者のブラウザーが cookie（ファーストパーティ）を受け入れる場合 |
| 4 | fid（フォールバック cookie） | 訪問者のブラウザーが cookie（ファーストパーティ）を受け入れる場合 |
| 5 | IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス | 訪問者のブラウザーが cookie を受け入れない場合 |

多くの場合、1回の呼び出しで2 ～ 3種類のIDが表示されますが、Analyticsでは、前の表の最初のIDが正式な訪問者IDとして使用されます。 例えば、&#39;vid&#39; クエリパラメーターに格納されるカスタム訪問者 ID を設定している場合は、この ID が、同じヒットで存在する他の ID よりも優先して使用されます。

>[!NOTE]各 Analytics 訪問者 ID は、Adobe サーバー上の訪問者プロファイルに関連付けられます。訪問者プロファイルは、少なくとも 13 ヶ月操作が実行されなかった場合、訪問者 ID cookie の有効期限にかかわらず削除されます。

## カスタム訪問者 ID

s.visitorID 変数を設定して訪問者を識別するためのカスタム方法を実装できます。

カスタム訪問者IDは、ユーザーが独自の方法でユーザーを識別できるサイトで使用できます。訪問者 例えば、ユーザーがユーザー名とパスワードを使用してWebサイトにログインしたときに生成されるIDがこれに該当します。

ユーザーのIDを取得および管理できる [!UICONTROL visitor IDs] 場合は、次の方法を使用してIDを設定できます。

| メソッド | 説明 |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) 変数 | ブラウザーでJavaScriptを使用している場合、または他のAppMeasurementライブラリを使用している場合は、訪問者IDをデータ収集変数に設定できます。 |
| クエリリクエストのイメージ文字列パラメータ | これにより、ハードコードさ [!UICONTROL visitor ID] れたイメージリクエストのパ [!UICONTROL vid query string] ラメーターを介してをアドビに渡すことができます。 |
| Data Insertion API | JavaScript を受け付けないワイヤレスプロトコルを使用するデバイスでは、お使いのサーバーからアドビの収集サーバーに、`<visitorid/>` XML 要素を含む XML ポストを送信できます。 |
| URLの書き直しとVISTA | 一部のデプロイメントアーキテクチャでは、cookieが設定できない場合にセッション状態を維持するためにURLの書き換えを使用するサポートを提供します。 このような場合、アドビのエンジニアリングサービスで [!DNL VISTA] ルールを導入できます。このルールでは、ページの URL 内のセッション値を検索し、整形して、[!UICONTROL visid] の各値に配置します。 |
>[!CAUTION]
>**カスタム訪問者 ID には十分な粒度と一意性が必要&#x200B;**： カスタム訪問者 ID の実装が無効だと、データが不正確になったり、レポートのパフォーマンスが低下する可能性があります。カスタム訪問者 ID が十分な一意性と粒度を備えていない、または共通のデフォルト値（文字列「NULL」や「0」など）に誤って設定されている場合、Adobe Analytics では、多くの異なる訪問者からのヒットが 1 人の訪問者として表示されます。この状況は、データが不正確になる、訪問者のカウントが少なすぎる、その訪問者に対してセグメントが正しく機能しないなどの結果につながります。また、粒度が不十分なカスタム訪問者 ID を使用すると、Analytics レポートクラスターのノード間でデータが分散されなくなります。この場合、1 つのノードが過負荷になり、レポート要求をタイムリーに処理できなくなります。最終的には、そのレポートスイートに関するすべてのレポートが失敗します。<br>Analytics は数ヶ月分の不均衡なデータを処理できることが多いので、カスタム訪問者 ID が適切に実装されていなくても、レポートのパフォーマンスには直ちに影響しない可能性があります。ただし、時間の経過と共に、適切に実装されていないカスタム訪問者 ID の値が問題となり、影響を受けるレポートスイートの処理を Analytics で無効にする必要が生じる可能性があります。</br><br>実装者は、単一のカスタム訪問者 ID 値を、レポートスイートのトラフィックの 1％以上に対して与えないというガイドラインに従う必要があります。ほとんどのレポートスイートでは 1％のガイドラインで十分ですが、非常に大きなレポートスイートでは、レポートのパフォーマンスに影響を与える可能性がある実際の制限が 1％未満となる場合があります。</br>

## Analytics 訪問者 ID

ユーザーがサイトを訪問すると、ブラウザーに対するHTTP応答にcookieを含めることで、アドビのWebサーバーによって永続的なcookieが設定されます。 このcookieは、指定されたデータ収集ドメインに対して設定されます。

リクエストがアドビのデータ収集サーバーに送信されると、ヘッダーで訪問者 ID cookie（`s_vi`）の有無がチェックされます。この Cookie がリクエストに含まれている場合、この Cookie を使用して訪問者が識別されます。cookieがリクエストに含まれていない場合、サーバーは一意の訪問者IDを生成し、HTTP応答ヘッダーにcookieとして設定し、リクエストと共に返送します。 このcookieはブラウザーに保存され、その後のサイト訪問時にデータ収集サーバーに送信されます。これにより、訪問間で訪問者を識別できます。

### サードパーティcookieとCNAMEレコード {#section_61BA46E131004BB2B75929C1E1C93139}

Apple Safari などのブラウザーによっては、現在の Web サイトのドメインと一致しないドメインから HTTP ヘッダーに設定される cookie については保存しないものもあります。例えば、`mysite.com` を表示しているとき、データ収集サーバーが `mysite.omtrdc.net` である場合は、`mysite.omtrdc.net` からの HTTP ヘッダーで返された Cookie はブラウザーによって拒否される可能性があります。

この問題を回避するために、多くのお客様は[ファーストパーティ cookie を導入する](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-first-party.translate.html)中で、データ収集サーバーの CNAME レコードを導入しています。お客様のドメインのホスト名をデータ収集サーバーにマッピングするように CNAME レコードを設定すると（例えば、`metrics.mysite.com` を `mysite.omtrdc.net` にマッピングする）、データ収集ドメインは Web サイトのドメインと一致するので、訪問者 ID cookie が保存されます。これにより、訪問者ID cookieが保存される可能性が高まりますが、CNAMEレコードを設定し、データ収集サーバーのSSL証明書を維持する必要があるので、オーバーヘッドが発生します。

### モバイルデバイスのCookie {#section_7D05AE259E024F73A95C48BD1E419851}

cookie を使用してモバイルデバイスをトラッキングする場合、測定の実施方法を変更するために使用できる設定がいくつかあります。cookie の有効期間はデフォルトで 5 年ですが、CL クエリパラメーター変数（`s.cookieLifetime`）を使用してデフォルト設定を変更できます。CNAME 実装での cookie の場所を設定するには、CDP クエリ文字列 `s.cookieDomainPeriods` を使用します。値を指定しない場合、デフォルトは2です。 デフォルトの場所はdomain.comです。 CNAME を使用しない実装では、訪問者 ID cookie の場所は 207.net ドメインになります。

## ID サービス

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

このサービスに関する製品ドキュメントについては「[ID サービス](https://marketing.adobe.com/resources/help/ja_JP/mcvid/)」を参照してください。

## モバイルデバイスの識別

ほとんどのモバイルデバイスはブラウザーのcookieを受け付けます。 ただし、デバイスがcookieを受け付けない場合は、ワイヤレスデバイスを一意に識別する別の方法が使用されます。

アドビでは、ほとんどのモバイルデバイスを一意に識別する様々な HTTP 加入者 ID ヘッダーを識別しています。これらのヘッダーには、デバイスの電話番号（または番号のハッシュ化されたバージョン）や他の識別子が含まれます。 現在のデバイスの大半には、デバイスを一意に識別する1つ以上のヘッダーがあり、すべてのAdobeデータ収集サーバーでは、訪問者IDの代わりにこれらのヘッダーが自動的に使用されます。

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). ただし、HTTPヘッダに基づいてモバイルデバイスとして認識された場合は、「1」の代わりに「5」が渡され、wbmp形式のイメージが返され、認識されたワイヤレスヘッダのリスト（cookieではない）がデバイスの識別に使用されます。

次の表に、パス内の戻り画像タイプの値（「1」または「5」）に基づいて使用されるIDメソッドの順序をリストします。

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> IDメソッドの順序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>デフォルト: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">カスタム訪問者 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">購読者IDヘッダー </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IPアドレス — ユーザエージェント — ゲートウェイIPアドレス </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>デバイスがワイヤレスデバイスとして識別されました。または、<code> /5/</code> はイメージリクエストに手動で設定されていました。 </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">カスタム訪問者 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">購読者IDヘッダー </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IPアドレス — ユーザーエージェント — ゲートウェイIPアドレス </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

また、手動のイメージリクエストで「1」または「5」を渡すこともできますが、これらのコードは相互に排他的なので、常に「5」を渡してもcookieがサポートされている場合は利用されません。 独自のメカニズムを組み込んで、デバイスがcookieをサポートしているかどうかを判断し、サポートしている場合は、画像内で「5」ではなく「1」を渡すことができます。 この状況で改善される精度は、cookieをサポートするモバイルデバイスの数に制限されます。

### サブスクライバIDヘッダ {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Cookieの削除、Cookieの受け入れの問題、ゲートウェイCookieの管理の問題が原因で、一般に、サブスクライバID方式はCookieよりも信頼性が高く、ユーザーの識別が可能です。

モバイル訪問者が使用する通信事業者のホワイトリストに追加されることで、訪問者の識別の変更を改善できます。 通信業者の訪問者IDにアクセスするには、通信業者に問い合わせて、ドメインをホワイトリストに追加します。 通信業者のホワイトリストを使用している場合は、他の方法ではアクセスできないサブスクライバIDヘッダにもアクセスできます。

次のリストのヘッダーは、ワイヤレスデバイスの識別に使用されます。 ヘッダを処理するアルゴリズムは、

1. HTTPヘッダーキー（「X-Up-Calling-Line-ID」などのヘッダーの名前）を抽出します。
1. アルファベット(A ～ Z、a ～ z)以外の文字をすべて削除する
1. ヘッダーキーを小文字に変換する
1. キーの末尾と次の表の終わりを比較して、一致を見つけます。

| Header | タイプ | 例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID:8613802423312 |
| subno | ID | x-up-subno:swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID:eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid:a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid:595961714786 |
| deviceid | ID | rim-device-id:200522ae |
| forwardedfor | IDまたはIPアドレス | X-Forwarded-For:127.0.0.1 |
| msisdn | IDまたはIPアドレス | X-Wap-msisdn:8032618185 |
| clientip | IP アドレス | Client-ip:10.9.41.2 |
| wapipaddr | IP アドレス | X-WAPIPADDR:10.48.213.162 |
| huaweinasip | IP アドレス | x-huawei-NASIP:211.139.172.70 |
| userip | IP アドレス | UserIP:70.214.81.241 |
| ipaddress | IP アドレス | X-Nokia-ipaddress:212.97.227.125 |
| subscriberinfo | IP アドレス | X-SUBSCRIBER-INFO:IP=10.103.132.128 |

例えば、「callinglineid」は、「X-Up-Calling-Line-ID」および「nokia-callinglineid」と一致します。 ヘッダーのタイプは、ヘッダーの内容を示します。 ヘッダーの優先順位は、ここに示されます（「callinglineid」ヘッダーが存在する場合は、「subno」の代わりに使用されます）。

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## フォールバック ID による方法

訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。

### 代替訪問者識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

JavaScript 1.x 版 AppMeasurement と JavaScript H.25.3（2013 年 1 月リリース）以降のバージョンは、アドビのデータ収集サーバーによって設定される cookie（`s_vi`）をブロックするブラウザーを使用している訪問者を対象とした、新しいフォールバック訪問者の識別方法を備えています。以前は、cookie を設定できない場合、データ収集時に IP アドレスとユーザーエージェント文字列の組み合わせを使用して訪問者を識別していました。

この更新により、標準的な `s_vi` cookie を使用できない場合は、ランダムに生成された一意の ID を使用して、Web サイトでフォールバック cookie が作成されます。この cookie は `s_fid` と呼ばれ、2 年間の有効期限付きで設定され、今後のフォールバック識別方法として使用されます。この変更により、プライマリ cookie（`AMCV_` または `s_vi`）を設定できない状況での、訪問回数と訪問者数の精度が向上します。

訪問総数には、`s_vi` cookie またはフォールバック方法を使用して識別されたすべての訪問者が含まれます。

### IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス {#section_104819D74C594ECE879144FCC5DEF4BF}

 の呼び出しの後におこなわれる場合です。`AMCV_` または `s_vi`、`s_fid` のいずれの cookie も設定できない場合、訪問者は IP アドレスとユーザーエージェントの組み合わせによって識別されます。
