---
description: データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。
seo-description: データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。
seo-title: データタイプとカテゴリの概要
solution: Analytics
subtopic: データソース
title: データタイプとカテゴリの概要
topic: 開発者と導入
uuid: b5004cdc- b68a-4a82- a159- a7cd7b8bfe21
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# データタイプとカテゴリの概要

データソースのカテゴリは、提供する機能の類似性に基づいて様々なデータソースのタイプを識別します。

カテゴリによって、ユーザーの視点でデータソースをグループ分けすることができます。データソース UI からデータソースを作成する場合、まずデータソースのカテゴリを選択してから、データソースのタイプを指定します。各カテゴリに含まれるデータソースのタイプは、類似したタイプのデータをサポートしています。データソースには、次のようなデータソースのカテゴリがあります。

## Web サイトの使用状況 {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Web サーバーログファイル </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B" type="concept" format="dita" scope="local"> Web ログ </a> </p> </td> 
   <td colname="col3"> <p>大部分の Web サーバーは、提供したすべてのページを記録するログファイルを生成しています。このデータソースを使用すると、大部分の Web サーバーデータからのログファイルを処理してレポートに追加することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>広告クラウドバルクアップロード </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>手動およびExcelで自動化されたバルクアップロードをAdvertising Cloudで提供します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サイトレベルのトラフィックデータソース </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> トラフィック </a> </p> </td> 
   <td colname="col3"> <p>Web サイト全体のトラフィックデータをインポートします。例えば、ページビュー数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>分類トラフィックデータソース </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> トラフィック </a> </p> </td> 
   <td colname="col3"> <p>別の Web サイト変数で分類されたトラフィックデータをインポートします。例えば、製品別ページビュー数です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 広告キャンペーン {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>汎用広告サーバー </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>広告サーバーの広告アクティビティのインプレッションおよびその他のトップライン指標をマーケティングレポート内に組み込むことができます。これは汎用の広告サーバーデータソースであり、特定の広告サーバーがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>汎用電子メールキャンペーンサーバー </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>電子メールキャンペーンサーバーにある指標をマーケティングレポート内に統合できます。 </p> <p>一般的に統合される指標は、送信されたメッセージ数、配信されたメッセージ数、読まれたメッセージ数などです。これは汎用の電子メールキャンペーンデータソースであり、特定の電子メールキャンペーンサーバーがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>汎用ペイパークリックサービス </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p> インプレッション、クリック数、コストなど、ペイパークリックの実績に関するデータをインポートできます。 </p> <p>これは汎用のペイパークリックデータソースであり、特定のペイパークリックサービスがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 顧客関係管理（CRM） {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>汎用コールセンター </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>コールセンターに関する情報をマーケティングレポート内に組み込むことができます。比較的よくインポートされる指標として、通話回数、電話使用時間、エージェント名、合計販売額などがあります。 </p> <p>これは汎用のコールセンターデータソースであり、特定のコールセンターソフトウェアがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>汎用顧客サポート </p> <p>アプリケーション </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>カスタマーサポートソフトウェアに関する情報をマーケティングレポート内に組み込むことができます。新規サポート件数、解決したサポート件数、およびサポート解決の所要時間などの指標が含まれます。 </p> <p>これは汎用の顧客サポートデータソースであり、特定の顧客サービスアプリケーションがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 顧客満足度 {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>汎用調査データ </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>サードパーティのツールから得た調査結果をマーケティングレポート内に組み込むことができます。これにより、サイトでの顧客のインタラクションを基に顧客の全体的な満足度がわかります。 </p> <p>これは汎用の調査データソースであり、特定の調査データサービスがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サイトのパフォーマンス {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>汎用サイトダウンロード速度 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>ダウンロードの速度を追跡するアプリケーションまたはサービスから得たデータを、利用しているデータに統合できます。 </p> <p>これは汎用のダウンロード速度データソースであり、特定のダウンロード速度測定ソフトウェアまたはサービスがサポートされていない場合に使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 汎用 {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>一般的なデータソース（サマリデータのみ） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>このデータソースは、マーケティングレポートおよび Analytics にインポートするデータに近いタイプがない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一般的なデータソース（フル処理） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> フル処理 </a> </p> </td> 
   <td colname="col3"> <p>ログファイルのデータをインポートできます。このデータは、指定した時間にデータ収集サーバーで受信したかのように処理されます（各ヒットにタイムスタンプが付与されます）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>一般的なデータソース（トランザクション ID） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776" type="concept" format="dita" scope="local"> トランザクション ID </a> </p> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5" type="concept" format="dita" scope="local"> Visitor ID </a> </p> </td> 
   <td colname="col3"> <p>任意のオフラインイベントをオンラインイベントに関連付けることができます。トランザクション ID は、オフラインイベントとオンラインイベント間のキーとして機能します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## オンライン購入 {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>製品の返却数 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>製品返却データをインポートして購入 ID に関連付けることによって、返品につながる可能性の高い検索エンジン、キーワード、キャンペーンなどの属性を特定することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品コスト </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>Web サイトから購入および発送された製品の実際のコストが得られます。コストまたは利益を各製品に関連付けることで、Web サイトで最も利益を上げたキャンペーン、キーワード、社内プロモーションに関して正確なレポートが得られるようになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>注文ステータス </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>指標を使用して、発注されたすべての注文のステータス（キャンセルされた注文、発送済みの注文、完了した注文、不正と見なされる注文など）を特定します。 </p> <p>注文ステータスレポートでは、注文完了率が最も高い獲得方法を特定できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## リード数と見積もり数 {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>データソース </p> </th> 
   <th colname="col2" class="entry"> <p>処理タイプ </p> </th> 
   <th colname="col3" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>リードジェネレーション </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>Web サイトで発生したすべてのリードについて、実際に発生した売上高を含む、リード数の結果に関する情報をアップロードできます。 </p> <p>売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>オンラインの見積もり </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>Web サイトで発生したすべてのリードについて、実際に発生した売上高を含む、リード数の結果に関する情報をアップロードできます。 </p> <p>売上高をリード ID に正確に関連付けることで、最も利益を上げたキャンペーンとプロモーションを特定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コールセンターデータ </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> コンバージョン </a> </p> </td> 
   <td colname="col3"> <p>コールセンタートランザクションをアップロードして、顧客の電話に結びついた方策（キャンペーンやプロモーションなど）を特定できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

