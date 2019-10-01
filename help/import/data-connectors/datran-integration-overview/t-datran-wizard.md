---
description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。
seo-description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。
seo-title: Data Connectors統合ウィザードの実行
title: Data Connectors統合ウィザードの実行
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Data Connectors統合ウィザードの実行{#running-the-data-connectors-integration-wizard}

Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。

統合を設定するには：

1. Experience Cloud にログインします。
1. Adobe Analyticsホームページで、ピンホイールまたはツールバーのData Connectors™アイコンをクリックします。
1. Data Connectorsページで、統合を設定するレポートスイートを選択します。

   >[!NOTE]
   >
   >必ず、Data Connectorsページの左上隅にある「レポートスイート **** 」ドロップダウンリストから目的のレポートスイートを選択してください。

1. Data Connectors UIの左側にある **パートナーリスト** ( **Partner List** )の上部にある「アルファベット順」タブをクリックし、「データ」アイコンを見つ **けます** 。
1. Data Connectors統合ウ **ィザードを起動するには** 、Adobe Analyticsレポートスイートの空のプラグインスロットに「データ」アイコンをドラッグします。

1. データ統合の概要ページで、テキストを確認し、チェックボックスを選択して統合に関連する料金を受け入れ、「次へ」をクリッ **クします**。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連するアドビとデータランの両方の料金が発生します。 両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. 次の表に示すように、Data Connectors統合ウィザードの各ページで、必要な情報を指定します。

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>ウィザードページ番号</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>統合名 </p> </td> 
   <td colname="col3"> <p>レポートスイートのアクティブな統合リストにData Connectorsが表示する統合名を指定します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>統合電子メールアドレス </p> </td> 
   <td colname="col3"> <p>この統合に関連するすべての通知を受信する電子メールアドレスを指定し、「次へ <b></b> 」をクリックしてウィザードの手順2に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>アカウントID </p> </td> 
   <td colname="col3"> <p>データランアカウントID（Datarnによって組織に割り当てられた一意の識別子）を指定し、「次へ <b></b> 」をクリックしてウィザードの手順3に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>メッセージID </p> </td> 
   <td colname="col3"> <p>電子メールメッセージIDの追跡に使用するAdobe Analytics eVarを識別します。 </p> <p>メッセージIDは、マーケティング/リマーケティングキャンペーンに使用されます。 メッセージIDは、「トラッキングコード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>電子メール受信者IDの追跡に使用するAdobe Analytics eVarを指定します。 </p> <p>受信者IDは、マーケティング/リマーケティングキャンペーンに使用されます。 メッセージIDは、「訪問者コード」と呼ばれることがよくあります。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>承認チェックボックス </p> </td> 
   <td colname="col3"> <p>「受け入れ」チェックボックスの横に表示される情報を確認します。 </p> <p><i>「受信者ID」の追跡を有効にすると、この機能でサイト訪問者の個人特定情報を追跡できることを理解しています。 これは、サイト訪問者に通知を行ったり、サイト訪問者の同意を得たりするなど、プライバシーが適切な手続きを行う必要があることを意味します。 </i> </p> <p>受け入れ文に同意する場合は、チェックボックスを選択し、「 <b>Next</b> 」をクリックしてウィザードの手順4に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>クライアント定義レポートスイートレベルのセグメント </p> </td> 
   <td colname="col3"> <p>この統合により、統合ウィザードの統合セグメントページの左側に表示されるパートナー定義のセグメントが作成されます。 </p> <p>また、統合に含める既存のレポートスイートレベルのセグメントを選択できます。 </p> <p>ページの右側で目的のセグメントを選択し、「次へ <b></b> 」をクリックしてウィザードの手順5に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートした電子メールのクリックデータを保存するAdobe Analyticsイベントを指定します。 </p> <p>クリック済みイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートした電子メールの「開いた」データを保存するAdobe Analyticsイベントを指定します。 </p> <p>Openedイベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートした電子メール送信データを保存するAdobe Analyticsイベントを指定します。 </p> <p>Clickedイベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>合計バウンス数 </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートした電子メールの合計バウンスデータを保存するAdobe Analyticsイベントを指定します。 </p> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col3"> <p>電子メールシステムからインポートした電子メールの登録解除データを保存するAdobe Analyticsイベントを指定します。 </p> <p>「購読解除」イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認し、「購読解除」リンクをクリックして、組織からの今後の電子メールメッセージをオプトアウトできます。 </p> <p>「次へ」をクリックして、ウィザードの手順6に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集：JavaScriptプラグイン </p> </td> 
   <td colname="col3"> <p>この統合の収集モデルとして <b>プラグインを使用する場合は、「</b> JavaScriptプラグイン」を選択し、「次へ <b>」をクリックしてウィザードの手順</b> 7に進みます。 </p> <p> <p>注意： デフォルトでは、自動化ソリューションが選択されます。 </p> </p> <p>アドビコンサルタントに連絡して、この統合に使用するJavaScriptプラグインのコピーを入手してください。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>データ収集：自動化ソリューション </p> </td> 
   <td colname="col3"> <p>この統 <b>合に自動収集モデルを使用する場合は、「自動ソリューション</b> 」を選択し、この統合に使用する一意の識別子を指定します。 </p> <p> <p>注意： デフォルトでは、自動化ソリューションが選択されます。 </p> </p> <p>このオプションを選択した場合は、この統合に使用する一意の識別子を指定します。 </p> <p><b>メッセージIDクエリ文字列パラメ</b>ーター：この値は、電子メールパートナーによってランディングページURLに追加されたメッセージIDを表します。 </p> <p><b></b> 受信者IDクエリ文字列パラメータ：この値は、電子メールパートナーがランディングページのURLに追加する受信者IDを表します。 </p> <p>「 <b>Next</b> 」をクリックして、ウィザードの手順7に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>統合サマリ </p> </td> 
   <td colname="col3"> <p>各カテゴリの横にあるプラス記号(+)をクリックして統合パラメーターを確認し、「保存」をクリックして <b></b> 、ウィザードの手順8に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>統合の完了 </p> </td> 
   <td colname="col3"> <p>「完了 <b></b> 」をクリックして統合を完了します。 </p> <p><b></b> 重要：Adobe Analyticsは、「完了」をクリックするまで統合設定を保存し <b>ません</b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
