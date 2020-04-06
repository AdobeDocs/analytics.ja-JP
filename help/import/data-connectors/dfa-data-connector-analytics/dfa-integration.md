---
description: 'DFA 統合の設定には、次のタスクが含まれます。 '
keywords: DFA
title: DFA 統合
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# DFA 統合 {#dfa-integration}

DFA 統合の設定には、次のタスクが含まれます。

## DFA 統合の設定 {#configure-the-dfa-integration}

DFA Data Connectors 統合について、順を追って説明します。

設定ページには、統合の概要と、詳細に関する便利なリンクが表示されます。 この統合に関連するAdobeとDoubleClickの両方の料金が発生します。 両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。

1. [!DNL Adobe Analytics] にログインします。
1. クリック **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. を見つ **[!UICONTROL DoubleClick DFA]**&#x200B;けて、をクリックしま **[!UICONTROL Add New]**&#x200B;す。

   ![手順の結果](assets/wizard-01.png)

   統合ウィザードの各ページで、必要な情報を入力し、をクリックしま **[!UICONTROL Next]**&#x200B;す。 次の表に、ウィザードを使用して統合を完了するために必要な情報を示します。

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ウィザードのページ番号 </th> 
   <th colname="col2" class="entry"> フィールド </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 統合名 </td> 
   <td colname="col3"> Genesis で、レポートスイートの有効な統合リストに表示される統合名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 統合電子メールアドレス </td> 
   <td colname="col3"> この統合に関連するすべての通知を受信する電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ユーザー名 </td> 
   <td colname="col3"> この統合で使用するDFA APIユーザー名。 APIログイン用のユーザーを有効にするには、DFAインターフェイスのAPI属性を確認します。 APIログインを有効にすると、ユーザーのパスワードを入力するためのパスワードフィールドが表示されます。 このパスワードは、認証のためにウィザードにユーザー名と共に入力します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> パスワード </td> 
   <td colname="col3"> DFA APIパスワード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 広告主ID </td> 
   <td colname="col3"> <p>DFA広告主IDまたは親のFloodlight設定ID。 Data Connectorsは、このIDを使用して、追跡するDFA広告主を識別します（統合のバージョン1.5）。 この広告主 ID は、統合のバージョン 2.0 では使用されません。親の Floodlight 設定 ID が検索され、使用されます。画面の説明を参照してください </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA広告変数 </td> 
   <td colname="col3"> DFAデータ属性、インプレッションおよびキャンペーンのクリック数データを受け取るAnalytics eVar。 通常、これはトラッキングコードeVar( <span class="varname"> s.キャンペーン </span>)ですが、使用可能な任意のeVarを選択できます。 また、Data Connectorsは、選択したeVarに次のDFA関連の分類を追加します。 <p><b>キャンペーン</b>:共通のメッセージを伝える複数のサイトに提供される広告の集まり。 </p> <p><b>サイト名</b>:広告が提供されたサイト。 </p> <p><b>広告名</b>:DFAアカウントで定義される広告名。 </p> <p><b>サイト配置名</b>:広告が提供されたWebサイトおよびページ。 </p> <p><b>配信ツール</b>:DoubleClick for Advertisers。 </p> <p><b>チャネル</b>:バナー広告。 </p> <p><b>コスト構造</b>:CPM、CPC、または固定。広告のコスト構造に基づきます。 </p> <p><b>クリエイティブ名</b>:広告/プレースメント/クリエイティブIDに関連付けられたクリエイティブの名前。 </p> <p><b>DFA/SearchCenter重複排除 - 重複</b>:DFAクリックスルーまたは表示スルーが発生した場合に、DFAがSearchcenter変数に値を配置するように指定します。 </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> インプレッション </td> 
   <td colname="col3"> DFAインプレッション数指標イベントを受け取るカスタムデータ。 インプレッション数は、広告が提供された回数を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> クリック数 </td> 
   <td colname="col3"> DFAクリック数指標イベントを受け取るカスタムデータを選択します。 クリック数は、訪問者が DFA のリダイレクトによって測定された広告をクリックした回数を示します。クリック数指標は、Analytics クリックスルー指標と相関関係があります。 <p>注意： DFA クリック数と Analytics クリックスルー数ではデータの収集方法が異なるので、厳密に一致しない可能性があります。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 表示スルー変数 </td> 
   <td colname="col3"> <p>DFA表示スルーデータを受け取るAnalytics eVar。 表示スルー変数は、表示スルーがサイト上のコンバージョン率に与える影響を確認するのに役立ちます。 </p> <p>Data Connectorsは、DFA広告変数に追加するのと同じDFA関連の分類をこのeVarに追加します（上記を参照）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 前回の表示からの時間(表示スルー時間グループ変数) </td> 
   <td colname="col3"> DFAの前回のデータからの時間を受け取るAnalytics eVar表示。 前回からの時間表示は、最後の広告の表示スルーから経過した時間を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 表示スルー </td> 
   <td colname="col3"> DFAイベントスルー指標データを受け取る表示のカスタムデータ。 ビュースルーイベントをビュースルー変数と共に使用して、直接クリックスルーに影響しないが、その後の時間にサイトへのトラフィック上昇に一役買った可能性のあるキャンペーンはどれかを確認します。 <p>Data Connectors は、選択したカスタムイベントの名前を「ビュースルー数」に変更します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFAクエリエラー </td> 
   <td colname="col3"> （オプション）レポートされたDFAクエリエラーメッセージコードを受け取るAnalytics eVar。 可能なDFAメッセージコードは次のとおりです。 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>:DoubleClick cookieを使用しない。 </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>:ユーザーがオプトアウトしました。 </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>:キャンペーン履歴なし。 </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>:クエリエラー（タイムアウト、サーバーダウンなど） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> タイムアウトイベント </td> 
   <td colname="col3"> <p>s.maxDelayタイマーが期限切れになるたびに増加し、 <span class="varname"> DFAサーバーか </span> ら応答を受け取らない、Analyticsカウンターイベント。 このイベントを使用して、<span class="varname"> s.maxDelay </span> 変数 Tuning s.maxDelay </a> を設定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## DFA 統合のための Web サイトの更新 {#web-site-updates-for-the-dfa-integration}

