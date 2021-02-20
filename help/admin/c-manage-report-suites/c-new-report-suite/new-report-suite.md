---
description: 新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。
title: 新しいレポートスイート - 設定
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 94%

---


# 新しいレポートスイート - 設定

新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。

エレメントの説明（[レポートスイートの作成時](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)で使用されます）。

>[!NOTE]
>
>仮想レポートスイートの作成方法について詳しくは、[仮想レポートスイートのドキュメント](/help/components/vrs/c-workflow-vrs/vrs-create.md)を参照してください。

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
   <td colname="col2"> <p>英数字文字のみ含めることができる一意な ID を指定します。この ID は作成後は変更できません。アドビによって設定される必須の ID プレフィックスも変更できません。 </p> <p>複数のレポートスイートを作成する場合は、レポートスイート ID が一意になる命名方法を使用してください。 </p> </td> 
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
   <td colname="col2"> （オプション）レポートスイートのベースドメインを定義します。レポートスイートの内部 URL フィルターを明示的に定義していない場合、この URL が内部 URL フィルターとして機能します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> デフォルトのページ</span> </td> 
   <td colname="col2"> <p>（オプション）<span class="wintitle">デフォルトのページ</span>値がある場合、それは URL から削除されます。<span class="wintitle">最頻訪問ページ</span>レポートにページ名ではなく URL がある場合に、この設定によって同じ Web ページが複数の URL で表されることを防止できます。 </p> <p>例えば、URL<span class="filepath"> https://example.com</span>と<span class="filepath"> https://example.com/index.html</span>は通常同じページです。 不要なファイル名を削除できるので、これらのURLは共に<span class="filepath"> https://example.com</span>としてレポートに表示されます。 </p> <p>この値を設定しない場合、Analytics は URL から以下のファイル名を自動的に削除します。<span class="filepath"> index.htm</span>、<span class="filepath"> index.html</span>、<span class="filepath"> index.cgi</span>、<span class="filepath"> index.asp</span>、<span class="filepath"> default.htm</span>、<span class="filepath"> default.html</span>、<span class="filepath"> default.cgi</span>、<span class="filepath"> default.asp</span>、<span class="filepath"> home.htm</span>、<span class="filepath"> home.html</span>、<span class="filepath"> home.cgi</span>、および <span class="filepath"> home.asp</span>。 </p> <p>ファイル名の削除を無効にするには、URL に決して存在しないデフォルトのページ値を入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live 日 </p> </td> 
   <td colname="col2">このレポートスイートがアクティブになると予想される日をアドビに知らせます。デプロイメントスケジュールを変更する場合、<a href="/help/admin/c-traffic-management/traffic-management.md">トラフィック管理</a>にある<span class="wintitle">恒久的なトラフィック</span>ツールを使って更新したトラフィックの予想値を入力します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 予想日別ページビュー数</span> </td> 
   <td colname="col2"> このレポートスイートが 1 日にサポートすると予想されるページビュー数を特定します。トラフィックの量が多いと承認プロセスに時間がかかります。処理の遅延を防ぐために、この予測値はできる限り正確なものにしてください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基準通貨</span> </td> 
   <td colname="col2"> <p>すべての通貨データの保存に使用するデフォルトの通貨を指定します。Analytics はデータを受け取った時点での為替レートを使用して、別の通貨のトランザクションをベース通貨に変換します。 </p> <p> Analytics レポーティングでは、<span class="varname"> currencyCode</span> JavaScript 変数を使用して、特定のトランザクションの通貨を特定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">2 バイト文字サポートの無効化</span> </td> 
   <td colname="col2"> <p>レポートスイートのマルチバイト文字サポートを無効にします。マルチバイト文字のサポートが無効になっている場合、システムはデータを ISO-8859-1 形式であると想定します。Web ページの文字セットは、<span class="varname"> charSet</span> JavaScript 変数で設定する必要があります。 </p> <p>マルチバイト文字のサポートでは、UTF-8 を使用してレポートスイートに文字が保存されます。この要求を受けると、Web ページの文字セットから UTF-8 文字セットにデータが変換されて、マーケティングレポートで任意の言語を使用できるようになります。 </p> <p>既存のレポートスイートのマルチバイト文字サポートを変更する場合は、担当のアカウントマネージャーまたはカスタマーケアにお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> このスイートの Ad Hoc Analysis をアクティブにする</span> </td> 
   <td colname="col2"> ad hoc analysis の実行時にこのレポートスイートを表示できるようにします。 </td> 
  </tr> 
 </tbody> 
</table>

