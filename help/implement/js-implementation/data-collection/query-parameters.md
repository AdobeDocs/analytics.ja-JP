---
description: 以下の表に、データ収集に送られる各 Analytics 変数の値が含まれるクエリパラメーターを示します。
keywords: Analytics の導入
seo-description: 以下の表に、データ収集に送られる各 Analytics 変数の値が含まれるクエリパラメーターを示します。
seo-title: データ収集クエリパラメーター
solution: Analytics
title: データ収集クエリパラメーター
topic: 開発者と導入
uuid: 4d5af486- df27-42fe- bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# データ収集クエリパラメーター

以下の表に、データ収集に送られる各 Analytics 変数の値が含まれるクエリパラメーターを示します。

ここに示す情報は、[パケットアナライザー](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258)、イメージリクエストを手動で作成するとき、または動的変数を使用 [する場合](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> パラメーター </th> 
   <th class="entry"> Analytics 変数 </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Audience Manager のロケーションヒント（Experience Cloud 共有プロファイルの統合で使用） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Audience Manager Blob（Experience Cloud 共有プロファイルの統合で使用） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Analytics 訪問者 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> イメージリクエストの開始を示します。 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> イメージリクエストの終了を示します。これは、要求が切り捨てられていないことを表しています。 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | ブラウザーの高さ </td> 
   <td> ブラウザーウィンドウの高さ（ピクセル） </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | ブラウザーの幅 </td> 
   <td> ブラウザーウィンドウの幅（ピクセル） </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | 画面の色 </td> 
   <td> カラー画像画質（ビット） </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>なし </p> </td> 
   <td> <p>キー値のペアは以下のどちらかの形式で指定します。 </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>または </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>この例では、どちらの形式でもコンテキストデータ値は <code>my.a = red</code> になります。複数のキー値ペアを指定できます。 </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1 ～ c75 </td> 
   <td> s.prop1 ～ s.prop75 </td> 
   <td> すべてのカスタムトラフィックレポート </td> 
   <td> カスタムトラフィックレポートで使用されるトラフィック変数 </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> なし </td> 
   <td> サイトで使用される通貨の種類 </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> なし </td> 
   <td> cookieトラッキング用のドメインに含まれるピリオドの数を示します。この数は手動で設定します。 </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> なし </td> 
   <td> イメージリクエストの文字エンコーディング </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime（秒単位の s_vi cookie の保存期間） </td> 
   <td> なし </td> 
   <td> 訪問者 cookie の存続期間。 </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> サイトコンテンツ | サイトセクション </td> 
   <td> トラフィックレポートで使用されるサイトセクション変数 </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> ヒットタイプ </td> 
   <td> ヒットタイプ </td> 
   <td> 動作がフォアグラウンドでの直接的なインタラクションの結果なのか、バックグラウンドでの直接的なインタラクションなしにデバイスが送信する情報なのかを示します。 </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | 接続タイプ </td> 
   <td> 接続タイプ（モデムや LAN など。IE ブラウザーでのみ入力できます） </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> なし </td> 
   <td> <p>詳しくは、 <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> 動的変数 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events または ev </td> 
   <td> s.events </td> 
   <td> サイトトラフィック | 購入、買い物かご、カスタムイベント </td> 
   <td> ページで発生するコマースおよびカスタムイベント。コンバージョンレポートで使用されます。 </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> ページの現在の URL（最大 255 バイト） </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> 255 バイトを超える URL は分割され、最初の 255 バイトは g パラメーターに、残りのバイトはその後のクエリ文字列の -g= クエリパラメーターに表示されます。 </td> 
  </tr> 
  <tr> 
   <td> h1 ～ h5 </td> 
   <td> s.hier1 ～ s.hier5 </td> 
   <td> サイトコンテンツ | 階層レポート </td> 
   <td> トラフィックレポートで使用される階層変数 </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | 訪問者ホームページ </td> 
   <td> 現在のページがブラウザーのホームページであるかどうかを示します（Y または N。IE ブラウザーでのみ入力できます）。 </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | JavaScript のバージョン </td> 
   <td> インストールされている現在の JavaScript のバージョン（通常は 1.x）を表示します。 </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | cookie </td> 
   <td> ブラウザーで cookie がサポートされているかどうかを示します（Y、N または U）。 </td> 
  </tr> 
  <tr> 
   <td> l1 ～ l3 </td> 
   <td> s.list1 ～ s.list3 </td> 
   <td> カスタムコンバージョン </td> 
   <td> 変数に渡され、レポートの個別行項目としてレポートされる値の区切りリスト。 </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> Experience Cloud 訪問者 ID </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> イメージリクエストが JS ファイルから発生したものであるかどうかを示します（1 または 0）。 </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> なし </td> 
   <td> cookie が設定されているドメインを指定します。 </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> サイトコンテンツ | リンク | ClickMap </td> 
   <td> ClickMap で使用される、最後のページのオブジェクト識別子 </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> なし </td> 
   <td> サイトコンテンツ | リンク | ClickMap </td> 
   <td> ClickMap で使用される、最後のページのオブジェクトタグ名 </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | Netscape プラグイン </td> 
   <td> セミコロンで区切られるブラウザープラグインの名前 </td> 
  </tr> 
  <tr> 
   <td> pageName（または gn） </td> 
   <td> s.pageName </td> 
   <td> サイトコンテンツ | ページ </td> 
   <td> レポート内でページに指定された名前 </td> 
  </tr> 
  <tr> 
   <td> pageType（または gt） </td> 
   <td> s.pageType </td> 
   <td> サイトコンテンツ | エラーページ </td> 
   <td> 404 エラーページかどうかを示します（「エラー」または空白のいずれか）。 </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> 新規訪問者に対してのみ発生します。無限リダイレクトを防ぎます（常に true）。 </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> サイトコンテンツ | リンク | 出口リンク、ファイルのダウンロード数、カスタムリンク </td> 
   <td> 実行されたカスタムリンクのヒットの種類を特定します。 </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> なし </td> 
   <td> サイトコンテンツ | リンク | 出口リンク、ファイルのダウンロード数、カスタムリンク </td> 
   <td> カスタムリンクのヒットが発生した URL </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> なし </td> 
   <td> サイトコンテンツ | リンク | 出口リンク、ファイルのダウンロード数、カスタムリンク </td> 
   <td> カスタムリンクのわかりやすい名前 </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> なし </td> 
   <td> すべてのビデオレポート </td> 
   <td> レガシービデオレポートでマイルストーンを追跡するために使用されます。v15 では廃止されました。 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> アドビ側のみが使用するもので、変更できません。 </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> なし </td> 
   <td> サイトコンテンツ | リンク | ClickMap </td> 
   <td> ClickMap で使用される、最後のページのページ識別子 </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> なし </td> 
   <td> サイトコンテンツ | リンク | ClickMap </td> 
   <td> ClickMap で使用される、最後のページのページ識別子タイプ </td> 
  </tr> 
  <tr> 
   <td> products（または pl） </td> 
   <td> s.products </td> 
   <td> 製品 | 製品 </td> 
   <td> コンバージョンレポートで使用される製品変数 </td> 
  </tr> 
  <tr> 
   <td> purchaseID（または pi） </td> 
   <td> s.purchaseID </td> 
   <td> なし </td> 
   <td> 購入を複製するために使用されます。売上高の水増しを防ぎます。 </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> すべてのトラフィックソースレポート </td> 
   <td> 参照 URL </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | 画面の解像度 </td> 
   <td> 画面解像度（幅×高さ） </td> 
  </tr> 
  <tr> 
   <td> サーバー（または sv） </td> 
   <td> s.server </td> 
   <td> サイトコンテンツ | サーバー </td> 
   <td> トラフィックレポートで使用される、ページのサーバー </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> 訪問者プロファイル | 訪問者の都道府県／州 </td> 
   <td> 変数での定義に従って都道府県／州を指定します。 </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> （自動、カスタムタイムスタンプを持たないすべてのヒットと共に送信） </td> 
   <td> なし </td> 
   <td> <p><code>t</code> パラメーターは以下の形式で指定します。 </p> 
    <code>dd/mm/yyyy&amp; amp;nbsp;hh:mm:amp&amp; amp;nbsp;テキスト（&amp; amp）;nbsp;OFFSET </code>
  <p>ここで、D は曜日を表す <code>0 ～ 6</code> の範囲の値です。<code>OFFSET</code> は次の値を表します。 </p> 
    <code>offset&amp; amp;nbsp;from&amp; amp;nbsp;GMT&amp; amp;nbsp;in&amp; amp;nbsp;hours&amp; amp;nbsp;* amp;nbsp;60&amp; amp;nbsp;* amp;nbsp;-&amp; amp;nbsp;1 </code>
  <p> 次に例を示します。 </p> 
    <code>23/09/2016&amp; amp;nbsp;14:00:00&amp; amp;nbsp;1&amp; amp;nbsp;420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> なし </td> 
   <td> <p>計算され、ヒットと共に送信されるカスタムタイムスタンプ。通常、オフライントラッキングで使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | Java </td> 
   <td> Java が有効かどうか（Y または N） </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> キャンペーン | トラッキングコード </td> 
   <td> コンバージョンレポートで使用されるキャンペーン変数 </td> 
  </tr> 
  <tr> 
   <td> v1 ～ v75 </td> 
   <td> s.eVar1 ～ s.eVar75 </td> 
   <td> すべてのカスタムコンバージョンレポート </td> 
   <td> カスタムコンバージョンレポートで使用されるコンバージョン変数 </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> なし </td> 
   <td> 訪問者固有の ID。を" 訪問者 ID 変数. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> なし </td> 
   <td> 訪問者の移行キー。サードパーティからファーストパーティへ cookie を移行するために使用します。非推奨です。 </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> なし </td> 
   <td> Genesis 統合で使用されます。 </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> なし </td> 
   <td> オンラインデータをオフラインデータにリンクするために使用されるトランザクション ID </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> 訪問者プロファイル | 訪問者の郵便番号 </td> 
   <td> 変数での定義に従って郵便番号を特定します。 </td> 
  </tr> 
  <tr> 
   <td> イメージリクエスト URL 内の /5/（モバイルプロトコルの場合）または /1/（モバイルプロトコル以外の場合） </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> <p> 訪問者の識別に cookie とそれ以外の手段が使用される順序を制御します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

