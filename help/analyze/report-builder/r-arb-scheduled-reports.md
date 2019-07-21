---
description: スケジュールされたタスクマネージャーのフィールドの説明です。
seo-description: スケジュールされたタスクマネージャーのフィールドの説明です。
seo-title: スケジュールされたタスクマネージャー
solution: Analytics
title: スケジュールされたタスクマネージャー
topic: Report Builder
uuid: jec259f0-2a04-4c94- abbc-5008cf2f1cb8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# スケジュールされたタスクマネージャー

スケジュールされたタスクマネージャーのフィールドの説明です。

スケジュールされたタスクマネージャーでは、受信者、スケジュールの詳細、ファイル形式と共に、既存の予定レポートのリストを表示できます。また、実行に失敗したスケジュール済みワークブックを再開することもできます。

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>「<b>予定レポート</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポート名 </p> </td> 
   <td colname="col2"> <p>スケジュールされているタスクの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 電子メール / FTP </p> </td> 
   <td colname="col2"> <p>受信者の電子メールアドレスまたは FTP アドレス。 </p> <p>注意：電子メールを選択すると、1 MB を超えるレポートは自動的に .zip ファイルとして電子メールに添付されます。この機能によって、添付ファイルのサイズを小さく保つことができます。この機能は無効にできません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>発行オプション </p> </td> 
   <td colname="col2"> <p>いずれかの <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#concept_0C4105AA10F9460A872C2489C9CD7945" format="dita" scope="local">Power BI 発行オプション</a>が選択されている場合、この列に Power BI が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>スケジュール </p> </td> 
   <td colname="col2"> <p>スケジュールされた配信のタイプ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ファイル形式 </p> </td> 
   <td colname="col2"> <p> Excel、PDF、HTML などのレポートの配信形式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>再開 </p> </td> 
   <td colname="col2"> <p>スケジュールされているワークブックの実行が失敗した場合、Report Builder では 15 分ごとにさらに 2 度ワークブックの実行を試みます。3 回実行が失敗すると、スケジュールが無効になり、「<span class="wintitle">再開</span>」ボタンが表示されます。ワークブックを再開すると、スケジュールされた配信が無効になった時刻から再開されます。 </p> <p>例えば、スケジュールされているワークブックが 14 日前に無効になっており、今日再開すると、実行されなかったすべての日に対して配信が実行されるため、14 回配信されることになります。配信が実行されなかった日に対してワークブックの配信を行わないようにするためには、スケジュールされたワークブックを削除してから、新しくスケジュールされたワークブックを作成します。 </p> <p> <p>注意：なぜシステム上でワークブックが無効になったかを把握していない場合は、ワークブックを再開しないでください。トラブルシューティングの際には、無効になったワークブックをダウンロードしてクライアント側で更新し、エラーが表示されなければワークブックを再開できると判断する、という方法が考えられます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最後の送信 </p> </td> 
   <td colname="col2"> <p>レポートが最後に送信された日時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「<b>受信者</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>受信者の電子メール </p> </td> 
   <td colname="col2"> レポート受信者の電子メール。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポート </p> </td> 
   <td colname="col2"> 各受信者に送信されたレポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「<b>レポートの履歴</b>」タブ </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイル名 </p> </td> 
   <td colname="col2"> スケジュールされているタスクの名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付 </p> </td> 
   <td colname="col2"> レポートが最後に送信された日時。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> レポートが送信されたかどうかを示すステータス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>電子メール / FTP </p> </td> 
   <td colname="col2"> レポートの受信者の電子メールアドレスまたは FTP アドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイル形式 </p> </td> 
   <td colname="col2"> Excel、PDF、HTML などのレポートの配信形式。 </td> 
  </tr> 
 </tbody> 
</table>
