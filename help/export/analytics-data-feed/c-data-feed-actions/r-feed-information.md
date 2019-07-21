---
description: 「フィード情報」セクションを使用して、フィードに名前を付けたり、フィードを実行するレポートスイート、フィードの繰り返し、フィードの開始と終了のタイミングを指定したりできます。
keywords: データフィード;情報;name;レポートスイート;email、complete、email;interval;フィード;処理の遅延;delay;start;end;date;連続フィード
seo-description: 「フィード情報」セクションを使用して、フィードに名前を付けたり、フィードを実行するレポートスイート、フィードの繰り返し、フィードの開始と終了のタイミングを指定したりできます。
seo-title: フィード情報
solution: Analytics
title: フィード情報
uuid: adf92f42- a957-4de0- a5a1-683f2933af04
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# フィード情報

「フィード情報」セクションを使用して、フィードに名前を付けたり、フィードを実行するレポートスイート、フィードの繰り返し、フィードの開始と終了のタイミングを指定したりできます。

![](assets/feed-info.jpg)

<table id="table_C98C7C3CE4194BEF819E792793EBC517">
 <thead>
  <tr>
   <th colname="col1" class="entry"> フィールド </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名前（必須） </p> </td>
   <td colname="col2"> <p>フィード名を入力します。 </p> <p>名前は、選択したレポートスイート内で一意である必要があり、最大 255 文字まで設定できます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>レポートスイート（必須） </p> </td>
   <td colname="col2"> <p>フィードクエリ用のレポートスイートを指定します。 </p> <p>少なくとも 1 つのレポートスイートを選択する必要があります。同じレポートスイートを 2 回リストすることはできません。 </p> <p>ログインしているユーザーが使用できる仮想レポートスイートはすべて使用できます。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>完了時に電子メールを送信（必須） </p> </td>
   <td colname="col2"> <p>フィード配信の更新を受け取る電子メール受信者を指定します。 </p> <p>このフィールドは空にできません。適切な形式の電子メールアドレスを含める必要があります。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>フィード間隔（必須） </p> </td>
   <td colname="col2"> <p>スケジュールの繰り返しを指定します。 </p> <p>注意：データフィード zip ファイルの潜在的なサイズに起因して、ETL プロセスが 64 ビット zip ユーティリティを使用していることを確認してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>遅延処理（オプション） </p> </td>
   <td colname="col2"> <p>各スケジュールインスタンスに適用する遅延を指定します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>開始日と終了日（必須） </p> <p>連続フィード（オプション） </p> </td>
   <td colname="col2"> <p>フィードを開始および終了する日付をスケジュールします。 </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">開始日：デフォルトは今日の日付です。 </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">終了日：デフォルトは明日の日付です。 </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>