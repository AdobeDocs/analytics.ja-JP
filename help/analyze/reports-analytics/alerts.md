---
description: 'null'
seo-description: 'null'
seo-title: アラート
solution: Analytics
subtopic: アラート
title: アラート
topic: Reports and Analytics
uuid: e1333a9b- aba0-45b7- b7e6-46e06190db64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# アラート

## アラート {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

すべてのAdobe Analyticsの新しいアラートシステムとして、インテリジェントアラートを使用すると、アラートプレビューとルール貢献度を使用してアラートを作成および管理できます。次のことが可能です。

* 異常値（90％、95％または 99％ のしきい値、変化率、超過／未満）に基づいたアラートの構築。
* アラートがトリガーされる頻度のプレビュー。
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信。
* 1 つのアラートで複数の指標を示す「積み重ね」アラートの作成。

You can access this new Alerts system from **[!UICONTROL More]** &gt; **[!UICONTROL Alerts]** in any report in Reports &amp; Analytics.

詳しくは、Analysis Workspace ドキュメントの[インテリジェントアラート](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html)を参照してください。

## アラートの追加 {#task_51187E8BF19544DDA9EF2057E6F11D35}

Adobe Analytics にアラートを追加する手順を説明します。

<!-- 

t_add_an_alert.xml

 -->

**[!UICONTROL Analytics]** / **[!UICONTROL コンポーネント]** メニューの新しいアラートビルダーに移動します。ただし、Reports &amp; Analytics のレポート内からもアクセスできます。

1. Reports &amp; Analytics で、アラートを設定するレポートを開きます。
1. **[!UICONTROL その他]** /アラート **[!UICONTROL の追加をクリック]**&#x200B;します。
1. これによって、[新しいアラートビルダー](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html)が表示されます。

## 既存のアラートを表示または編集するには {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

タスクコンテキスト

1. **[!UICONTROL Analytics]** / **[!UICONTROL コンポーネント]** / **[!UICONTROL アラートに移動]**&#x200B;します。これによって、[新しいアラートビルダー](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html)が表示されます。

## レガシーアラートの移行 {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

既存の Analytics アラートのいくつかの機能は、2016 年秋に（Analysis Workspace の一部として）リリースされる新しいアラートマネージャーには含まれません。次の表には、廃止されるアラート機能と、異なる形式で新しいアラートマネージャーに移行される一部のアラート機能が記載されています。

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> レガシーアラートの機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 廃止または移行のどちらか </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>合計（すべての項目） </p> </td> 
   <td colname="col2"> <p>ディメンションレポートのすべての項目にアラートを作成します。 </p> </td> 
   <td colname="col3"> <p>場合によっては、ディメンションレポートのすべての項目にアラートを作成しても、単独で集計された指標にのみアラートを設定しても（ディメンションには適用しない）、同じ結果になります。例えば、「売上高」指標のすべての項目の毎月のアラートを作成するとします。単に売上高レポートを実行するのと、毎月のアラートを設定するのとで、同じ結果が得られます。 </p> <p>この場合、レガシーの合計（すべての項目）アラートは使用できなくなり、後者の、よりシンプルなバージョンに移行されます。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上位 1000 項目 </p> <p> </p> </td> 
   <td colname="col2"> <p>レポートの上位 1000 項目に関するアラートを作成します。 </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間ベースの実訪問者数アラート（毎日、毎週、毎月などの実訪問者数） </p> <p> </p> </td> 
   <td colname="col2"> <p>1 時間ごと、毎日、毎週、毎月の実訪問者数レポートに関するアラートを作成します。 </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは、こうした時間ベースの実訪問者数アラートは、サポートされなくなります。例えば、以前、日別訪問者数に関する毎週のアラートを設定していても、発行される実訪問者数指標に毎日、毎週などのアラートを設定できます（Analysis Workspace は、実訪問者数指標をサポートしますが、毎日／毎週／毎月などの実訪問者数指標はサポートしません）。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>検索 </p> </td> 
   <td colname="col2"> <p>検索が適用されたディメンションレポートに関するアラートを作成します。「合計（すべての項目）」または「上位 1000 項目」にのみ適用されます。 </p> <p> </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics に特有のレポート </p> </td> 
   <td colname="col2"> <p>次のような、Reports &amp; Analytics に存在し、Analysis Workspace レポートに対応しないいくつかのレポートに関するアラートを作成します。 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">パスの長さ </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">ボット </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">タイムゾーン </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">トップレベルドメイン </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ASI スロットをレポートスイートとして使用するアラート </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html" format="https" scope="external">ASI スロットを作成または編集</a>できなくなっており、Analysis Workspace で使用できません。従って、新しいアラートでサポートされません。 </p> <p> </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パーティシペーション指標を使用したアラート </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html" format="https" scope="external">パーティシペーション指標</a>は、Reports &amp; Analytics で使用できますが、Analysis Workspace の新しいアラートシステムでは、現在、使用できません。 </p> <p> </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムカレンダーレポートスイート用の毎月のアラート </p> </td> 
   <td colname="col2"> <p>これは、<a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html" format="https" scope="external">カスタムの月の開始日</a>（全米小売業協会／NRF およびカスタムカレンダータイプ）を含むレポートスイートに関するアラートを設定しているお客様にのみ影響します。 </p> <p>グレゴリオ暦または修正グレゴリオ暦カレンダーのレポートスイートに関するアラートには影響しません。以前は、これらのアラートは、グレゴリオ暦の月の最初の日（例：1 月 1 日、2 月 1 日など）に送信されていました。これは、異常値を検出する際に以前の月のデータを考慮する、アラートの新しい異常値検出機能では動作しません。将来は、カスタムカレンダーのスケジュールシステムのサポートを追加し、アラートおよびスケジュールされたプロジェクトの両方で、グレゴリオ暦の月の最初の日でなく、カスタムカレンダーの月の最初の日に送信するようにスケジュールできるようになります。 </p> <p> </p> </td> 
   <td colname="col3"> <p>新しいアラートマネージャーでは、まだ使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2015 年 9 月以降、実行していないアラート </p> </td> 
   <td colname="col2"> <p>2015 年 9 月以降にアラートが実行されていないのには、次を含め、いくつかの理由があります。 </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">アラートマネージャーでアラートの「無効にする」をクリックした。 </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">アラートにエラーが発生し、正常に完了していない。 </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> これらのアラートは、新しいシステムに移行されません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 「無効」とマークされたアラート </td> 
   <td colname="col2"> この機能を追加する予定はありますが、現在、新しいユーザーインターフェイスではアラートを無効にする／再度有効にする方法がありません。 <p> </p> </td> 
   <td colname="col3"> これらのアラートは、新しいシステムに移行されません。 </td> 
  </tr> 
 </tbody> 
</table>

