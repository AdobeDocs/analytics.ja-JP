---
description: 新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。
title: 新しいレポートスイート - 設定
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 新しいレポートスイート - 設定

新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。

エレメントの説明（[レポートスイートの作成時](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)で使用されます）。

>[!NOTE]仮想レポートスイートの作成方法について詳しくは、[仮想レポートスイートのドキュメント](/help/components/vrs/c-workflow-vrs/vrs-create.md)を参照してください。

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">レポートスイート ID</span> </td> 
   <td colname="col2"> <p>英数字のみを含む一意のIDを指定します。 このIDは、作成後は変更できません。 アドビは必要なIDプレフィックスを設定し、変更することもできません。 </p> <p>複数のレポートスイートを作成する場合は、レポートスイート ID が一意になる命名方法を使用してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">サイトのタイトル</span> </td> 
   <td colname="col2"><span class="wintitle">管理ツール</span>のレポートスイートを識別します。このタイトルは、スイートのヘッダーにある<span class="wintitle">レポートスイート</span>ドロップダウンリストでも使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">タイムゾーン</span> </td> 
   <td colname="col2"> イベントおよびタイムスタンプのデータをスケジュールします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">ベース URL</span> </td> 
   <td colname="col2"> （オプション）レポートスイートのベースドメインを定義します。 レポートスイートの内部URLフィルターを明示的に定義しない場合、このURLは内部URLフィルターとして機能します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> デフォルトのページ</span> </td> 
   <td colname="col2"> <p>（オプション）<span class="wintitle">デフォルトのページ</span>値がある場合、それは URL から削除されます。<span class="wintitle">最頻訪問ページ</span>レポートにページ名ではなく URL がある場合に、この設定によって同じ Web ページが複数の URL で表されることを防止できます。 </p> <p>例えば、<span class="filepath">https://mysite.com</span> と <span class="filepath">https://mysite.com/index.html</span> という URL では、通常同じページが表示されます。不要なファイル名を削除できるので、これらの URL は共にレポートで <span class="filepath">https://mysite.com</span> として表示されます。 </p> <p>この値を設定しない場合、Analytics は URL から以下のファイル名を自動的に削除します。<span class="filepath"> index.htm</span>、<span class="filepath"> index.html</span>、<span class="filepath"> index.cgi</span>、<span class="filepath"> index.asp</span>、<span class="filepath"> default.htm</span>、<span class="filepath"> default.html</span>、<span class="filepath"> default.cgi</span>、<span class="filepath"> default.asp</span>、<span class="filepath"> home.htm</span>、<span class="filepath"> home.html</span>、<span class="filepath"> home.cgi</span>、および <span class="filepath"> home.asp</span>。 </p> <p>ファイル名の削除を無効にするには、URLに決して存在しないデフォルトのページ値を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live日 </p> </td> 
   <td colname="col2">このレポートスイートがアクティブになると予想される日をアドビに知らせます。 デプロイメントスケジュールを変更する場合、<a href="/help/admin/c-traffic-management/traffic-management.md">トラフィック管理</a>にある<span class="wintitle">恒久的なトラフィック</span>ツールを使って更新したトラフィックの予想値を入力します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 予想日別ページビュー数</span> </td> 
   <td colname="col2"> このレポートスイートが1日にサポートすると予想される表示のページ数を特定します。 トラフィック量が多い場合は、承認プロセスに時間がかかります。 処理の遅延を避けるには、この推定値をできるだけ正確に指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基準通貨</span> </td> 
   <td colname="col2"> <p>すべての通貨データの保存に使用するデフォルトの通貨を指定します。 Analyticsレポートは、データを受け取った時点の現在のコンバージョン率を使用して、他の通貨のトランザクションをベース通貨に変換します。 </p> <p> Analyticsレポートは、currencyCode <span class="varname"></span> JavaScript変数を使用して、特定のトランザクションの通貨を識別します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">2 バイト文字サポートの無効化</span> </td> 
   <td colname="col2"> <p>レポートスイートのマルチバイト文字サポートを無効にします。 マルチバイト文字のサポートを無効にした場合、システムはデータがISO-8859-1形式であると想定します。 Webページの文字セットは、 <span class="varname"> charSet</span> JavaScript変数で指定する必要があります。 </p> <p>マルチバイト文字のサポートでは、文字がUTF-8を使用してレポートスイートに保存されます。 この要求を受けると、Webページの文字セットからUTF-8文字セットにデータが変換され、マーケティングレポートで任意の言語を使用できるようになります。 </p> <p>既存のレポートスイートのマルチバイト文字サポートを変更する場合は、担当のアカウントマネージャーまたはカスタマーケアにお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> このスイートの Ad Hoc Analysis をアクティブにする</span> </td> 
   <td colname="col2"> ad hoc analysis の実行時にこのレポートスイートを表示できるようにします。 </td> 
  </tr> 
 </tbody> 
</table>

