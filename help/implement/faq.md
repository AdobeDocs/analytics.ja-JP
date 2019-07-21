---
description: 導入に関するよくある質問と、詳細情報へのリンクです。
keywords: Analyticsの導入;faq;よくある質問、evar有効期限;カスタムイベントの視認性;timestamp;訪問者ID猶予期間;訪問者ID;Experience Cloud訪問者ID;analytics訪問者ID;dtm;ハートビート;cookie;トラッキングサーバー;パフォーマンス、javascript;データ収集;s_ codeバージョン;s_ code debug;トラッキングリンクタイプ、追跡、ビデオ、trackモバイルアプリ;ファーストパーティcookie;ssl証明書;証明書の有効期限;証明書の有効期限;plugins;data insertion api;500エラー;500;ユーザー管理;管理グループ;users;グループ
seo-description: 導入に関するよくある質問と、詳細情報へのリンクです。
seo-title: Analyticsの導入に関するFAQ
solution: Analytics
title: Analyticsの導入に関するFAQ
topic: 開発者と導入
uuid: 983d759a- c4f2-4021-84c8-0486dbb951b8
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Analyticsの導入に関するFAQ

導入に関するよくある質問と、詳細情報へのリンクです。

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>質問</b> </td> 
   <td> <b>回答</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics のユーザーおよびグループはどのようにして管理しますか。 </p> </td> 
   <td colname="col3"> <p>For information about managing users and groups, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html" format="html" scope="external"> User and Product Management </a> in the Adobe Experience Cloud help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>eVar 有効期限 - レポートで eVars の属性が「なし」になるのはなぜですか。 </p> </td> 
   <td colname="col3"> <p> 「<span class="uicontrol">有効期限</span>」は、eVar 値の有効期限が切れる（成功イベントのクレジットを受け取らなくなる）までの期間またはイベントを指定します。eVar の有効期限が切れた後に成功イベントが発生した場合、「なし」がそのイベントのクレジットを受け取ることになります。つまり、アクティブな eVar がないということを示します。有効期限にイベントを指定した場合、そのイベントが発生した場合にのみ eVar の有効期限が切れます。イベントが発生しない場合、eVar の有効期限は切れません。<a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>カスタムイベントの表示 - レポートメニューにカスタムイベントが表示されないのはなぜですか。 </p> </td> 
   <td colname="col3"> <p>表示列で、メニュー、指標セレクター、計算指標ビルダーおよびセグメントビルダー内の標準（組み込み）指標、カスタムイベントおよび組み込みイベントを非表示にできます。この設定は、ユーザーインターフェイス内での表示にのみ影響し、指標やイベントのデータ収集には影響しません。<a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>タイムスタンプ - タイムスタンプ設定を変更する前に考慮する必要があることは何ですか。 </p> </td> 
   <td colname="col3"> <p>タイムスタンプオプション機能を使用すると、データを損失することなく、タイムスタンプのないデータをタイムスタンプのあるデータと組み合わせることができます。モバイルデバイスで生成されたタイムスタンプのあるオフラインデータは、Web ページからのライブのタイムスタンプのないデータと組み合わせたり、クライアント側のタイムスタンプ呼び出しを使用した任意のプラットフォームからのデータと統合したりできます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪問者 ID - 訪問者 ID 猶予期間はどのように機能し、どうしたら有効にできますか。 </p> </td> 
   <td colname="col3"> <p>同じレポートスイートにデータを送信する複数の JavaScript ファイルがある場合、またはサイト上で Flash ビデオによる測定などの他のテクノロジーを使用している場合は、猶予期間を設定することをお勧めします。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪問者 ID - Experience Cloud 訪問者 ID と Analytics 訪問者 ID の違いは何ですか。 </p> </td> 
   <td colname="col3"> <p>IDサービスは、すべてのサイト訪問者に一意の永続的な識別子を割り当てます。この ID を使用して、訪問者やそのデータを Experience Cloud の他のソリューションで共有できます。また、この ID は、Analytics 訪問者 ID などのソリューション専用の ID を置き換えたり、共に使用したりできます。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪問者 ID - cookie がブロックされている場合、訪問者 ID はどのように設定されますか。 </p> </td> 
   <td colname="col3"> <p>標準的な s_vi cookie を使用できない場合は、ランダムに生成された一意の ID を使用して、Web サイトでフォールバック cookie が作成されます。この cookie は s_fid と呼ばれ、2 年間の有効期限付きで設定され、今後のフォールバック識別方法として使用されます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management - DTM のルールが実行されないのはなぜですか。 </p> </td> 
   <td colname="col3"> <p>イベント型ルールが実行されない場合、ルールのセレクターまたは条件に問題がある可能性があります。Firefox で目的のイベントアクションが発生するサイトの要素を探して右クリックし、「要素を調査」を選択します。開いたボックスで強調表示されたスクリプトを検証し、正しい要素をターゲットにしていることを確認します。<a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>どのようにしてハートビートビデオトラッキングを導入すればよいですか。 </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="https" scope="external">この節</a>に、お使いのプラットフォーム用のビデオハートビート SDK および開発者ガイドをダウンロードする手順が含まれています。また、ビデオハートビートに関する特定の導入手順を含んでいるので、SDK をダウンロードする際に、docs フォルダーにある開発者ガイドもダウンロードしてください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>適切なサブドメインに cookie を追加するには、どうしたらよいですか。 </p> </td> 
   <td colname="col3"> <span class="varname"> cookieDomainPeriods </span> 変数は、ページURLのドメイン内のピリオド数を指定することで、Analyticsのcookie s_ ccとs_ sqが設定されるドメインを決定します。この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。[設定変数]（/help/implementing/js- implementation/c- variables/configuration- variables. md）を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>トラッキングサーバー - トラッキングサーバーを適切に設定するにはどうしたらよいですか。 </p> </td> 
   <td colname="col3"> <p>Adobe Analytics サーバーにデータを送信するように実装を設定する場合、正しい場所に送信する必要があります。そうしないと、訪問者数の水増しやデータ損失の原因となります。<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external">詳細情報...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>パフォーマンス - 外部の Adobe JavaScript の読み込みの失敗は（それが Adobe でのインターネット接続、プロキシ、ファイアウォール、またはサービスの中断によるものであろうとなかろうと）、パフォーマンスに影響しますか。 </p> </td> 
   <td colname="col3"> <p>いいえ。JavaScript ファイルは、Adobe サーバーでホストしていないで、Adobe の停止状態が JavaScript の実行に影響することはありません。Dynamic Tag Management が採用されている場合、JavaScript ファイルは Akamai でホストされているか、顧客が決定したサーバーの場所にあります。 </p> <p>「<i>Dynamic Tag Management によって Web サイトのパフォーマンスが低下することはありますか</i>」（<a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html" format="https" scope="external">Dynamic Tag Management FAQ</a>）を参照してください。 </p> <p>さらに、Akamai の CDN に依存することに不安を感じる場合は、独自のコア Dynamic Tag Management ファイルをホストできます。<a href="https://marketing.adobe.com/resources/help/en_US/dtm/?f=deployment" format="https" scope="external">埋め込みコードとホスティングオプション</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>パフォーマンス - 外部 Adobe JavaScript の読み込みがパフォーマンス低下の原因となることはありますか。 </p> </td> 
   <td colname="col3"> <p> JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。 </p> <p> [!DNL AppMeasurement]圧縮:アドビのJavaScriptクライアントのページの重さ（サイズ）が心配な場合、GZIPを使用してファイルの圧縮を検討することをお勧めします。GZIP はすべての主要なブラウザーでサポートされており、JavaScript の圧縮よりも高いパフォーマンスで、コア <span class="filepath"></span>JavaScript ファイルの圧縮と解凍がおこなわれます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>パフォーマンス - ブラウザーから Adobe サーバーへのデータの送信によってパフォーマンスが低下することはありますか。 </p> </td> 
   <td colname="col3"> <p> Adobe JavaScript ファイルは、HTML ページ内にイメージオブジェクトを作成し、ブラウザーは、Adobe サーバーからイメージオブジェクトをリクエストします。Adobe サーバーが低速になったり応答しなくなった場合、そのリクエストを処理するスレッドは、イメージが返されるかタイムアウトが発生するまで、遅延します。ブラウザーはイメージを複数のスレッドで処理するので、アドビの停止状態はページ読み込み時間にわずかな影響しか与えず、1 つのスレッドが停止していても、他のスレッドは機能し続けます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>パフォーマンス - Adobe からの JavaScript イベントがシステムの動作や機能に影響することはありますか。 </p> </td> 
   <td colname="col3"> <p>いいえ。前述のパフォーマンスに関する回答を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 収集されたデータを規定の条件に基づいて変更するにはどうすればよいですか。 </td> 
   <td colname="col3"> 処理ルールを使用すると、データ収集をシンプル化し、レポートに送信されるコンテンツを管理できます。<a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> s_code ファイルの最新バージョン </td> 
   <td> このセクションには、[!WebおよびモバイルプラットフォームにおけるDIL AppMeasurement]ライブラリ。各ライブラリの最新バージョンは、Reports &amp; Analytics／管理ツール／コードマネージャーからダウンロードできます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/?f=c_release_notes_javascript" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> s_code ファイルのデバッグ方法を教えてください </td> 
   <td> Adobe Debugger（旧称 DigitalPulse Debugger）はアドビが提供する無料のツールで、特定のページに関してユーザーのサイトから収集されたデータを表示することができます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> 複数のリンクタイプを追跡する方法を教えてください。 </td> 
   <td> ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=function_tl" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> ビデオを追跡する方法を教えてください。 </td> 
   <td> JavaScript を使用して、さまざまなプレーヤーを追跡できます。JavaScript を使用して追跡をおこなうには、プレーヤーが含まれている Web ページにコードを追加し、イベントハンドラーを使用してプレーヤーを追跡します。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> モバイルアプリを追跡する方法を教えてください。 </td> 
   <td> Adobe Mobile Services に一意の追跡コードを持つダウンロード計測用リンクが生成されます。ユーザーが生成されたリンクをクリックした後で Apple App Store からアプリをダウンロードして実行すると、SDK が自動的に獲得データを収集し、Adobe Mobile Services に送信します。<a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=acquisition" format="http" scope="external"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=acquisition" format="http" scope="external">Android </a> </td> 
  </tr> 
  <tr> 
   <td> ビデオトラッキングを導入する方法を教えてください。 </td> 
   <td> ビデオプレイヤーのイベントハンドラーに追加する関数を作成することで、メディアプレイヤーを追跡できます。これにより、Media.open、Media.play、Media.stop、Media.close を適切なタイミングで呼び出すことができます。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js_events" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> ファーストパーティ Cookie を設定する方法を教えてください。 </td> 
   <td> Analytics は、画像リクエストとブラウザーセッション間で保持されない変数およびコンポーネントの情報を提供するために、cookie を使用します。これらの cookie は安全で、アドビがホストするドメインから作成されるもので、サードパーティ cookie と呼ばれます。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> SSL 証明書を取得する方法を教えてください。 </td> 
   <td> サイトが https:// プロトコルを使用するかどうかを指定します。使用する場合、CSR を要求し SSL 証明書を購入する必要があります。注意：セキュリティで保護されているページやコンテンツがない場合、SSL 証明書は不要です。サイトでhttps://プロトコルのみを使用する場合は、この手順全体をスキップできます。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> 証明書の有効期限の通知に関する情報は、どこで確認できますか。 </td> 
   <td> SSL 証明書は毎年期限が切れ、期限切れになるたびにアドビから証明書の更新が要求されます。期限切れになると FPC スペシャリストから十分な警告がありますが、有効期限の監視、およびアドビへの更新された証明書の提供を事前に計画されることをお勧めします。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_renewals" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> プラグインとは何ですか。 </td> 
   <td> JavaScript 版 AppMeasurement プラグインは、いくつかの高度な機能を実行するプログラムや関数です。これらのプラグインは、JavaScript ファイルの機能を拡張して、基本的な導入では利用できなかった機能を提供します。アドビは他にも多数のプラグインを高度なソリューションの一部として提供しています。JavaScript を使用してデータを取り込む必要があるが、手順がわからない場合は、社内のアカウントマネージャーにお問い合わせください。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=impl_plugins" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> Data Insertion API についての情報 </td> 
   <td> アドビでは、Analytics にデータを送信する複数の方法を導入しています。<a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=usecase_sending_data_to_sc" format="http" scope="external"> 詳細情報 </a> </td> 
  </tr> 
  <tr> 
   <td> 500 エラーとは何ですか。 </td> 
   <td> 「500 Query Error」の状態を引き起こす内部サーバーエラーについての情報です。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=pageType" format="http" scope="external">pageType変数を参照してください </a> </td> 
  </tr> 
 </tbody> 
</table>

