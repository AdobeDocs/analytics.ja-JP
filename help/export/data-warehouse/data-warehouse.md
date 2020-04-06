---
description: Data Warehouse は、データをフィルタリングして、保存用およびカスタムレポート用の Analytics データのコピーを参照できます。ユーザー独自の質問に基づいて、生データから詳細なデータの関連性を表示するようレポートにリクエストできます。Data Warehouse レポートは、電子メールまたは FTP 経由で送信できます。処理のために最大で 72 時間かかります。処理時間は、処理の複雑さと要求されるクエリの量によって異なります。
title: Data Warehouse の概要
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Warehouse の概要

Data Warehouse は、データをフィルタリングして、保存用およびカスタムレポート用の Analytics データのコピーを参照できます。ユーザー独自の質問に基づいて、生データから詳細なデータの関連性を表示するようレポートにリクエストできます。Data Warehouse レポートは、電子メールまたは FTP 経由で送信できます。処理のために最大で 72 時間かかります。処理時間は、処理の複雑さと要求されるクエリの量によって異なります。

アドビでは、特定のレポートスイートの管理者レベルのユーザーに対してのみ Data Warehouse を有効にします。（グローバルレポートスイートと子レポートスイートで有効にできますが、ロールアップレポートスイートでは有効にできません）。管理者は、Data Warehouseにアクセスできるグループを作成し、非管理者レベルのユーザーをそのグループに関連付けることができます。

Data Warehouseは、1 MBを超えるファイルを自動的にzipします。 電子メールの添付ファイルの最大サイズは10 MBです。

Data Warehouseは、スケジュール済みおよびダウンロード済みの個々のレポートに対する1回のリクエストで、無制限の行数を処理できます。

>[!NOTE]Data Warehouse では、レポート期間中に最初に発生した値がレポートされます。

>[!IMPORTANT]
>
>分類された値でセグメント化する場合、Analysis Workspace と Data Warehouse では、「未指定」の値の処理方法が異なります。Workspace では、「未指定」は分類されていない値を表し、Data Warehouse では「未指定」はユーザーが「未指定」に分類した値を表します。

## Data Warehouse リクエストの説明 {#section_F21C78ED36884C389C852E876AF5CDE8}

次の表に、タブのフィールドとオプションを示 [!UICONTROL Data Warehouse Request] します。

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">リクエスト名</span> </td> 
   <td colname="col2"> リクエストを識別します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">レポート日</span> </td> 
   <td colname="col2"> <p>リクエストの日付と精度です。 </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle">カスタム</span>：カレンダーに設定する日付範囲。 </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle">プリセット</span>：プリセット範囲。プリセット範囲はレポート日に相対的な日時です。 </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle">精度</span>：時間の精度。設定できる値は「なし」、「時間」、「日」、「週」、「月」、「四半期」、「年」です。 </li> 
    </ul> <p>仮想レポートスイートのData Warehouseレポートは、仮想レポートスイートで設定された別のタイムゾーンをサポートします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">選択可能なセグメント</span> </td> 
   <td colname="col2"> <p>調査対象の訪問者母集団の一部を選択し、複雑なセグメントを生成できます。 事前設定済みのセグメントを読み込んだり、新しいセグメントを作成したり、セグメントのコンポーネントをライブラリに保存して、追加のセグメントを作成できます。 </p> <p>セグメントを積み重ねることができるようになりました。 複数のセグメントを選択する場合、プレビュー領域、リクエストマネージャーおよびリクエストの詳細ポップアップに、名前のコンマ区切りのリスト（Segment1、Segment2など）が表示されます。 </p> <p>詳しくは、<a href="/help/components/c-segmentation/seg-home.md">セグメントガイド</a>を参照してください。 </p> <p>注意：同じ Data Warehouse レポート内の同一のセグメントに、セグメントフィルターと分類の両方を含めることはできません。これはエラーの原因となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">分類</span> </td> 
   <td colname="col2"> <p>分類を使用してデータを分類できます。 セグメントと分類は異なりますが、セグメントではデータセットからデータをフィルターし、分類ではその分類に対して有効なすべての値でデータを区分します。 </p> また、1つ以上のセグメントでレポートを分類することもできます。 ただし、同じData Warehouseレポートに、同じセグメントにセグメントフィルターと分類の両方を含めることはできません。 これはエラーの原因となります。 <p> 例えば、セグメントを使用してデータセットから性別を削除し、分類を使用して性別ごとにデータを表示します。 </p> <p>複数の複数値のディメンション（様々なモバイルレポートなど）を使用してData Warehouseリクエストが送信されると、単一のヒットから行の指数が生成される場合があります。 1回のヒットから出力できる行数の上限は100（以前は1,000）です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">指標</span> </td> 
   <td colname="col2">レポートする指標を追加できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle">指標の並べ替え</span> </td> 
   <td colname="col2">Reports &amp; Analytics ユーザーインターフェイス、Data Workbench などに表示されるレポートのような、指標値を降順で並べ替えたランク分類レポートを提供します。<a href="/help/export/data-warehouse/sorting-by-metric.md"  >さらに詳しく...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">配信の予定</span> </td> 
   <td colname="col2"> <p>選択した間隔で、または1回限りのレポートとして、自動配信のリクエストをスケジュールできます。 デフォルトの形式を使用すると、レポートは.csvファイルとして電子メールで受信されます。 </p> <p>データ範囲を追加するには、ファイル名に <span class="filepath">%R</span> を含めます。この値は、レポートで要求された期間の値を表します。例えば、2013 年 5 月 1 日から 2013 年 5 月 7 日までのデータを要求した場合、<span class="filepath">%R</span> を挿入することにより、ファイル名に「20130501 - 20130507」という期間が挿入されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

