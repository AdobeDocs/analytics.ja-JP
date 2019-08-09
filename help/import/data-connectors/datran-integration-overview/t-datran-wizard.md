---
description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-title: Data Connectors統合ウィザードの実行
title: Data Connectors統合ウィザードの実行
uuid: 714417f7- c1df-4e61- a07f- d319f6581c9c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Data Connectors統合ウィザードの実行{#running-the-data-connectors-integration-wizard}

Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。

統合を設定するには:

1. Marketing Cloud にログインします。
1. Adobe Analyticsホームページで、ピンホイールまたはツールバーのdata connectors™アイコンをクリックします。
1. Data Connectorsページで、統合を設定するレポートスイートを選択します。

   >[!NOTE]
   >
   >Data Connectorsページの左上隅にある **「レポートスイート** 」ドロップダウンリストから、目的のレポートスイートを選択してください。

1. Data **Connectors** UIの左側にある **パートナーリスト** の上部にある「アルファベット順」タブをクリックして、 **Datran** アイコンを見つけます。
1. **Datran** アイコンをAdobe Analyticsレポートスイートの空のプラグインスロットにドラッグして、Data Connectors統合ウィザードを起動します。

1. Datran統合の紹介ページで、テキストを確認し、このチェックボックスを選択して統合に関連する料金を承認し、「 **次へ**」をクリックします。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連するAdobeとDatranの両方の料金があります。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. Data Connectors統合ウィザードの各ページで、次の表に示すように、必要な情報を入力します。

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>ウィザードPAGE#</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>統合名 </p> </td> 
   <td colname="col3"> <p>Data Connectorsがレポートスイートのアクティブ統合リストに表示する統合名を指定します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>統合電子メールアドレス </p> </td> 
   <td colname="col3"> <p>この統合に関連するすべての通知を受信する電子メールアドレスを指定し、「 <b>次へ」</b> をクリックしてウィザードの手順2に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>アカウントID </p> </td> 
   <td colname="col3"> <p>DatranアカウントID（Datranによって貴社に割り当てられた一意の識別子）を指定し、「 <b>次へ」</b> をクリックしてウィザードの手順3に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>メッセージID </p> </td> 
   <td colname="col3"> <p>電子メールメッセージIDの追跡に使用するAdobe Analytics eVarを識別します。 </p> <p>メッセージIDは、マーケティング/リマーケティングキャンペーンに使用されます。メッセージIDは「トラッキングコード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>電子メール受信者IDの追跡に使用するAdobe Analytics eVarを識別します。 </p> <p>受信者IDは、マーケティング/リマーケティングキャンペーンに使用されます。メッセージIDは「訪問者コード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>受け入れチェックボックス </p> </td> 
   <td colname="col3"> <p>「受け入れ」チェックボックスの横に表示される情報を確認します。 </p> <p><i>「受信者ID"の追跡を有効にすることで、この機能はサイト訪問者の個人特定情報を追跡することがわかります。これには、サイト訪問者に対する通知や同意を得るなど、自社の組織による適切な手順の導入を必要とするプライバシーに関する配慮があります。 </i> </p> <p>同意文に同意した場合は、チェックボックスを選択し、「 <b>次へ」</b> をクリックしてウィザードの手順4に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>クライアント定義のレポートスイートレベルセグメント </p> </td> 
   <td colname="col3"> <p>統合により、統合ウィザードの統合セグメントページの左側に表示されるパートナー定義セグメントが作成されます。 </p> <p>さらに、統合に含める既存のレポートスイートレベルのセグメントを選択できます。 </p> <p>ページの右側で目的のセグメントを選択し、「 <b>次へ」</b> をクリックしてウィザードの手順5に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールを保存するAdobe Analyticsイベントを指定します。 </p> <p>クリックイベントにより、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールを保存するAdobe Analyticsイベントを指定します。 </p> <p>開封イベントでは、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メール送信データを保存するAdobe Analyticsイベントを指定します。 </p> <p>クリックされたイベントにより、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>合計バウンス </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールの合計バウンスデータを保存するAdobe Analyticsイベントを指定します。 </p> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールの登録解除データを保存するAdobe Analyticsイベントを指定します。 </p> <p>登録解除イベントにより、電子メールメッセージを開いたが、組織からの将来の電子メールメッセージをオプトアウトするためのリンク解除リンクをクリックした訪問者の数を確認できます。 </p> <p>「次へ」をクリックして、ウィザードの手順6に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集:JavaScriptプラグイン </p> </td> 
   <td colname="col3"> <p>この統合のコレクションモデルとしてプラグインを使用したい場合は <b>"JavaScriptプラグイン</b> 」を選択し、「 <b>次へ」</b> をクリックしてウィザードの手順7に進みます。 </p> <p> <p>注意:自動ソリューションがデフォルトの選択です。 </p> </p> <p>この統合に使用するJavaScriptプラグインのコピーを入手するには、アドビコンサルタントにお問い合わせください。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集:自動化ソリューション </p> </td> 
   <td colname="col3"> <p>この統合に自動収集モデルを使用する場合は「 <b>自動ソリューション</b> 」を選択し、この統合に使用する一意の識別子を指定します。 </p> <p> <p>注意:自動ソリューションがデフォルトの選択です。 </p> </p> <p>このオプションを選択する場合、この統合に使用する一意の識別子を指定します。 </p> <p><b>メッセージIDクエリ文字列パラメータ:</b>この値は、電子メールパートナーによってランディングページのURLに付加されるメッセージIDを表します。 </p> <p><b>受信者IDクエリ文字列パラメータ:</b> この値は、電子メールパートナーによってランディングページのURLに付加される受信者IDを表します。 </p> <p>「 <b>Next</b> 」をクリックして、ウィザードの手順7に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>統合の概要 </p> </td> 
   <td colname="col3"> <p>各カテゴリの横にあるプラス記号（+）をクリックして統合パラメーターを確認し、 <b>「保存」</b> をクリックしてウィザードの手順8に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>統合完了 </p> </td> 
   <td colname="col3"> <p>「 <b>Finish"</b> をクリックして統合を完了します。 </p> <p><b>重要:</b> Adobe Analyticsでは、「完了」をクリック <b>するまで統合設定は保存されません</b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