Genesis で DFA 統合用に Analytics レポートスイートを設定したら、統合をサポートするために、記載された手順に従って Web サイトおよび DFA 環境を設定する必要があります。

### ドメインの cookie 領域の検証 {#verify-cookie-space-on-the-domain}

DFA用のData Connectors統合では、ページのドメインにcookieを設定する必要があります。

稀に見られますが、一部のドメインは、一部のWebブラウザーでcookieの最大容量に達しています。 訪問者の Web サイトでの閲覧に影響を与えないよう、ネットワーク運用チーム、開発チーム、またはエンジニアリンググループに相談して、DFA 統合に使用されるページのドメインに別の cookie を追加してもユーザーエクスペリエンスに影響がでないかを検証します。また、cookie の名前を選択する必要があります。

### DFA クエリー文字列パラメーターの更新 {#update-your-dfa-query-string-parameter}

DFA 統合の前に既に Adobe Analytics で広告キャンペーンをトラッキングしている場合、すべてのキャンペーン（電子メール、検索またはバナー）で同じクエリー文字列パラメーターを使用して、ランディングページ上の参照するキャンペーン ID を識別できます。

DFA広告キャンペーン用にDFAデータから表示スルーおよびクリックスルーデータをいつリクエストするかを理解するには、Data Connectorsは、訪問者がDFAキャンペーンバナー広告をいつクリックしたかを識別する必要があります。 これを可能にするために、異なるクエリー文字列パラメーターを DFA 広告キャンペーンのランディングページ URL に追加して、Data Connectors が Web サイトで実施する DFA 広告キャンペーンページと他の広告キャンペーンページを区別できるようにする必要があります。DFA では JavaScript プラグインの `dfa_overrideParam` を使用していました。

