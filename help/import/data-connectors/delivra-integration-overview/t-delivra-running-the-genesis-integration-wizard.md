---
description: Data Connectors 統合ウィザードでは、Data Connectors 統合プロセスを順に進めることができます。
title: Data Connectors 統合ウィザードの実行
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 100%

---


# Data Connectors 統合ウィザードの実行 {#running-the-data-connectors-integration-wizard}

Data Connectors 統合ウィザードでは、Data Connectors 統合プロセスを順に進めることができます。

統合を設定するには、次の手順を実行します。

1. Experience Cloud にログインします。
1. Analytics ホームページで、ピンホイールまたはツールバーの Data Connectors™ アイコンをクリックします。
1. Data Connectors ページで、統合を設定するレポートスイートを選択します。

   >[!NOTE]
   >
   >必ず、Data Connectors ページの左上隅にある「**レポートスイート**」ドロップダウンリストから目的のレポートスイートを選択してください。

1. Data Connectors UI の左側にある&#x200B;**パートナーリスト**&#x200B;で、一番上の「**アルファベット順**」タブをクリックし、**Delivra** アイコンを見つけます。
1. **Delivra** アイコンを Analytics レポートスイートの空のプラグインスロットにドラッグし、Data Connectors 統合ウィザードを起動します。
1. Delivra 統合の概要ページで、テキストを確認し、チェックボックスを選択して統合に関連する料金を承認し、「**次へ**」をクリックします。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連して、Adobe と Delivra の両方で料金が発生します。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. 次の表に示すように、Data Connectors 統合ウィザードの各ページで、必要な情報を提供します。

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>ウィザードのページ #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>フィールド</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>説明</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>統合名 </p> </td> 
   <td colname="col3"> <p>Data Connectors で、レポートスイートのアクティブな統合リストに表示される統合名。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>統合電子メールアドレス </p> </td> 
   <td colname="col3"> <p>この統合に関連するすべての通知を受信する電子メールアドレスを指定し、「<b>次へ</b>」をクリックしてウィザードの手順 2 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>アカウント ID </p> </td> 
   <td colname="col3"> <p>Delivra アカウント ID（Delivra によって組織に割り当てられた一意の識別子）を指定し、「<b>次へ</b>」をクリックしてウィザードの手順 3 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>メッセージ ID </p> </td> 
   <td colname="col3"> <p>電子メールメッセージ ID の追跡に使用する Analytics eVar を識別します。 </p> <p>メッセージ ID は、マーケティングキャンペーンやリマーケティングキャンペーンに使用されます。メッセージ ID は「トラッキングコード」とも呼ばれています。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>受信者 ID </p> </td> 
   <td colname="col3"> <p>電子メール受信者 ID の追跡に使用する Analytics eVar を識別します。 </p> <p>受信者 ID は、マーケティングキャンペーンやリマーケティングキャンペーンに使用されます。メッセージ ID は「訪問者コード」とも呼ばれています。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>承認チェックボックス </p> </td> 
   <td colname="col3"> <p>承認チェックボックスの横に表示される情報を確認します。 </p> <p><i>「受信者 ID」の追跡を有効にすることによって、この機能がサイト訪問者の個人識別情報を追跡する可能性があることを理解するものとします。また、サイト訪問者に通知したり、サイト訪問者の同意を得たりするなど、プライバシーに関して適切な手順を踏む必要があることを了承します。</i> </p> <p>承認ステートメントに同意する場合は、チェックボックスを選択し、「<b>次へ</b>」をクリックしてウィザードの手順4に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>クライアント定義レポートスイートレベルのセグメント </p> </td> 
   <td colname="col3"> <p>この統合により、統合ウィザードの統合セグメントページ左側に表示される、パートナー定義のセグメントが作成されます。 </p> <p>また、統合に含める既存のレポートスイートレベルのセグメントを選択することもできます。 </p> <p>ページの右側で目的のセグメントを選択し、「<b>次へ</b>」をクリックしてウィザードの手順 5 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムから読み込まれた電子メールのクリック済みデータを保存する Analytics イベントを指定します。 </p> <p>クリックイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムから読み込まれた電子メールの開封済みデータを保存する Analytics イベントを指定します。 </p> <p>開封済みイベントを使用すると、電子メールメッセージを開封した訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムから読み込まれた電子メールの送信済みデータを保存する Analytics イベントを指定します。 </p> <p>クリックイベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>バウンス数合計 </p> </td> 
   <td colname="col3"> <p>電子メールシステムから読み込まれた、電子メールのバウンス数合計データを保存する Analytics イベントを指定します。 </p> <p>バウンス数合計イベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col3"> <p>電子メールシステムから読み込まれた電子メールの登録解除データを保存する Analytics イベントを指定します。 </p> <p>登録解除イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。組織からの今後の電子メールメッセージをオプトアウトするには、登録解除リンクをクリックします。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> 共有 </td> 
   <td colname="col3"> <p>電子メールメッセージがソーシャルネットワークに共有された回数を指定し、「<b>次へ</b>」をクリックしてウィザードの手順 6 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集：JavaScript プラグイン </p> </td> 
   <td colname="col3"> <p>この統合の収集モデルとしてプラグインを使用する場合は、「<b>JavaScript プラグイン</b>」を選択し、「<b>次へ</b>」をクリックしてウィザードの手順 7に進みます。 </p> <p> <p>注意：デフォルトでは、「自動ソリューション」が選択されます。 </p> </p> <p>この統合に使用する JavaScript プラグインのコピーを入手するには、アドビ担当コンサルタントにお問い合わせください。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集：自動ソリューション </p> </td> 
   <td colname="col3"> <p>この統合に自動収集モデルを使用する場合は、「<b>自動ソリューション</b>」を選択し、この統合に使用する一意の ID を指定します。 </p> <p> <p>注意：デフォルトでは、「自動ソリューション」が選択されます。 </p> </p> <p>このオプションを選択する場合は、この統合に使用する一意の ID を指定します。 </p> <p><b>メッセージ ID クエリー文字列パラメーター：</b>電子メールパートナーによるランディングページ URL にメッセージ ID を追加した値です。 </p> <p><b>受信者 ID クエリー文字列パラメーター：</b>電子メールパートナーによるランディングページ URL に受信者 ID を追加した値です。 </p> <p>「<b>次へ</b>」をクリックして、ウィザードの手順 7 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>統合の概要 </p> </td> 
   <td colname="col3"> <p>各カテゴリの横にあるプラス記号（+）をクリックして統合パラメーターを確認した後、「<b>保存</b>」をクリックしてウィザードの手順 8 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>統合の完了 </p> </td> 
   <td colname="col3"> <p>「<b>完了</b>」をクリックして統合を完了します。 </p> <p><b>重要：</b>Analytics は、「<b>完了</b>」をクリックするまで統合設定を保存しません。 </p> </td> 
  </tr> 
 </tbody> 
</table>
