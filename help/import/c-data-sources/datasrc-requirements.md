---
description: データソース使用前のレポートスイートに対する要件についての情報です。
subtopic: Data sources
title: 要件とアップロードに関する制限
topic: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 98%

---


# 要件とアップロードに関する制限

データソース使用前のレポートスイートに対する要件についての情報です。

以下の節では、データソース、およびマーケティングレポートにインポートするデータに適用される制約を示します。

* [サイズ制限](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [日付](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [一般](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [2 バイト文字のサポート](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Web ログファイルのアップロード](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## サイズ制限 {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* それぞれの FTP アカウントでは、全ファイルの合計データサイズが 50 MB に制限されます。データサイズが 50 MB を超えると処理が一時停止し、合計 50 MB 未満になるまで再開しません。

## 日付  {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* カレンダーの日ごとに、90 日分までの一意の日付のデータをアップロードできます。この制限を超えた場合、固有の最大日数を超えたというエラーメッセージが表示されてアップロードに失敗します。
* 現在または過去の日付があるデータのみをインポートできます。データソースのデータには未来の日付を使用しないでください。
* レポートのグラフ機能を有効にするために、すべての行に日付を指定する必要があります。日付を含まない行がある場合、データソースでエラーが発生しファイルが拒否されます。日付および時刻のフォーマットは、データソースのタイプによって次のように異なります。

   * **フル処理データソース**&#x200B;では、`YYYY-MM-DDThh:mm:ss±UTC_offset` という ISO 8601 の日付フォーマット（例：`2013-09-01T12:00:00-07:00`）、または Unix の時刻フォーマット（1970 年 1 月 1 日から経過した秒数）を使用します。

   * **標準および統合データソース**&#x200B;では、`MM/DD/YYYY/HH/mm/SS` の日付フォーマットを使用します（例：`01/01/2013/06/00/00`）。

## 一般 {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* データソースファイルをアップロードすると、データソースによって基本的なデータ検証が実行され、ファイルにフォーマットエラーがないことが確認されます。ファイルにエラーが見つかった場合、電子メール通知が送信され、処理が停止します。
* データフィールドにセミコロンを含めることはできません。セミコロンを含むレコードはスキップされます。
* Web ログ、トラフィック、および一部の汎用データソースのグループは、Data Warehouse や Discover で使用できません。詳しくは、[データのタイプとカテゴリ](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md)を参照してください。
* データソースは、シリアル化されたイベントをサポートしません。

## 2 バイト文字のサポート {#section_96C8D26B21184C3E839865DB6F23EA22}

データソースでは、2 バイト文字のエンコーディングがサポートされます。受信されるデータソースファイルのフォーマット検出が行われ、必要な場合、サポートされるフォーマットに変換します。次の表に、一般的な文字フォーマットとそのサポート状況を示します。

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文字フォーマット </th> 
   <th colname="col2" class="entry"> サポート </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>サポート対象。データソースで使用されるレポートスイートでは、2 バイト文字のサポートを有効にする必要があります。 </p> <p>ヘルプの「<a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html"  >新しいレポートスイート</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> バイトオーダーマーク付きの UTF-8（EF BB BF） </td> 
   <td colname="col2"> <p>サポート対象。このフォーマットは標準ではありませんが、多くの Windows アプリケーションでの保存時にこのフォーマットが使用されます。 </p> <p>例えば、ワードパッドで「UTF-8」を選択すると、このフォーマットで保存されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1（Latin-1 または Windows-1252） </td> 
   <td colname="col2"> サポート対象。Microsoft Excel で「タブ区切り」のエクスポートを選択すると、このフォーマットで保存されます。レポートスイートでは ISO-8859-1 のロケールを使用する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> バイトオーダーマーク付きの UTF-16 リトルエンディアン（FF FE） </td> 
   <td colname="col2"> ISO-8859-1 または UTF-8（レポートスイートの設定による）に変換されます。Unicode のエクスポートを選択すると、Microsoft Excel ではこのフォーマットで保存されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> バイトオーダーマーク付きの UTF-16 ビッグエンディアン（EF FF） </td> 
   <td colname="col2"> ISO-8859-1 または UTF-8（レポートスイートの設定による）に変換されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> バイトオーダーマークなしの UTF-16 </td> 
   <td colname="col2"> サポート対象外。 </td> 
  </tr> 
 </tbody> 
</table>

UTF-8 または ISO-8859-1 のファイルを送信し、レポートスイートでこれらのサポートが設定されていない場合は、次のうちいずれかが発生します。

* コンバージョン時にエラーが検出され、「UTF-8 から ISO-8859-1 への変換中、ファイル内の場所 18 に不正な文字が見つかりました」のようなメッセージが表示されます。
* ファイルはエラーなしで処理されますが、レポートには文字化けしたデータが表示されます。

## Web ログファイルのアップロード  {#section_DD736FC971FE45C89AB310BEDC1FE707}

* Web ログデータの表示が最も有効なレポートは、ページビュー数などのトラフィックレポートです。
* ページ名は、完全な URL として表示され、クエリ文字列を含みます。
* それぞれのファイル要求は、個別のページビューとして表示され、スタイルシートや画像ファイルを含みます。
* URL に情報を付加すると、ファイルが個別のページとして記録されることがあります。例えば、次のURLはAdobeで2つの個別のページとして記録されます。

`/jokes/misc/snail_joke.html?userid=12345`

`/jokes/misc/snail_joke.html?userid=98765`
