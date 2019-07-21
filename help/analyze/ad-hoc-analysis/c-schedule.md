---
description: レポートの配信スケジュールをカスタマイズできます。特定の時間に配信を中止したり、レポートの送信回数を指定したりできます。スケジュールされたレポートでは、レポートで定義されている日付範囲が使用されます。例えば、最近 90 日間のレポートを作成し、このレポートを毎日実行するように設定した場合、最近 90 日間のレポートを毎日受信することになります。カレンダーで静的に日付範囲を指定してレポートを作成すると、送信されるたびに同じレポートが表示されます。
seo-description: レポートの配信スケジュールをカスタマイズできます。特定の時間に配信を中止したり、レポートの送信回数を指定したりできます。スケジュールされたレポートでは、レポートで定義されている日付範囲が使用されます。例えば、最近 90 日間のレポートを作成し、このレポートを毎日実行するように設定した場合、最近 90 日間のレポートを毎日受信することになります。カレンダーで静的に日付範囲を指定してレポートを作成すると、送信されるたびに同じレポートが表示されます。
seo-title: 予定レポートマネージャー
solution: Analytics
title: 予定レポートマネージャー
topic: Ad Hoc Analysis
uuid: 82a054ef-109d-414d- a6e1- e09ee57c163f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 予定レポートマネージャー

レポートの配信スケジュールをカスタマイズできます。特定の時間に配信を中止したり、レポートの送信回数を指定したりできます。スケジュールされたレポートでは、レポートで定義されている日付範囲が使用されます。例えば、最近 90 日間のレポートを作成し、このレポートを毎日実行するように設定した場合、最近 90 日間のレポートを毎日受信することになります。カレンダーで静的に日付範囲を指定してレポートを作成すると、送信されるたびに同じレポートが表示されます。

## 予定レポートマネージャー {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

レポートの配信スケジュールをカスタマイズできます。特定の時間に配信を中止したり、レポートの送信回数を指定したりできます。スケジュールされたレポートでは、レポートで定義されている日付範囲が使用されます。例えば、最近 90 日間のレポートを作成し、このレポートを毎日実行するように設定した場合、最近 90 日間のレポートを毎日受信することになります。カレンダーで静的に日付範囲を指定してレポートを作成すると、送信されるたびに同じレポートが表示されます。

