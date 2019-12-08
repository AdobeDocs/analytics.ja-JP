---
description: 変数とその制限に関する概要です。
keywords: Analytics Implementation;variable;limitations;limits
subtopic: Variables
title: 変数と制限
topic: Developer and implementation
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 変数と制限

変数とその制限に関する概要です。

>[!NOTE]
>
>最も一般的な Analytics 変数について詳しくは、「[設定変数](/help/implement/js-implementation/c-variables/configuration-variables.md)」および「[ページ変数](/help/implement/js-implementation/page-variables/page-variables.md)」を参照してください。

次の表に、[!DNL Analytics] 変数に関する概要情報を示します。

| 変数 | 説明 |
|---|---|
| s_account | データの保存とレポートをおこなうレポートスイートを決定します。 |
| browserHeight | ブラウザーウィンドウの高さを自動取得します。 |
| browserWidth | ブラウザーウィンドウの幅を自動取得します。 |
| campaign | 訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別します。の値&#x200B;*`campaign`* の値はクエリ文字列パラメーターから取得します。 |
| channel | 通常、Web サイトのセクションを特定します。例えば、EC サイトなら、エレクトロニクス、玩具、アパレルなどのセクションが考えられます。メディアサイトなら、ニュース、スポーツ、ビジネスなどのセクションが考えられます。 |
| charSet | Web ページの文字セットを設定します。UTF-8 に変換されます。 |
| colorDepth | 画面の各ピクセルに色を表示するのに使用されるビット数を自動取得します。 |
| connectionType | （Internet Explorer における）ブラウザーの接続設定（LAN 接続またはモデム接続）を自動取得します。 |
| cookieDomainPeriods | ページ URL のドメインに含まれるピリオドの数を指定することによって、[!DNL Analytics][!UICONTROL  訪問者 ID]の（s_vi）cookie が設定されるドメインを決定します。`www.mysite.com` の場合、*`cookieDomainPeriods`* は「2」にする必要があります。`www.mysite.co.jp` の場合、*`cookieDomainPeriods`* は「3」にする必要があります。 |
| cookieLifetime | cookie の有効期限を決定するために、JavaScript と [!DNL Analytics] サーバーの両方で使用されます。 |
| cookiesEnabled | ファーストパーティセッション cookie が JavaScript によって設定できたかどうかを自動取得します。 |
| currencyCode | [!DNL Analytics] サーバーに収集されるときに売上高に適用される変換レートを決定するため、通貨を指定します。[!DNL Analytics] サーバーには、すべての金額が選択した通貨で格納されます。その通貨が *`currencyCode`* で指定したものと同じ場合、または *`currencyCode`* が空の場合、コンバージョンは適用されません。 |
| dc |  変数は、データの送信先のデータセンターを設定するために使用します。 |
| doPlugins | *`doPlugins`* は、*`s_doPlugins`* 関数の参照です。これにより、JavaScript ファイル内の適切な場所で *`s_doPlugins`* 関数を呼び出すことができます。 |
| dynamicAccountList | データの送信先となるレポートスイートを動的に選択します。Folio Builder *`dynamicAccountList`* 変数には、目的のレポートスイートを決定するために使用されるルールが含まれます。 |
| dynamicAccountMatch | DOM オブジェクトを使用して、*`dynamicAccountList`* のすべてのルールが適用される URL のセクションを取得します。この変数は、*`dynamicAccountSelection`* が「True」に設定されているときのみ有効です。 |
| dynamicAccountSelection | 各ページの URL に基づいてレポートスイートを動的に選択できます。 |
| dynamicVariablePrefix | 動的に設定する必要のある変数にフラグを付けることができます。動的に設定できるものには、cookie、リクエストのヘッダーおよびイメージクエリ文字列パラメーターがあります。 |
| eVarN | [!DNL Analytics][!UICONTROL  コンバージョンモジュール]内でカスタムレポートを作成するために使用されます。eVar を 1 人の訪問者に設定すると、[!DNL Analytics] ではその値が期限切れになるまで記憶されます。eVar 値がアクティブなときに訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。 |
| events | 買い物かご関連の各種成功イベントおよびカスタム成功イベントを記録します。 |
| fpCookieDomainPeriods | ページのドメインに含まれるピリオドの数を指定することによって、[!DNL Analytics]訪問者 ID[!UICONTROL （s_vi）cookie 以外の ] cookie が設定されるドメインを決定します。 |
| hierN | サイトの階層におけるページの位置を決定します。この変数は、サイト構造に 3 つ以上のレベルを持つサイトの場合に最も有効です。 |
| homepage | （Internet Explorer において）現在のページがユーザーのホームページとして設定されているかを自動取得します。 |
| javaEnabled | Java がブラウザーで有効になっているかどうかを自動取得します。 |
| javascriptVersion | ブラウザーでサポートされている JavaScript のバージョンを自動取得します。 |
| linkDownloadFileTypes | ファイル拡張子のコンマ区切りリスト。サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。 |
| linkExternalFilters  | サイトに外部サイトへのリンクが多数含まれており、一部の離脱リンクは追跡する必要がない場合、*`linkExternalFilters`*&#x200B;を使用すると、計測する離脱リンクを絞り込むことができます。 |
| linkInternalFilters | サイトのどのリンクが離脱リンクかを決定します。これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。 |
| linkLeaveQueryString | クエリ文字列を[!UICONTROL 離脱リンク]と[!UICONTROL ファイルのダウンロード数]レポートに含めるかどうかを決定します。 |
| linkName | [!UICONTROL リンクトラッキング]に使用されるオプションの変数で、カスタム、ダウンロードまたは離脱リンクの名前を決定します。*`linkName`* 変数は、*`tl()`* 関数の 3 番目のパラメーターで置き換えられるので、通常は必要ありません。 |
| linkTrackEvents | カスタム、ダウンロードおよび離脱リンクと共に送信する必要があるイベントを含みます。この変数は、*`linkTrackVars`* に「events」が含まれる場合にのみ考慮されます。 |
| linkTrackVars | カスタムリンク、離脱リンク、ダウンロードリンクの計測時に設定される、変数のコンマ区切りリストです。*`linkTrackVars`*&#x200B;が "" に設定されている場合、値を持つすべての変数がリンクデータと共に送信されます。 |
| linkType | リンクトラッキングで使用されるオプションの変数で、リンク名や URL が表示されるレポート（カスタムリンク、ダウンロードリンクまたは離脱リンク）を決定します。*`linkType`*&#x200B;は、*`tl()`* 関数の 2 番目のパラメーターで置き換えられるので、通常は必要ありません。 |
| mediaLength | 再生されるメディアの合計の長さを指定します。 |
| mediaName | ビデオまたはメディアの名前を指定します。この変数は、[!UICONTROL Data Insertion API] と[!UICONTROL フル処理のデータソース]を介してのみ使用できます。 |
| mediaPlayer | ビデオまたはメディアを使用するプレイヤーを指定します。 |
| mediaSession | 使用されるビデオまたはメディアアセットのセグメントを指定します。 |
| Media.trackEvents | どのイベントがメディアヒットと共に送信されるかを示します。JavaScript [!UICONTROL ActionSource] でのみ適用できます。 |
| Media.trackVars | どの変数がメディアヒットと共に送信されるかを示します。JavaScript [!UICONTROL ActionSource] でのみ適用できます。 |
| mobile | 訪問者の識別に使用される cookie と 加入者 ID の順序を制御します。 |
| s_objectID | リンクの [!UICONTROL onClick] イベントに設定する必要があるグローバル変数です。リンクまたはページのリンクの場所に対して一意のオブジェクト ID を作成することによって、訪問者クリックマップのトラッキングを向上したり、訪問者クリックマップを使用して、リンク URL ではなく、リンクタイプやリンクの場所でレポートします。 |
| pageName | サイトの各ページの名前を設定します。*`pageName`* が空白の場合、[!DNL Analytics] ではページ名を表すために URL が使用されます。 |
| pageType | 404（ページが見つかりません）エラーページを計測する目的でのみ使用します。指定可能な値は「errorPage」のみです。404 エラーページには、*`pageName`*&#x200B;変数を入力しないでください。 |
| pageURL | まれに、ページの URL が [!DNL Analytics] でレポートしたい URL ではないことがあります。これらの状況に対応するために、[!DNL Analytics] では、ページの実際の URL を上書きする *`pageURL`* 変数を提供しています。 |
| plugins | Netscape および Mozilla ベースのブラウザーで、ブラウザーにインストールされているプラグインが自動検出されます。 |
| products | 製品と製品カテゴリ、および購入数量と購入価格を追跡するために使用します。Folio Builder *`products`* 変数は、必ず成功イベントと組み合わせて設定する必要があります。*`products`* 変数では、カスタムの数値イベントや通貨イベントだけでなく、[!UICONTROL マーチャンダイジング] eVar を追跡することもできます。 |
| propN | [!DNL Analytics][!UICONTROL  トラフィックモジュール]内でカスタムレポートを作成するために使用します。[!UICONTROL prop] は、パスレポートやクロス集計レポートで、（ページビューが送信された回数をカウントするために）カウンターとして使用することができます。 |
| purchaseID | [!DNL Analytics] で 1 つの注文が複数回カウントされないようにするために使用します。購入イベントがサイトで使用される場合は必ず *`purchaseID`* 変数を使用する必要があります。 |
| referrer | リファラー情報がリダイレクトなどによって消去される場合に、リファラーを明示的に指定するために使用します。 |
| resolution | Web ページを表示する訪問者の画面の解像度を自動取得します。 |
| server | Web ページのドメイン（ユーザーがアクセスするドメインを表示）またはページを提供するサーバー（ロードバランシングのクイック参照用）を設定します。 |
| state | サイトへの訪問者の居住地の都道府県を設定します。 |
| trackDownloadLinks | サイトのダウンロード可能なファイルへのリンクを追跡したい場合は、*`trackDownloadLinks`* を「true」に設定します。*`trackDownloadLinks`* が「true」の場合は、*`linkDownloadFileTypes`* によって、どのリンクがダウンロード可能ファイルかを判断します。 |
| trackExternalLinks | *`trackExternalLinks`* が「true」の場合、*`linkInternalFilters`* および *`linkExternalFilters`* によって、クリックしたリンクが離脱リンクであるかどうかを判断します。 |
| trackingServer | イメージリクエストが送信されるサーバーのドメインを指定します。セキュリティ保護されていないページで使用されます。 |
| trackingServerSecure | イメージリクエストが送信されるサーバーのドメインを指定します。セキュリティ保護されているページで使用されます。 |
| trackInlineStats | 訪問者クリックマップ用のデータを収集するかどうかを指定します。 |
| transactionID | オフラインデータをオンライントランザクション（オンラインで生成されたリードや購入など）に関連付けるためのキーとしての ID を指定します。一意の *`transactionID`* をイメージリクエストの一部として送信しておくことで、トランザクションに関するオフライン情報の[!UICONTROL データソース]を後日アップロードした際にオンラインデータとの紐付けが可能になります。[データソースガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)を参照してください。 |
| s_usePlugins | *`s_doPlugins`* 関数が利用可能になっていて、有効なコードが含まれている場合は、[!UICONTROL s_usePlugins] を「true」に設定する必要があります。[!UICONTROL usePlugins] が「true」の場合、イメージリクエストの前に *`s_doPlugins`* 関数が呼び出されます。 |
| visitorID | 訪問者は、*`visitorID`* タグ、または IP アドレス／ユーザーエージェントで特定することもできます。*`visitorID`* は最大 100 文字の英数字で指定でき、ハイフンを含めることはできません。 |
| visitorNamespace | *`visitorNamespace`* を JavaScript ファイルで設定している場合は、この変数を削除または変更しないでください。この変数は、cookie が設定されているドメインを識別するために使用されます。*`visitorNamespace`* を変更すると、 でレポートされるすべての訪問者が新規訪問者となる場合があります。[!DNL Analytics]したがって、アドビコンサルタントの許可がない場合は、この変数を変更しないでください。 |
| 郵便番号 | サイトへの訪問者の居住地の郵便番号をセットします。 |