>[!CAUTION]
>
>警告：Campaign 変数は他のキャンペーンに使用できますが、DFA キャンペーンには使用しないでください。Campaign 変数を DFA キャンペーンのランディングページに設定すると、アドビはインプレッション数とクリック数を DFA キャンペーンのクリックスルーに結び付けることができなくなります。1回の訪問で1回、アドビの収集サーバーは、以前のクリックスルーまたは表示スルーについてDFAサーバーを確認します。 そのため、共通のランディングページにはDFA プラグインコードのみを含め、特に低速インターネット接続を使用するユーザーに対しては、ページ読み込み時間を遅くする不要なリダイレクトをおこなわないようにしてください。

## Web サイトのデータコレクションコードの更新 {#update-your-web-site-s-data-collection-code}

DFA 用の Genesis 統合は、DFA Floodlight 設定 ID（dfa_SPOTID）を利用します。これにより、DFA と Adobe データ収集システム間のレポートの一貫性が向上します。

>[!NOTE]注意：Google DFA の最近のリリースで 「Spotlight」という用語は、「Floodlight」に変更されました。JavaScript パラメーター `dfa_SPOTID` は、Spotlight の用語に基づいて命名されましたが、両方のバージョンで使用されます。

WebサイトでDFA統合を有効にするには、次を追加してJavaScriptデータ収集コードを更新する必要があります。

* DFA 用 Integrate モジュール
* コレクションコードへの追加

### DFA 用 Integrate モジュール {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA 統合は、Adobe Experience Cloud Integrate モジュールを利用して、コア JavaScript データコレクションコード（`s_code.js`）に機能を追加します。Integrate モジュールは、コードマネージャーから JavaScript 版 AppMeasurement コードをダウンロードする際に、.zip ファイルの一部として提供されます。アドビコンサルタントにお問い合わせください。

Integrate モジュールコードを Web サイトの `Modules` ファイルの `s_code.js` セクションに挿入します。

### コレクションコードへの追加 {#section-8f98c727f1ba414fb8b4f02d696b8791}

統合ウィザードでの DFA 統合のアクティブ化の際の選択に基づいて、Data Connectors は、カスタマイズした追加を JavaScript データコレクションコードに生成して電子メールで送付します。`s_code.js` ファイルの（`doPlugins` 関数またはその他の関数ではなく）メインセクションにこのコードを挿入します。

以下に示すサンプルコードは、説明用です。data connectors統合ウィザードを完了した後に電子メールで送信されたコードを使用します。

コレクションコードは、次のコンポーネントで構成されます。

* DFA Integrate設定
* 統合が必要なプラグイン

**DFA Integrate設定**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA Integrate Settingsブロックは、DFA統合で必要な変数を設定します。 これらの各変数の値は、次のソースから取得されます。

**CSID**:クライアント側ID。 統合ウィザードを完了すると、DFAによって生成されます。 Data Connectorsは、DFA CS IDを使用してこの変数を事前設定し、統合ウィザードの完了後にこの値をセットアップ電子メールで送信します。 アカウントでアドバンス広告配信が有効になっている場合、この変数は不要です。

**SPOTID**:Floodlightの設定（旧称Spotlight ID）。 Data Connectorsは、統合ウィザードで指定したDFAアカウント情報に基づいて、DFA Floodlight設定IDでこの変数を事前設定します。

**tEvar**:変数の転送を参照してください。 Data Connectorsは、統合ウィザードで表示スルー変数に対して指定したAnalytics変数名でこの変数を事前設定します。 この値は、アドビエンジニアリングまたはエンジニアリングサービスと慎重に調整しない限り変更しないでください。

**errorEvar**:エラー変数。 Data Connectorsは、統合ウィザードでDFAクエリ失敗変数に対して指定したAnalytics変数名でこの変数を事前設定します。

**timeoutEvent**:タイムアウトイベント。 Data Connectorsは、統合ウィザードでタイムアウト変数に指定したAnalytics変数名を使用して、このイベントを事前設定します。

**requestURL**:広告情報のためのリモートDFAホストからクエリへの接続。 アドビの指示がない限り、この値を変更しないでください。

