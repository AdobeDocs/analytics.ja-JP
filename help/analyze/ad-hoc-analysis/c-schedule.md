---
description: レポートの配信スケジュールをカスタマイズできます。 特定の時間に配信を停止したり、レポートの送信回数を指定したりできます。 新しいスケジュールでは、レポートで定義された日付範囲が使用されます。 例えば、過去90日間のレポートを作成し、毎日実行するようにスケジュールした場合、最近90日間のレポートを毎日受信します。 カレンダーの静的な日付範囲を使用してレポートを作成すると、送信されるたびに同じレポートが表示されます。
title: 予定レポートマネージャー
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 予定レポートマネージャー

レポートの配信スケジュールをカスタマイズできます。 特定の時間に配信を停止したり、レポートの送信回数を指定したりできます。 新しいスケジュールでは、レポートで定義された日付範囲が使用されます。 例えば、過去90日間のレポートを作成し、毎日実行するようにスケジュールした場合、最近90日間のレポートを毎日受信します。 カレンダーの静的な日付範囲を使用してレポートを作成すると、送信されるたびに同じレポートが表示されます。

## 予定レポートマネージャー {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

レポートの配信スケジュールをカスタマイズできます。 特定の時間に配信を停止したり、レポートの送信回数を指定したりできます。 新しいスケジュールでは、レポートで定義された日付範囲が使用されます。 例えば、過去90日間のレポートを作成し、毎日実行するようにスケジュールした場合、最近90日間のレポートを毎日受信します。 カレンダーの静的な日付範囲を使用してレポートを作成すると、送信されるたびに同じレポートが表示されます。

>[!NOTE]ユーザーアカウントが無効になった場合、このユーザーによって作成された予定レポートの配信は中止されます。

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis では、状況に応じてタイミング良く特定のレポートを作成するニーズに対応することを目的として、すばやくレポートを定義してスケジュールを設定できるようになっています。大量の行、列、指標の評価、またはデータ抽出を使用した詳細な分類を含むデータの完全なエクスポート用に設計されていません。
>
>Ad Hoc分析でのスケジュール済みレポートの実用的な制約は、次の原則に基づいています。レポートが10分(アドホック分析のタイムアウト)以内に作成されない場合は、レポートが複雑すぎる可能性が高くなります。
>
>レポートに含まれる指標が多すぎる、ディメンション分析の分類が多すぎる、行や列が多すぎる、その他の極端な値が原因で、Ad Hocエレメントのレポート生成プロセスが長すぎる可能性が高い。 このタイプのレポートは、レポートの生成時にオフラインで実行されるフルデータ抽出用のAdobe Analytics機能であるData Warehouseで実行する必要があります。この機能は、数時間または数日かかる場合があります。
>
>例えば、アドホック分析は50,000行のデータを処理できますが、10種類のブラウザーのデータを分類すると50,000倍の10を意味し、アドホックレポートツールには複雑すぎる指数的増加を意味します。 さらに分類を追加すると、データの行が指数関数的に増加します。 アドホック分析のレポートを制限する実際の行、列および分類の定義は、厳密に定義することはできませんが、これらすべての要因の組み合わせです。

## レポートの配信スケジュールの設定 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

レポートの配信スケジュールを設定する手順を説明します。

<!-- 

t_schedule_delivery.xml

 -->

1. をクリック **[!UICONTROL Tools]**&#x200B;し、をクリックしま **[!UICONTROL Schedule Manager]**&#x200B;す。
1. で、 [!UICONTROL Schedule Manager]「 **[!UICONTROL New.]**

## 配信オプション - 定義 {#reference_CA49AC560258471AAE959BCA243F170C}

オプションの設定の配信です。

<!-- 

r_delivery_options.xml

 -->

現在選択されているレポートに表示される情報を、選択した形式で送信できます。 1回だけ送信するか、配信スケジュールを設定し、目的のファイル形式を指定できます。 デジタル署名を作成して送信し、ファイルが本物であることを受信者に保証できます。 ファイルを電子メールアドレスに送信したり、FTPサーバーにアップロードしたりできます。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フィールド </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名前 </p> </td> 
   <td colname="col2"> <p> このレポートの設定可能な名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>レポートIDが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ファイル形式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel:すべての画像を含むレポートをスプレッドシートに出力します。 Microsoft Excelで編集できます。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV:レポートをコンマ区切り値で出力します。 単純なテキストエディタ（メモ帳など）またはスプレッドシートエディタ（Excelなど）で編集できます。 画像を含まない。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF:レポートをポータブルドキュメント形式で出力します。 Adobe AcrobatまたはAdobe Readerで編集できず、表示も可能です。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML:レポートをハイパーテキストマークアップ言語の添付ファイルで出力します。 この形式は、ほとんどのWebサイトが構成する形式です。 HTMLコードに精通していない限り編集できません。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">単語：すべての画像を含むレポートをリッチテキスト形式で出力します。 Microsoft Wordまたはワードパッドで編集できます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> アドバンス </p> </td> 
   <td colname="col2"> <p> 詳しくは、<a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >アドバンスフォーマット設定</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルの保存先 </p> </td> 
   <td colname="col2"> <p>電子メール：電子メールで送信する設定。 </p> <p>FTP:FTPサーバーにアップロードするための設定です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポート範囲と配信スケジュール </p> </td> 
   <td colname="col2"> <p>レポートをいつ配信するかを指定します。 新しいスケジュールでは、レポートで定義された日付範囲が使用されます。 例えば、過去90日間のレポートを作成し、毎日実行するようにスケジュールした場合、最近90日間のレポートを毎日受信します。 カレンダーの静的な日付範囲を使用してレポートを作成すると、送信されるたびに同じレポートが表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## アドバンスフォーマット設定 - 定義 {#reference_F99B65BF7C9746638D8147EED147015B}

「アドバンスフォーマット設定」の設定の定義です。

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フィールド </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ファイル名 </p> </td> 
   <td colname="col2"> <p>ユーザー定義のファイル名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>filenameにIDを追加 </p> </td> 
   <td colname="col2"> <p>レポートIDをファイル名に自動的に追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ファイル名に日付を追加 </p> </td> 
   <td colname="col2"> <p> レポートの日付をファイル名に自動的に追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>言語 </p> </td> 
   <td colname="col2"> <p> レポートの言語を選択できます。 使用する言語に関係なく、次のいずれかの言語でレポートを送信できます。 </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">英語 </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">スペイン語 </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">簡体字中国語 </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">繁体字中国語 </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">フランス語 </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">ドイツ語 </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">日本語 </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">ポルトガル語 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>エンコード </p> </td> 
   <td colname="col2"> <p>エンコーディングタイプを指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> レポートを圧縮ファイルとして送信 </p> </td> 
   <td colname="col2"> <p> ファイルを圧縮します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>電子署名ファイルの送信 </p> </td> 
   <td colname="col2"> <p>電子メールと共に送信する電子署名を作成します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

