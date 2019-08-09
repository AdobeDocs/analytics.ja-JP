---
description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。
seo-title: Silverpop統合
title: Silverpop統合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Silverpop統合{#silverpop-integration}

Data Connectors統合ウィザードでは、Data Connectors統合プロセスを手順に従って進めることができます。

統合を設定するには:

1. Adobe Marketing Cloudで、製品ドロップダウンリストから"Data Connectors™」を選択します。
1. 「新規 **** 追加」をクリックし、 ******[!UICONTROL 「表示」]** ドロップダウンリストで「名前」を選択します。
1. **Silverpop Serving2.0** アイコンを探し、Analyticsレポートスイートの空のプラグインスロットにドラッグして、Data Connectors統合ウィザードを起動します。
1. Silverpop統合の紹介ページで、テキストを確認し、このチェックボックスを選択して統合に関連する料金を受け入れます。
1. この統合に使用するレポートスイートを選択します。
1. この統合を識別するわかりやすい名前を入力し、「 **[!UICONTROL この統合を作成して設定」をクリック]**&#x200B;します。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連するアドビとSilverpopの両方の料金があります。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. Data Connectors統合ウィザードの各ページで、次の表に示すように、必要な情報を入力します。

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>フィールド</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>設定セクション</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>説明</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>統合名 </p> </td> 
   <td colname="col03"> <p>（1）統合設定 </p> </td> 
   <td colname="col3"> <p>Data Connectorsがレポートスイートのアクティブ統合リストに表示する統合名を指定します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>ファイルのダウンロード </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p> ファイルのダウンロードリマーケティングに使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>既知のSilverpop IDを使用しない訪問者へのリマーケティングに使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>アカウントID </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>SilverpopアカウントID（Silverpopによって貴社に割り当てられた一意の識別子）を指定し、「 <b>次へ」</b> をクリックしてウィザードの手順3に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>フォーム名 </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断の再マーケティングに使用。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>メールID </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> バウンス </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートされた電子メールの合計バウンスデータを保存するAnalyticsイベントを指定します。 </p> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートされた電子メールを保存するAnalyticsイベントを指定します。 </p> <p>クリックイベントにより、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> ファイルのダウンロード </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p> ファイルのダウンロードリマーケティングに使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム完了 </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断の再マーケティングに使用。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム開始 </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断の再マーケティングに使用。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートされた電子メールを保存するAnalyticsイベントを指定します。 </p> <p>開封イベントでは、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートされた電子メール送信データを保存するAnalyticsイベントを指定します。 </p> <p>送信イベントでは、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col03"> <p>（2）変数のマッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートされた電子メールのUnsubscribingデータを保存するAnalyticsイベントを指定します。 </p> <p>登録解除イベントにより、電子メールメッセージを開いたが、組織からの将来の電子メールメッセージをオプトアウトするためのリンク解除リンクをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>セグメント </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p>この統合により、パートナーセグメントセクションに表示されるパートナー定義のセグメントが作成されます。 </p> <p>さらに、統合に含める既存のレポートスイートレベルのセグメントを選択できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Access Requests </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p> （必須）この統合を有効 <span class="uicontrol"> にして、製品データ</span>をダウンロードします。 </p> <p>オプション:この統合で売上高、注文件数、数量をダウンロードできるようにします。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>データ収集 </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p>この統合のコレクションモデルとしてs_ code. jsプラグインを使用する場合は、 <b>JavaScriptプラグイン</b> を選択してください（ <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Analyticsプラグインコード</a>を参照）。 </p> <p>この統合に自動収集モデルを使用する場合は「 <b>自動ソリューション</b> 」を選択し、この統合に使用する一意の識別子を指定します。 </p> <p>このオプションを選択する場合、この統合に使用する一意の識別子を指定します。 </p> <p> <b>メッセージIDクエリ文字列パラメータ:</b>この値は、電子メールパートナーによってランディングページのURLに付加されるメッセージIDを表します。 </p> <p> <b>受信者IDクエリ文字列パラメータ:</b> この値は、電子メールパートナーによってランディングページのURLに付加される受信者IDを表します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ダッシュボードとブックマークの生成 </p> </td> 
   <td colname="col03"> <p>（4）レポート設定 </p> </td> 
   <td colname="col3"> <p>統合のダッシュボードとブックマークを自動的に生成します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

