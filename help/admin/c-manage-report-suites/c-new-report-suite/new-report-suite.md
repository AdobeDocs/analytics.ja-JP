---
description: 新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。
seo-description: 新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。
seo-title: 新しいレポートスイート-設定
solution: Analytics
title: 新しいレポートスイート-設定
topic: 管理ツール
uuid: 3508f684-11a3-4c8f- a233- bea6bafd57c0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 新しいレポートスイート-設定

新しいレポートスイートを作成するには、事前定義済みのテンプレートを選択するか、モデルとなる既存のレポートスイートを 1 つ選択して使用します。

使用する要素の説明[レポートスイートの作成時](../../../admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md#task_67033B9710CB49F9B71A4DE374A538A0)に使用されるエレメントの説明。

>[!NOTE]
>
>The [Virtual Report Suite documentation](/help/components/vrs/c-workflow-vrs/vrs-create.md) shows you how to create virtual report suites.

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
   <td colname="col1"> <span class="wintitle"> サイトのタイトル</span> </td> 
   <td colname="col2"><span class="wintitle">管理ツール</span>のレポートスイートを識別します。このタイトルは、スイートのヘッダーにある<span class="wintitle">レポートスイート</span>ドロップダウンリストでも使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> タイムゾーン</span> </td> 
   <td colname="col2"> イベントおよびタイムスタンプのデータをスケジュールします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base URL</span> </td> 
   <td colname="col2"> （オプション）レポートスイートのベースドメインを定義します。レポートスイートの内部 URL フィルターを明示的に定義していない場合、この URL が内部 URL フィルターとして機能します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> デフォルトのページ</span> </td> 
   <td colname="col2"> <p>（オプション）<span class="wintitle">デフォルトのページ</span>値がある場合、それは URL から削除されます。<span class="wintitle">最頻訪問ページ</span>レポートにページ名ではなく URL がある場合に、この設定によって同じ Web ページが複数の URL で表されることを防止できます。 </p> <p>For example, the URLs<span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove extraneous filenames so that both these URLs show up as <span class="filepath"> https://mysite.com</span> in your reports. </p> <p>この値を設定しない場合、Analytics は URL から以下のファイル名を自動的に削除します。<span class="filepath">index.htm</span>、 <span class="filepath">index.html</span>、 <span class="filepath">index.cgi</span>、 <span class="filepath">index.asp</span>、 <span class="filepath">default.htm</span>、 <span class="filepath">default.html</span>、 <span class="filepath">default.cgi</span>、 <span class="filepath">default.asp</span>、 <span class="filepath">home.htm</span>、 <span class="filepath">home.html</span>、 <span class="filepath">home.cgi</span> および<span class="filepath">home.asp</span>。 </p> <p>ファイル名の削除を無効にするには、URL に決して存在しないデフォルトのページ値を入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live 日 </p> </td> 
   <td colname="col2">このレポートスイートがアクティブになると予想される日をアドビに知らせます。If your deployment schedule changes, provide an updated traffic estimate using the <span class="wintitle"> Permanent Expected Traffic</span> tool in <a href="../../../admin/c-traffic-management/traffic-management.md#concept_8BD651EE8B84434CB4D6308BC6C01B79" format="dita" scope="local"> Traffic Management</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 予想日別ページビュー数</span> </td> 
   <td colname="col2"> このレポートスイートが 1 日にサポートすると予想されるページビュー数を特定します。トラフィックの量が多いと承認プロセスに時間がかかります。処理の遅延を防ぐために、この予測値はできる限り正確なものにしてください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基準通貨</span> </td> 
   <td colname="col2"> <p>すべての通貨データの保存に使用するデフォルトの通貨を指定します。Analytics はデータを受け取った時点での為替レートを使用して、別の通貨のトランザクションをベース通貨に変換します。 </p> <p> Analytics レポーティングでは、<span class="varname"> currencyCode</span> JavaScript変数を使用して、特定のトランザクションの通貨を特定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">2 バイト文字サポートの無効化</span> </td> 
   <td colname="col2"> <p>レポートスイートのマルチバイト文字サポートを無効にします。マルチバイト文字のサポートが無効になっている場合、システムはデータを ISO-8859-1 形式であると想定します。Web ページの文字セットは、<span class="varname"> charSet</span> JavaScript変数。 </p> <p>マルチバイト文字のサポートでは、UTF-8 を使用してレポートスイートに文字が保存されます。この要求を受けると、Web ページの文字セットから UTF-8 文字セットにデータが変換されて、マーケティングレポートで任意の言語を使用できるようになります。 </p> <p>既存のレポートスイートのマルチバイト文字サポートを変更する場合は、担当のアカウントマネージャーまたはカスタマーケアにお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> このスイートの Ad Hoc Analysis をアクティブにする</span> </td> 
   <td colname="col2"> ad hoc analysis の実行時にこのレポートスイートを表示できるようにします。 </td> 
  </tr> 
 </tbody> 
</table>

