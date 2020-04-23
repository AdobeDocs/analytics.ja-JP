---
description: データの場所に関する訪問者を表示します。 地理特性レポートには、国、地域、市区町村、米国の州、米国DMA（デジタル販売地域）が含まれます。 地理特性レポートは、すべてのお客様に対して有効になります。
title: 地理特性
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 地理特性

データの場所に関する訪問者を表示します。 地理特性レポートには、国、地域、市区町村、米国の州、米国DMA（デジタル販売地域）が含まれます。 地理特性レポートは、すべてのお客様に対して有効になります。

Reports &amp; Analyticsで利用できる指標は、すべて自動的に国、地域、市区町村、米国の州、DMAのレポートに含まれます。コンバージョンおよび訪問ベースの指標、および計算指標。 For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> レポート </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 国 </td> 
   <td colname="col2"> <p> 最大の地域区分。 このレポートには、ほとんどのレポートで表示される標準的なランクビューとトレンドビューのほか、トラフィック量に基づいて国を色分けしたマップビューもあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地域 </td> 
   <td colname="col2"> <p> 国より小さく、市区町村より大きい地域です。 一部の国では、地域は州、郡、または県です。 その他の地域では、構成国、部門、または大都市圏です。 表示されている各地域の右側に、地域の国も括弧で囲まれて表示されます。 </p> <p>表の詳細で、[市区町村レポートをこの地域で実行する] （虫眼鏡アイコン）をクリックしてレポートを実行し、選択した地域の市区町村と地域の他の市区町村とのパフォーマンスを比較します。 </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 市区町村 </td> 
   <td colname="col2"> <p> 最も小さい地域区分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 米国の州 </td> 
   <td colname="col2"> <p> 米国の各州の訪問者を示すヒートマップ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 米国 DMA </td> 
   <td colname="col2"> <p> （デジタル販売地域）米国内のラジオやテレビのメディア市場部門。 レポートをフィルタリングして、特定の州のマーケティング領域のみを表示できます。 このデータは、アドビとNielsen Media Research, Inc.との提携を通じて提供されます。 </p> <p>注：米国 DMA レポートの指定のないエントリは、訪問者が特定の DMA に関連付けられていないことを示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポートの精度 </td> 
   <td colname="col2"> <p>アドビは、IPインテリジェンスおよび認証ソリューションのリーディングプロバイダーであるDigital Envoyと提携し、エンドユーザーのIPアドレスに基づく地理的測定機能であるオファーの地理特性を測定しました。 個々のデータセットに基づく精度は異なりますが、一般に、Digital Envoyのオファーは国レベルで99%を超え、地域レベルで97%を超え、市区町村レベルで90%を超える精度を示します。 </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>IP アドレスは郵便番号にマッピングされます。どの市区町村に属するかは、「地方自治体」が定める郵便番号に基づいて判断されます。例えば、ベルリンの郊外はベルリンの一部ではなく、別個の町または市として扱われます。これは、IP アドレスがそれらの町または市の郵便番号に正確にマッピングされるためです。 </p> <p>地理特性データに影響を与える要因には、次のようなものがあります。 </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">企業プロキシを表すIPアドレス。 これらは、ユーザーの会社のネットワークを通るトラフィックとして表示される場合があります。ユーザーがリモートで作業している場合は、実際には別の場所にある可能性があります。 </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">モバイルIPアドレス。 モバイルIPターゲット設定は、場所やネットワークに応じて様々なレベルで機能します。 多数の通信事業者が、中央のPOPまたは地域のPOPを通じてIPトラフィックをバックホールしています。 </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">衛星ISPのユーザに属するIPアドレス。 これらのユーザは通常、アップリンクの場所から来ているように見えるので、特定の場所を識別するのは困難です。 </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">軍および政府のIP。 これは、多くの場合、現在駐在している基地やオフィスではなく、世界中を移動し、自宅の場所を通じて入る人員を表します。 </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">アドビの地理特性/IPデータは、サードパーティのベンダーが提供し、ISPや他のネットワークソースから提供される情報に基づいて定期的に更新されます。 IP検索は、世界中で頻繁に購入され、販売されているので、本質的に不安定です。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

