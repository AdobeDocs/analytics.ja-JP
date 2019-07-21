---
description: 'null'
seo-description: 'null'
seo-title: Attribution IQ の FAQ
title: Attribution IQ の FAQ
uuid: 90961172-869d-4ed3- aba5-52374e53b603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# Attribution IQ の FAQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q：新しいアトリビューションモデルの使用時に、「なし」行項目が予想よりも高い有効性の評価を受けることがあるのはなぜですか。</b> </p> </td> 
   <td colname="col2"> <p>A：<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">ここ</a>で説明されているように、選択したレポートウィンドウが原因である可能性が高いです。多くの場合、レポートウィンドウの開始日がその当月の月初日であり、訪問者（レポートウィンドウ）ルックバックを使用している場合に起こります。追加のアトリビューションルックバックを取得し、「なし」行項目の有効性の評価を下げるには、レポートウィンドウの時間範囲を延長してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：アトリビューションモデルの使用時に、レポート期間外の日付がレポートに表示されることがあります。なぜですか。</b> </p> </td> 
   <td colname="col2"> <p>A：これらの余分な日付は、訪問者レポートルックバックウィンドウに見られる人為的な結果です（<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">こちら</a>を参照）。現在これが起こる理由については、<a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">Data appearing outside reporting window</a>（レポート期間外に出現するデータ）の記事で説明しています。Adobe Analytics の次期リリースでは、これらの余分な行は除外されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：独自のアトリビューションモデルでカスタムルックバックウィンドウを使用できますか。</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：「訪問」アトリビューションルックバックと「訪問者」アトリビューションルックバックは、どのような場合に使用すればよいですか。</b> </p> </td> 
   <td colname="col2"> <p>A：アトリビューションルックバックの選択は、実際にはユースケースによって決まります。コンバージョンの検討サイクルが比較的長い（1 回の訪問より長い）場合は、訪問者ルックバックを使用するか、その検討サイクルをより正確に反映する長い訪問の VRS を作成することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：アトリビューションモデルはデータフィードやデータウェアハウスでも使用できますか。</b> </p> </td> 
   <td colname="col2"> <p>A：いいえ。アトリビューションモデルは<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">レポート時間処理</a>を使用してレポート時に計算されるので、データフィードやデータウェアハウスにアトリビューションモデルを反映させることはできません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：アトリビューションモデルを使用できるのは、レポート時間処理を有効にして仮想レポートスイートを使用する場合だけですか。</b> </p> </td> 
   <td colname="col2"> <p>A：いいえ。アトリビューションモデルでは<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">レポート時間処理</a>をバックエンドで利用しますが、便宜上、VRS でも基本レポートスイートでもアトリビューションモデルを使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Analysis Workspace の Attribution IQ では、データドリブンアトリビューションモデルやアルゴリズムアトリビューションモデルをサポートしていますか。</b> </p> </td> 
   <td colname="col2"> <p>A：これは Analysis Workspace ではまだ利用できませんが、サポートを前向きに検討しているところです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Attribution IQ でサポートされていないディメンションや指標はありますか。</b> </p> </td> 
   <td colname="col2"> <p>A:アトリビューションIQはすべてのディメンションでサポートされています。</p> 
    <p>（主に意味がないので）サポートされて<u>いない</u>指標は以下のとおりです。 </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> 実訪問者数 </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">訪問回数 </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">発生件数 </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> ページビュー数 </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">A4T（Analytics と Target の統合）関連指標 </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">滞在時間指標 </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">バウンス </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">バウンス率 </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">入口 </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">出口 </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">エラーページ(404) </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">検索 </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">直帰数 </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">単一アクセス </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Attribution IQ は Data Workbench のアトリビューションとどう違うのですか。</b> </p> </td> 
   <td colname="col2"> <p>A：Data Workbench では以下の機能を増分的に提供しています。 </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">広告インプレッション数や POS など、より多くの訪問者レベルデータソースを対象にしたアトリビューション分析。 </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">アルゴリズム（<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">最適</a>）モデリング。Attribution IQ にはルールベースモデルのみ含まれています。 </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">追加のビジュアライゼーション（<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">待ち時間テーブル</a>など）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Attribution IQ はデータソースに対応しますか。</b> </p> </td> 
   <td colname="col2"> <p>A：現在、Attribution IQ は、サマリレベルのデータソース以外のデータソースに対応しています。 </p> <p> サマリレベルのデータソースは Analytics の訪問者の識別子に関連付けられていないので、詳細なアトリビューションができないからです。トランザクション ID のデータソースについては、<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">レポート期間処理</a>が有効になっている仮想レポートスイートで使用される場合を除いて対応しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Attribution IQ は <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a> との統合に対応していますか。</b> </p> </td> 
   <td colname="col2"> <p>A：インプレッション数、コスト、クリック回数、平均位置、平均品質スコアを含む統合指標はサマリレベルのデータソースなので、Attribution IQ との互換性はありません。ただし、メタデータディメンション（一致する種類やキーワード）は、標準の Analytics のイベントや指標とともに使用する場合に限り Attribution IQ で対応できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

