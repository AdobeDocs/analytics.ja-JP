---
description: 変数とその制限に関する概要です。
keywords: Analyticsの導入;変数、制限事項;limit
seo-description: 変数とその制限に関する概要です。
seo-title: 変数と制限
solution: Analytics
subtopic: 変数
title: 変数と制限
topic: 開発者と導入
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 変数と制限

変数とその制限に関する概要です。

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

次の表に、[!DNL Analytics] 変数に関する概要情報を示します。

| 変数 | 説明 |
|---|---|
| s_account | データの保存とレポートをおこなうレポートスイートを決定します。 |
| browserHeight | ブラウザーウィンドウの高さを自動取得します。 |
| browserWidth | ブラウザーウィンドウの幅を自動取得します。 |
| campaign | 訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別します。次の値の&#x200B;*`campaign`* の値はクエリ文字列パラメーターから取得します。 |
| channel | 通常、Web サイトのセクションを特定します。例えば、EC サイトなら、エレクトロニクス、玩具、アパレルなどのセクションが考えられます。メディアサイトなら、ニュース、スポーツ、ビジネスなどのセクションが考えられます。 |
| charSet | Web ページの文字セットを設定します。UTF-8 に変換されます。 |
| colorDepth | 画面の各ピクセルに色を表示するのに使用されるビット数を自動取得します。 |
| connectionType | （Internet Explorer における）ブラウザーの接続設定（LAN 接続またはモデム接続）を自動取得します。 |
| cookieDomainPeriods | ページ URL のドメインに含まれるピリオドの数を指定することによって、[!DNL Analytics][!UICONTROL  訪問者 ID]の（s_vi）cookie が設定されるドメインを決定します。For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | cookie の有効期限を決定するために、JavaScript と [!DNL Analytics] サーバーの両方で使用されます。 |
| cookiesEnabled | ファーストパーティセッション cookie が JavaScript によって設定できたかどうかを自動取得します。 |
| currencyCode | [!DNL Analytics] サーバーに収集されるときに売上高に適用される変換レートを決定するため、通貨を指定します。[!DNL Analytics] サーバーには、すべての金額が選択した通貨で格納されます。If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc |  変数は、データの送信先のデータセンターを設定するために使用します。 |
| doPlugins | *`doPlugins`* は *`s_doPlugins`* 、関数への参照です。It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| dynamicAccountList | データの送信先となるレポートスイートを動的に選択します。"*`dynamicAccountList`* 変数には、目的のレポートスイートを決定するために使用されるルールが含まれます。 |
| dynamicAccountMatch | DOM オブジェクトを使用して、*`dynamicAccountList`* のすべてのルールが適用される URL のセクションを取得します。This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| dynamicAccountSelection | 各ページの URL に基づいてレポートスイートを動的に選択できます。 |
| dynamicVariablePrefix | 動的に設定する必要のある変数にフラグを付けることができます。動的に設定できるものには、cookie、リクエストのヘッダーおよびイメージクエリ文字列パラメーターがあります。 |
| eVarN | [!DNL Analytics][!UICONTROL  コンバージョンモジュール]内でカスタムレポートを作成するために使用されます。eVar を 1 人の訪問者に設定すると、[!DNL Analytics] ではその値が期限切れになるまで記憶されます。eVar 値がアクティブな期間内に訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。 |
| events | 買い物かご関連の各種成功イベントおよびカスタム成功イベントを記録します。 |
| fpCookieDomainPeriods | ページのドメインに含まれるピリオドの数を指定することによって、[!DNL Analytics]訪問者 ID[!UICONTROL （s_vi）cookie 以外の ] cookie が設定されるドメインを決定します。 |
| hierN | サイトの階層におけるページの位置を計測します。この変数は、サイト構造に 4 つ以上のレベルを持つサイトの場合に最も有効です。 |
| homepage | （Internet Explorer において）現在のページがユーザーのホームページとして設定されているかを自動取得します。 |
| javaEnabled | Java がブラウザーで有効になっているかどうかを自動取得します。 |
| javascriptVersion | ブラウザーでサポートされている JavaScript のバージョンを自動取得します。 |
| linkDownloadFileTypes | ファイル拡張子のコンマ区切りリスト。サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。 |
| linkExternalFilters  | サイトに外部サイトへのリンクが多数含まれており、一部の離脱リンクは追跡する必要がない場合、*`linkExternalFilters`*&#x200B;を使用すると、計測する離脱リンクを絞り込むことができます。 |
| linkInternalFilters | サイトのどのリンクが離脱リンクかを決定します。これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。 |
| linkLeaveQueryString | クエリ文字列を[!UICONTROL 離脱リンク]と[!UICONTROL ファイルのダウンロード数]レポートに含めるかどうかを決定します。 |
| linkName | [!UICONTROL リンクトラッキング]に使用されるオプションの変数で、カスタム、ダウンロードまたは離脱リンクの名前を決定します。"*`linkName`* 変数は、 *`tl()`* 関数内の3番目のパラメーターに置き換えられるので、通常は必要ありません。 |
| linkTrackEvents | カスタム、ダウンロードおよび離脱リンクと共に送信する必要があるイベントを含みます。この変数は *`linkTrackVars`* に「events」が含まれている場合にのみ考慮されます。 |
| linkTrackVars | カスタムリンク、離脱リンク、ダウンロードリンクの計測時に設定される、変数のコンマ区切りリストです。*`linkTrackVars`* を"に設定すると、値を持つすべての変数がリンクデータと共に送信されます。 |
| linkType | リンクトラッキングで使用されるオプションの変数で、リンク名や URL が表示されるレポート（カスタムリンク、ダウンロードリンクまたは離脱リンク）を決定します。*`linkType`* は、 *`tl()`* 関数内の2番目のパラメーターに置き換えられるので、通常は必要ありません。 |
| mediaLength | 再生されるメディアの合計の長さを指定します。 |
| mediaName | ビデオまたはメディアの名前を指定します。この変数は、[!UICONTROL Data Insertion API] と[!UICONTROL フル処理のデータソース]を介してのみ使用できます。 |
| mediaPlayer | ビデオまたはメディアを使用するプレイヤーを指定します。 |
| mediaSession | 使用されるビデオまたはメディアアセットのセグメントを指定します。 |
| Media.trackEvents | どのイベントがメディアヒットと共に送信されるかを示します。JavaScript [!UICONTROL ActionSource] でのみ適用できます。 |
| Media.trackVars | どの変数がメディアヒットと共に送信されるかを示します。JavaScript [!UICONTROL ActionSource] でのみ適用できます。 |
| mobile | 訪問者の識別に使用される cookie と 加入者 ID の順序を制御します。 |
| s_objectID | リンクの [!UICONTROL onClick] イベントに設定する必要があるグローバル変数です。リンクまたはページのリンクの場所に対して一意のオブジェクト ID を作成することによって、訪問者クリックマップのトラッキングを向上したり、訪問者クリックマップを使用して、リンク URL ではなく、リンクタイプやリンクの場所でレポートします。 |
| pageName | サイトの各ページの名前を設定します。*`pageName`* が空白の場合、ページ名を表すためにURLが使用 [!DNL Analytics]されます。 |
| pageType | 404（ページが見つかりません）エラーページを計測する目的でのみ使用します。指定可能な値は「errorPage」のみです。404 エラーページには、*`pageName`*&#x200B;変数を入力しないでください。 |
| pageURL | まれに、ページの URL が [!DNL Analytics] でレポートしたい URL ではないことがあります。To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| plugins | Netscape および Mozilla ベースのブラウザーで、ブラウザーにインストールされているプラグインが自動検出されます。 |
| products | 製品と製品カテゴリ、および購入数量と購入価格を追跡するために使用します。"*`products`* 変数は、必ず成功イベントと組み合わせて設定する必要があります。Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | [!DNL Analytics][!UICONTROL  トラフィックモジュール]内でカスタムレポートを作成するために使用します。[!UICONTROL prop] は、パスレポートやクロス集計レポートで、（ページビューが送信された回数をカウントするために）カウンターとして使用することができます。 |
| purchaseID | [!DNL Analytics] で 1 つの注文が複数回カウントされないようにするために使用します。Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | リファラー情報がリダイレクトなどによって消去される場合に、リファラーを明示的に指定するために使用します。 |
| resolution | Web ページを表示する訪問者の画面の解像度を自動取得します。 |
| server | Web ページのドメイン（ユーザーがアクセスするドメインを表示）またはページを提供するサーバー（ロードバランシングのクイック参照用）を設定します。 |
| state | サイトへの訪問者の居住地の都道府県を設定します。 |
| trackDownloadLinks | サイトの&#x200B;*`trackDownloadLinks`* を"true"に設定します。*`trackDownloadLinks`* が"true"の場合、どのリンクがダウンロード可能ファイルかを *`linkDownloadFileTypes`* 判断します。 |
| trackExternalLinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | イメージリクエストが送信されるサーバーのドメインを指定します。セキュリティ保護されていないページで使用されます。 |
| trackingServerSecure | イメージリクエストが送信されるサーバーのドメインを指定します。セキュリティ保護されているページで使用されます。 |
| trackInlineStats | 訪問者クリックマップ用のデータを収集するかどうかを指定します。 |
| transactionID | オフラインデータをオンライントランザクション（オンラインで生成されたリードや購入など）に関連付けるためのキーとしての ID を指定します。一意の *`transactionID`* をイメージリクエストの一部として送信しておくことで、トランザクションに関するオフライン情報の[!UICONTROL データソース]を後日アップロードした際にオンラインデータとの紐付けが可能になります。[データソースガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)を参照してください。 |
| s_usePlugins | 該当する&#x200B;*`s_doPlugins`* 関数が使用可能で、有効なコードが含まれている場合、 [!UICONTROL s_ usePlugins] を"true"に設定する必要があります。[!UICONTROL usePlugins] が"true"の場合、 *`s_doPlugins`* 各イメージリクエストの前に関数が呼び出されます。 |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. *`visitorID`* 英数字は最大100文字で、ハイフンを含めることはできません。 |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. この変数は、cookie が設定されているドメインを識別するために使用されます。If *`visitorNamespace`* を変更すると、[!DNL Analytics] でレポートされるすべての訪問者が新規訪問者となる場合があります。したがって、アドビコンサルタントの許可がない場合は、この変数を変更しないでください。 |
| zip | サイトへの訪問者の居住地の郵便番号をセットします。 |