**maxDelay**:DFA Floodlightサーバーからの応答をJavaScriptデータ収集コードが待機する時間をミリ秒単位で指定します。 サイトのトラフィックに基づく最適な値を見つけるために、この値をテストしてみることをお勧めします。例えば、この値を増やすと、一般により多くのDFAデータが収集されますが、遅延期間中に訪問者がサイトを離れた場合に、ベース訪問者データが失われるリスクが高くなります。 この値を減らすと、ヒットデータを失うリスクは低くなりますが、アドビのヒットデータと共に送信されるDFAデータの量が減る可能性があります。

**visitCookie**:DFA呼び出しを訪問ごとに1回に制限するために使用するcookieの名前。

**clickThroughParam**:クエリ文字列。通常、すべての広告に含まれ、クリックが発生したことをIntegrateモジュールに通知します。 クエリー文字列にこのパラメーターがあると、訪問者が過去 30 分間に既にクエリされていても、DFA Floodlight サーバーにリクエストが発生します。

**newRsidsProp**:（オプション）未使用のトラフィックプロパティ変数にマッピング済み。 DFA統合は、この値を収集して訪問cookieに保存し、特定の訪問者のデータを収集したレポートスイートを識別します。 このプロパティは、アドビエンジニアリングサービスを使用したカスタム実装でのみ必要です。

**統合が必要なプラグイン**

コレクションコードの追加は、DFA統合の操作を改善する追加のプラグインを組み込みます。

* DFAクエリを訪問ごとに1回に制限
* cookie名に柔軟性を持たせます。 ほとんどの組織はs_dfaを使用しますが、DFA統合には任意の有効なcookie名を使用できます。
* 不要なリダイレクトを排除。 表示スルーデータはリアルタイムで収集されるので、アドビの収集サーバーとDFAは、すべてのページのデータを交換する可能性があります。表示 このプラグインは、情報が不要な場合に、これらのデータの交換をブロックします。

>[!CAUTION]
>
>不要な DFA クエリを排除するためにプラグインが使用するメカニズムの 1 つに、ドメインベースの訪問 cookie があります。複数のドメインにわたる統合レポートスイートは、DFA が影響を受けるビュースルーまたはクリックスルーの後で訪問者がドメインを横断すると、クリックスルーおよびビュースルーデータを水増しします。

## DFA 統合の成功の確認 {#confirming-a-successful-dfa-integration}

必要なすべての Web サイトの更新をおこなったら、Charles*、Chrome Developer Tools または Firebug* などのネットワークトラフィックビューアを使用して、DFA が Adobe コレクションサーバーと通信していることを確認できます。

DFA 対応 `s_code.js` ファイルをデプロイしたら、ネットワークトラフィックビューアを使用して、DFA と Adobe データコレクションサーバーの間のリクエストを表示します。以下を確認します。

* DFA の `fls.doubleclick.net/json` サービスへのリクエスト。このサービスの応答は、使用しているDFAのバージョンに応じて異なる場合があります。 DFA統合バージョン1.5の場合：

   * [!DNL ad.doubleclick.net] への HTTP 302 リダイレクト。これは、広告訪問者に関する情報を含む応答に Location: タグを送信します。
   * この Location タグによって、[!DNL integrate.112.2o7.net/dfa_echo] にリダイレクトされます。このサービスは、広告訪問者に関する情報をJSON(JavaScript Object Notation on)エンコードされた文字列に変換します。 このデータは、200 OK HTTP応答で返されます。

* DFA統合バージョン2.0（高度な広告配信が有効）の場合：

   * [!DNL fls.doubleclick.net] が 200 OK で直接返されます。

どちらの場合も、リクエストが成功すると、パラメーターvXを含むアドビのデータ収集サーバーにリクエストが送信されます。ここで、Xは表示スルーeVar番号です。 このパラメーターの値は次の形式を取ります。DFA-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. この文字列には、現在のインプレッションの最後のクリックと最後のインプレッションに関する訪問者が含まれます。

