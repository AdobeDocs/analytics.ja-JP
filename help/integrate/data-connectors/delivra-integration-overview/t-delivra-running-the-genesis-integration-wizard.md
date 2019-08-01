---
description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-title: Data Connectors統合ウィザードの実行
title: Data Connectors統合ウィザードの実行
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。

統合を設定するには:

1. Marketing Cloud にログインします。
1. Analyticsのホームページで、ピンホイールまたはツールバーのdata connectors™アイコンをクリックします。
1. Data Connectorsページで、統合を設定するレポートスイートを選択します。

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Delivra** icon.
1. **Deivra** アイコンをAnalyticsレポートスイートの空のプラグインスロットにドラッグして、Data Connectors統合ウィザードを起動します。
1. On the Delivra Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連するAdobeとDelovraの料金があります。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
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
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>アカウントID </p> </td> 
   <td colname="col3"> <p>Specify your Delivra Account ID (the unique identifier assigned to your organization by Delivra), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>メッセージID </p> </td> 
   <td colname="col3"> <p>電子メールメッセージIDの追跡に使用するAnalytics eVarを識別します。 </p> <p>メッセージIDは、マーケティング/リマーケティングキャンペーンに使用されます。メッセージIDは「トラッキングコード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>電子メール受信者IDの追跡に使用するAnalytics eVarを識別します。 </p> <p>受信者IDは、マーケティング/リマーケティングキャンペーンに使用されます。メッセージIDは「訪問者コード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>受け入れチェックボックス </p> </td> 
   <td colname="col3"> <p>「受け入れ」チェックボックスの横に表示される情報を確認します。 </p> <p><i>「受信者ID"の追跡を有効にすることで、この機能はサイト訪問者の個人特定情報を追跡することがわかります。This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>クライアント定義のレポートスイートレベルセグメント </p> </td> 
   <td colname="col3"> <p>統合により、統合ウィザードの統合セグメントページの左側に表示されるパートナー定義セグメントが作成されます。 </p> <p>さらに、統合に含める既存のレポートスイートレベルのセグメントを選択できます。 </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールを保存するAnalyticsイベントを指定します。 </p> <p>クリックイベントにより、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールを保存するAnalyticsイベントを指定します。 </p> <p>開封イベントでは、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メール送信データを保存するAnalyticsイベントを指定します。 </p> <p>クリックされたイベントにより、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>合計バウンス </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールの合計バウンスデータを保存するAnalyticsイベントを指定します。 </p> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートされた電子メールの登録解除データを保存するAnalyticsイベントを指定します。 </p> <p>登録解除イベントにより、電子メールメッセージを開いたが、組織からの将来の電子メールメッセージをオプトアウトするためのリンク解除リンクをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> 共有 </td> 
   <td colname="col3"> <p>Specify the number of times the email message was shared to a social network, then click <b>Next</b> to proceed to Step 6 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集:JavaScriptプラグイン </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>注意:自動ソリューションがデフォルトの選択です。 </p> </p> <p>この統合に使用するJavaScriptプラグインのコピーを入手するには、アドビコンサルタントにお問い合わせください。You can also copy and paste the plug-in contained in <a href="delivra-plug-in-code.md#concept_28E7C834A6804A949AA9306F8896B36E" type="concept" format="dita" scope="local"> Analytics Plug-In Code</a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集:自動化ソリューション </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>注意:自動ソリューションがデフォルトの選択です。 </p> </p> <p>このオプションを選択する場合、この統合に使用する一意の識別子を指定します。 </p> <p><b>メッセージIDクエリ文字列パラメータ:</b>この値は、電子メールパートナーによってランディングページのURLに付加されるメッセージIDを表します。 </p> <p><b>受信者IDクエリ文字列パラメータ:</b> この値は、電子メールパートナーによってランディングページのURLに付加される受信者IDを表します。 </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>統合の概要 </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>統合完了 </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>重要:</b> Analyticsでは、「完了」をクリック <b>するまで統合設定は保存されません</b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

