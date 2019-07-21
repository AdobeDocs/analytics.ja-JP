---
description: 時刻やファイル形式を指定してレポートをスケジュール送信することができます。
seo-description: 時刻やファイル形式を指定してレポートをスケジュール送信することができます。
seo-title: データリクエストのスケジュール設定
solution: Analytics
title: データリクエストのスケジュール設定
topic: Report Builder
uuid: f6d8c90f- e185-4d60-8035- f20f74bfcd89
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# データリクエストのスケジュール設定

時刻やファイル形式を指定してレポートをスケジュール送信することができます。

**データリクエストをスケジュールするには**

1. レポートを作成して保存します。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   「[!UICONTROL 予定レポート]」タブでは、作成したすべてのタスクと残りのタスク数などの概要が表示されます。
1. **[!UICONTROL 「予定レポート]** »タブで、??«新規??****
1. 基本のスケジュールウィザードに、次のように表示されます。

   ![](assets/simple-schedule-wizard.png)

1. [!UICONTROL 基本のスケジュールウィザード]で、次のオプションを設定します。

* **レポート**&#x200B;の選択:レポートの名前。新規の予定レポートでは、このフィールドに実行中のワークブック名が入力されます。

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>レポートの選択 </p> </td> 
   <td colname="col2"> <p>レポートの名前。新規の予定レポートでは、このフィールドに実行中のワークブック名が入力されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選択 </p> </td> 
   <td colname="col2"> <p>「<span class="wintitle">レポートの選択</span>」ページが表示されます。レポートは、サーバー（以前に作成されたすべてのワークブックが格納されている）またはローカルマシンから選択できます。ローカルドライブ上で <span class="filepath">.xls</span> 形式のワークブックを選択すると、そのファイルは <span class="filepath">.xlsx</span> に変換されます。変換の一環として、ファイルが Excel で開かれてアクティブになります。予定レポートで選択されているワークブックのファイル名が現在 Excel で開かれているワークブックと同じである場合、前にアップロードされたファイルではなく、ローカルファイルが選択されます。スケジュールリポジトリからレポートを選択する場合は、ワークブックのコピーがサーバー上に作成されます。その場合、ワークブックのファイル名は末尾に 1 を追加して更新されます。新規に作成された予定レポートはこのコピーされたワークブックを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタマイズ </p> </td> 
   <td colname="col2"> <p>日付形式をカスタマイズできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>宛先 </p> </td> 
   <td colname="col2"> <p>該当する場合、Outlook のアドレス帳を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>送信先：電子メール </p> </td> 
   <td colname="col2"> <p>レポート受信者の電子メール。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>送信先：発行リスト </p> </td> 
   <td colname="col2"> <p>この会社で使用可能な配信リストの一覧が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>詳しくは、<a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local">ワークブックを Microsoft Power BI に発行</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>件名 </p> </td> 
   <td colname="col2"> <p>メールの件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>スケジュール </p> </td> 
   <td colname="col2"> <p> レポートを送信するタイミングを指定します（即時、毎時、毎日、毎月、毎年から選択できます）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>「<b>スケジュール</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>配信時間 </p> </td> 
   <td colname="col2"> <p>レポートを今すぐ配信するか、任意の配信時間を指定します。タイムゾーンは変更できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>繰り返しパターン </p> </td> 
   <td colname="col2"> <p>繰り返す周期を指定します。。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>繰り返しの範囲 </p> </td> 
   <td colname="col2"> <p>レポートの配信を開始および停止するタイミングを指定します。 </p> <p> <p>注意：現在の期間（週、月、四半期、年）の最初の日にレポートをスケジュールすると、その期間の最初の日のみにデータが配信されます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「<b>ファイルオプション</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイル形式 </p> </td> 
   <td colname="col2"> <p>配信形式として、Excel 2007（<span class="filepath">.xlsx</span>）、Excel 2003（<span class="filepath">.xls</span>）、<span class="filepath">.pdf</span>、<span class="filepath">.csv</span>、<span class="filepath">.mht</span>、<span class="filepath">.txt</span> または <span class="filepath">.xml</span> を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ファイルの保存先 </p> </td> 
   <td colname="col2"> <p> 電子メールまたは FTP を指定します。ページのオプションは、選択内容よって異なります。FTP の場合、そのホストが外部からアクセス可能であることを確認する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>発行リスト </p> </td> 
   <td colname="col2"> <p> 予定レポートを複数の発行リストに対して送信する場合、各リストに対してレポートが一度実行されます。対象レポートスイートは、発行リストに割り当てられたレポートスイートに置き換えられます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルコンテンツの言語 </p> </td> 
   <td colname="col2"> <p>カバーレターに使用する言語を指定します。中国語（簡体または繁体）、ドイツ語、フランス語、日本語、韓国語、ポルトガル語（ブラジル）またはスペイン語を選択することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「<b>発行オプション</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI に発行中 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> ワークブックを Power BI に発行</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> すべての Report Builder リクエストを Power BI データセットテーブルとして発行</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> すべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>この Power BI レポートを次のようにラベル付けします。 </p> </td> 
   <td colname="col2"> <p>ラベルの詳細 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   [スケジュールされたタスクマネージャー](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31)に予定レポートが表示されます。