## s.maxDelay の調整 {#tuning-s-maxdelay}

DFA を正しく導入することが、特定のサイトの s.maxDelay の最適化に影響します。

一般に、*`s.maxDelay`* の増減を決定する際には、取得する DFA 訪問者データを増やすか、アドビ訪問者データの収集を危険にさらすかの間のトレードオフが必要になります。*`s.maxDelay`* を増やすと、取得される DFA 訪問者データも増加しますが、（過度に高く設定すると）Adobe 訪問者データのコレクションを危険にさらす可能性があります。s.maxDelay を減らすと、Adobe 訪問者データのコレクションは守られますが、DFA 訪問者データを失う可能性があります。

*`s.maxDelay`* は、単なる DFA に接続するためのネットワーク通信の時間以上のものをカプセル化します。また、これらの通信が基にする JavaScript を実行および評価するためのブラウザー遅延を表します。これは、Integrate モジュールが、DFA Floodlight サーバーからデータを取り込む DOM に HTML 要素を挿入した後で、*`s.maxDelay`*&#x200B;タイマーを開始するためです。この新しいHTML要素に基づいて、ブラウザーが実際にHTTPリクエストを開始するまでにかかる時間は、同時に読み込む他の画像やJavaScriptファイル、訪問者コンピューターの速度、特定のブラウザー実装によって異なります。 さらに、JSONデータがDFA Floodlightサーバーから取得される場合、JavaScriptはブラウザーで評価される必要があります。 これもまた、ブラウザーによって完全に制御され、同時に大量のJavaScriptコードが実行されている場合や、非同期JavaScriptリクエストが多数発生している場合は、遅延が発生する可能性があります。

With this in mind, *`s.maxDelay`* needs to be set dependent up on the complexity of the landing page plus the amount of network delay with DFA. 一部のサイトでは、ページの読み込みの早い段階でAdobeコレクションコードを実行し、Floodlightサーバーがリクエストされた時点でのブラウザーでの動作を減らすことが、複雑さを軽減する1つの方法です。

Timeout変数は、s.maxDelayタイムアウトに達するた *`s.maxDelay`*&#x200B;びに増加するので、調整時には絶対に必要です。 *`s.maxDelay`* の増減を決定する場合は、次の手順を実行することをお勧めします。

1. *`s.maxDelay`* を特定の値に設定して、数日間のデータを収集する。
1. 時間範囲に対して [!DNL Daily Unique Visitors Report] を実行する。
1. [!DNL Timeout Event Report] を実行して、タイムアウトになる数をチェックする。タイムアウトは訪問者ごとに1回のみ収集されます。

数字を手に入れたら、

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

タイムアウトの割合は、実際にはサイトへのすべての訪問者を考慮しています。 これらの訪問者の一部はDFAにまったく結び付けられていないので、タイムアウトは誤った結果になります。 この計算結果を改善するには、別の分析で、`clickThroughParam` を設定した（例：`?CID=1`）ページへの個別訪問者のみを考慮します。これにより、より正確に表示されます。

タイムアウトの割合が非常に低い場合、*`s.maxDelay`* を減らすことを検討してください。非常に高い場合は、*`s.maxDelay`* を増やします。*`s.maxDelay`* を減らす場合、[!DNL Timeout Report] を再実行することで、タイムアウトが劇的に増加していないことを確認できます。*`s.maxDelay`* を増やす場合、[!DNL Page Views Report] を実行することで、データ損失に起因してページビューが減少していないことを確認できます。*`s.maxDelay`* が変更されるたびに、数日間のデータを観察し、データが日々の変動だけでなく、傾向を表していることを確認します。

*`s.maxDelay`* の最適な設定は、タイムアウトの割合が最小になると同時に、ページビューが下降しないポイントです。

統合のバージョン 2.0 に移行すると、302 リダイレクトが排除されるので、タイムアウトは減少することが予想されます。ベータクライアントの初期の結果では、タイムアウトが一貫して減少し、より多くのDFAデータが収集されています。