>[!NOTE]
>
>ユーザーアカウントが無効になっている場合、そのユーザーによって作成されたスケジュール済みレポートの配信は中止されます。

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](../../analyze/ad-hoc-analysis/c-tablebuilder.md#concept_664FC77306E148DBA4EA081814943C5E) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysisを使用すると、特定のタイムリーでアドホックなレポートニーズに関するレポートをすばやく定義およびスケジュールできます。データ抽出機能を使用し、行、列、指標の評価結果または詳細な分類に関する情報が大量に含まれるデータをすべてエクスポートするような処理には、対応する設計になっていません。
>
>「レポートの作成が 10 分以内に（Ad Hoc Analysis のタイムアウトまでに）終わらないようなら、レポートが複雑すぎる可能性が高い」という原則が、Ad Hoc Analysis のスケジュールを使用したレポート作成機能の現実的な制約になります。
>
>指標が多すぎたり、ディメンション要素の分類が多すぎたり、行または列が多すぎたりするなど、レポートに Ad Hoc Analysis のレポート生成プロセスが長くなりすぎる原因となる異常値が存在することは多いと考えられます。このようなレポートの場合は、Adobe Analytics の機能の 1 つ、Data Warehouse で作成する必要があります。この機能は、何時間または何日にも及ぶ時間をかけてオフラインで全データを抽出してレポートを生成するためのものです。
>
>例えば、Ad Hoc Analysis では 50,000 行のデータを処理できるものの、そのデータを 10 種類のブラウザーに対応するように分類していくと、行数が 50,000 の 10 倍に増えることになるので、アドホックのレポートツールには複雑すぎるほどの量になると考えられます。分類をさらに追加した場合には、データの行数がその分だけ急激に増えていきます。Ad Hoc Analysis のレポート作成機能にとって制約となる行、列および分類の実際の数は、ここで説明した様々な要素すべてが組み合わさって決まるものなので、厳密に確定することはできません。

## レポートの配信スケジュールの設定 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

レポートの配信スケジュールを設定する手順を説明します。

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. 「[!UICONTROL 予定レポートマネージャー]**」で、「[!UICONTROL 新規]」をクリックします。**

## 配信オプション - 定義 {#reference_CA49AC560258471AAE959BCA243F170C}

配信オプション設定での定義について説明します。

<!-- 

r_delivery_options.xml

 -->

現在選択されているレポートに表示されている情報を、選択した形式で送信できます。この情報を 1 回だけ送信したり、配信スケジュールを設定したりできます。また、ファイル形式を指定することもできます。信頼性のあるファイルであることを受信者に示すために、デジタル署名を作成して送信できます。ファイルは電子メールアドレスに送信するか、FTP サーバーにアップロードすることができます。

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
   <td colname="col2"> <p> このレポートの名前を設定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>レポート ID が示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ファイル形式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel：レポートをスプレッドシート形式で出力します。画像もすべて含まれます。Microsoft Excel で編集できます。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV：レポートをコンマ区切りの値（CSV）で出力します。単純なテキストエディター（メモ帳など）や、スプレッドシートエディター（Excel など）で編集できます。画像は含まれません。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF：レポートをポータブルドキュメントフォーマット（PDF）で出力します。編集不可能で、Adobe Acrobat または Adobe Reader で閲覧できます。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML：レポートをハイパーテキストマークアップ言語（HTML）形式で出力します。この形式は、多くの Web サイトを構成している形式です。HTML コードに精通していなければ編集できません。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word：レポートをリッチテキスト形式（RTF）で出力します。画像もすべて含まれます。Microsoft Word またはワードパッドで編集できます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> アドバンス </p> </td> 
   <td colname="col2"> <p> See <a href="../../analyze/ad-hoc-analysis/c-schedule.md#reference_F99B65BF7C9746638D8147EED147015B" type="reference" format="dita" scope="local"> Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルの保存先 </p> </td> 
   <td colname="col2"> <p>電子メール：電子メールで送信するための設定です。 </p> <p>FTP：FTP サーバーにアップロードする場合の設定です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポート範囲および配信スケジュール </p> </td> 
   <td colname="col2"> <p>レポートをいつ配信するかを指定します。スケジュールされたレポートでは、レポートで定義されている日付範囲が使用されます。例えば、最近 90 日間のレポートを作成し、このレポートを毎日実行するように設定した場合、最近 90 日間のレポートを毎日受信することになります。カレンダーで静的に日付範囲を指定してレポートを作成すると、送信されるたびに同じレポートが表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## アドバンスフォーマット設定 - 定義 {#reference_F99B65BF7C9746638D8147EED147015B}

アドバンスフォーマット設定での定義について説明します。

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
   <td colname="col2"> <p>ユーザー定義のファイル名です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>filename に ID を付加する </p> </td> 
   <td colname="col2"> <p>自動的にファイル名にレポート ID を追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> filename に日付を付加する </p> </td> 
   <td colname="col2"> <p> 自動的にファイル名にレポートの日付を追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>言語 </p> </td> 
   <td colname="col2"> <p> レポートの言語を選択できます。使用されている言語に関係なく、次のいずれかの言語でレポートを送信できます。 </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">英語 </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">スペイン語 </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">簡体中国語 </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">繁体中国語 </li> 
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
   <td colname="col1"> <p>デジタル署名ファイルの送信 </p> </td> 
   <td colname="col2"> <p>デジタル署名を作成し、電子メールと共に送信します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

