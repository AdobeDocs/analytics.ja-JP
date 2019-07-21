---
description: Data warehouse は、保存用およびデータをフィルタリングして実行できるカスタムレポート用の、Analytics データのコピーを参照します。ユーザー独自の質問に基づいて生のデータから詳細なデータの関連性を表示するようにレポートにリクエストできます。Data warehouse レポートは、電子メールまたは FTP 経由で送信できます。処理のために最大で 72 時間かかります。処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。
seo-description: Data warehouse は、保存用およびデータをフィルタリングして実行できるカスタムレポート用の、Analytics データのコピーを参照します。ユーザー独自の質問に基づいて生のデータから詳細なデータの関連性を表示するようにレポートにリクエストできます。Data warehouse レポートは、電子メールまたは FTP 経由で送信できます。処理のために最大で 72 時間かかります。処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。
seo-title: Data Warehouseの概要
solution: Analytics
title: Data Warehouseの概要
topic: Data Warehouse
uuid: 768557dd-1644-4ce6- bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: 15d49195e5d555adcc37366d679d6b971972504b

---


# Data Warehouseの概要

Data Warehouse は、保存用およびカスタムレポート用の Analytics データのコピーを参照し、データをフィルタリングして実行できます。ユーザー独自の質問に基づいて生のデータから詳細なデータの関連性を表示するように、レポートにリクエストできます。Data warehouse レポートは、電子メールまたは FTP 経由で送信できます。処理のために最大で 72 時間かかります。処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。

アドビでは、特定のレポートスイートの管理者レベルのユーザーに対してのみ Data Warehouse を有効にします（Data Warehouse は、グローバルレポートスイートおよび子レポートスイートに対して有効にすることができます。ただし、ロールアップレポートスイートに対しては有効にすることができません）。管理者は Data Warehouse にアクセスできるグループを作成し、非管理者レベルのユーザーをそのグループに関連付けることができます。

Data Warehouse は、1 MB を超えるファイルを自動的に zip ファイルに圧縮します。電子メールの添付ファイルサイズは最大 10 MB です。

スケジュールに従ってダウンロードされる個々のレポートに対する 1 回のリクエストで、Data Warehouse の処理できる行数に制限はありません。

>[!NOTE]
>
>Data Warehouseは、レポート期間中に最初に検出された値をレポートします。

>[!IMPORTANT]
>
>分類された値にセグメント化する場合、Analysis WorkspaceとData Warehouseは「未指定」の値を扱います。Workspace では、「未指定」は分類されていない値を表し、Data Warehouse では「未指定」はユーザーが「未指定」に分類した値を表します。

## Data Warehouse リクエストの説明 {#section_F21C78ED36884C389C852E876AF5CDE8}

この表では、「[!UICONTROL Data Warehouse リクエスト]」タブのフィールドおよびオプションについて説明します。

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> リクエスト名</span> </td> 
   <td colname="col2"> リクエストを識別します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> レポート日</span> </td> 
   <td colname="col2"> <p>リクエストの日付と精度です。 </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle">カスタム</span>：カレンダーに設定する日付範囲。 </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle">プリセット</span>：プリセット範囲。プリセット範囲はレポート日に相対的な日時です。 </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle">精度</span>：時間の精度。設定できる値は「なし」、「時間」、「日」、「週」、「月」、「四半期」、「年」です。 </li> 
    </ul> <p>仮想レポートスイートの Data Warehouse レポートは、仮想レポートスイートで設定された別のタイムゾーンをサポートします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 選択可能なセグメント</span> </td> 
   <td colname="col2"> <p>調査対象の訪問者のみを選択し、複合セグメントを生成できます。事前に設定されたセグメントを読み込んだり、新しいセグメントを作成したり、またセグメントのコンポーネントを他のセグメント構築時に使用するためライブラリに保存することが可能です。 </p> <p>セグメントのスタックが可能になりました。複数のセグメントを選択するときには、プレビュー領域、リクエストマネージャー、リクエストの詳細のポップアップに、カンマ区切りの名前のリスト（「Segment1, Segment2」など）が表示されます。 </p> <p>詳細については、[セグメント化ガイド]（/help/components/c- segmentation/seg- home. md）を参照してください。 </p> <p>注意：同じ Data Warehouse レポート内の同一のセグメントに、セグメントフィルターと分類の両方を含めることはできません。これはエラーの原因となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 分類</span> </td> 
   <td colname="col2"> <p>分類を使用してデータを分類します。セグメントはデータセットからデータをフィルターし、分類はその分類で有効なすべての値のデータを区分するという点で、セグメントと分類は異なります。 </p> 1 つ以上のセグメントでレポートを分割することもできます。ただし、同じ Data Warehouse レポート内の同一のセグメントに、セグメントフィルターと分類の両方を含めることはできません。これはエラーの原因となります。 <p> 例えば、セグメントはデータセットから性別を削除するために使用し、分類は性別ごとに分割されたデータを確認するために使用します。 </p> <p>Data Warehouse のリクエストが複数の複数値のディメンションで送信されると（様々なモバイルレポートなど）、単一のヒットから行の指数が生成されます。単一のヒットから出力できる行数の条件は、100 です（以前は 1,000）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 指標</span> </td> 
   <td colname="col2">レポートする指標を追加できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 指標の並べ替え</span> </td> 
   <td colname="col2">Reports &amp; Analytics ユーザーインターフェイス、Data Workbench などに表示されるレポートのような、指標値を降順で並べ替えたランク分類レポートを提供します。<a href="../../export/data-warehouse/sorting-by-metric.md#concept_7B7BDE3D42E549389DACA1E33B2FC1CC" format="dita" scope="local">詳細情報...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 配信の予定</span> </td> 
   <td colname="col2"> <p>選択した間隔で、または 1 回限りのレポートとして、自動配信の要求をスケジュール設定できます。デフォルトの形式を使用した場合、レポートは .csv ファイルとして電子メールに送信されます。 </p> <p>データ範囲を追加するには、ファイル名に <span class="filepath">%R</span> を含めます。この値は、レポートで要求された期間の値を表します。例えば、2013 年 5 月 1 日から 2013 年 5 月 7 日までのデータを要求した場合、<span class="filepath">%R</span> を挿入することにより、ファイル名に「20130501 - 20130507」という期間が挿入されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

