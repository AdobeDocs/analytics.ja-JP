---
description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。
seo-description: Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。
seo-title: Silverpop統合
title: Silverpop統合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Silverpop統合{#silverpop-integration}

Data Connectors統合ウィザードでは、Data Connectors統合プロセスの手順を実行します。

統合を設定するには：

1. Adobe Experience cloudで、製品ドロップダウンリストから「Data Connectors™」を選択します。
1. 「新規追 **[!UICONTROL 加」をクリックし]** 、「表示 **[!UICONTROL 」ドロップダウンリ]****** ストで「名前別」を選択します。
1. Silverpop Engage 2.0 **** （Silverpopソーシャル管理）アイコンを探し、Analyticsレポートスイートの空のプラグインスロットにドラッグして、Data Connectors統合ウィザードを起動します。
1. Silverpop統合の概要ページで、テキストを確認し、チェックボックスを選択して統合に関連する料金を受け入れます。
1. この統合に使用するレポートスイートを選択します。
1. この統合を識別するわかりやすい名前を指定し、「この統合を作成 **[!UICONTROL および設定」をクリックします]**。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連するAdobeとSilverpopの両方の料金が発生します。 両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. 次の表に示すように、Data Connectors統合ウィザードの各ページで、必要な情報を指定します。

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
   <td colname="col03"> <p>(1)統合設定 </p> </td> 
   <td colname="col3"> <p>レポートスイートのアクティブな統合リストにData Connectorsが表示する統合名を指定します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>ファイルのダウンロード </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p> ファイルダウンロードのリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>既知のSilverpop IDを持たない訪問者に対する再マーケティングに使用されます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>アカウントID </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>SilverpopアカウントID（Silverpopによって組織に割り当てられた一意の識別子）を指定し、「次へ <b></b> 」をクリックしてウィザードの手順3に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>フォーム名 </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断再マーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>郵送ID </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> バウンス </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートした電子メールの合計バウンスデータを保存するAnalyticsイベントを指定します。 </p> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートした電子メールのクリックデータを保存するAnalyticsイベントを指定します。 </p> <p>クリック済みイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> ファイルのダウンロード </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p> ファイルダウンロードのリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム完了 </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断再マーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム開始 </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの中断再マーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートした電子メールの「開いた」データを保存するAnalyticsイベントを指定します。 </p> <p>Openedイベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートした電子メール送信データを保存するAnalyticsイベントを指定します。 </p> <p>送信イベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col03"> <p>(2)変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムからインポートした電子メールの登録解除データを保存するAnalyticsイベントを指定します。 </p> <p>「購読解除」イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認し、「購読解除」リンクをクリックして、組織からの今後の電子メールメッセージをオプトアウトできます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>セグメント </p> </td> 
   <td colname="col03"> <p>(3)データ設定 </p> </td> 
   <td colname="col3"> <p>この統合により、「パートナーセグメント」セクションに表示されるパートナー定義のセグメントが作成されます。 </p> <p>また、統合に含める既存のレポートスイートレベルのセグメントを選択できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Access Requests </p> </td> 
   <td colname="col03"> <p>(3)データ設定 </p> </td> 
   <td colname="col3"> <p> （必須）「この統合で製 <span class="uicontrol"> 品データをダウンロードできるようにします</span>。 </p> <p>オプション：この統合で、売上高、注文件数、数量をダウンロードできます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>データ収集 </p> </td> 
   <td colname="col03"> <p>(3)データ設定 </p> </td> 
   <td colname="col3"> <p>s_code <b>.jsプラグインをこの統合の収集モデルとして使用する場合は、「</b> JavaScriptプラグイン」を選択します( <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Analyticsプラグインコードを参照</a>)。 </p> <p>この統 <b>合に自動収集モデルを使用する場合は、「自動ソリューション</b> 」を選択し、この統合に使用する一意の識別子を指定します。 </p> <p>このオプションを選択した場合は、この統合に使用する一意の識別子を指定します。 </p> <p> <b>メッセージIDクエリ文字列パラメ</b>ーター：この値は、電子メールパートナーによってランディングページURLに追加されたメッセージIDを表します。 </p> <p> <b></b> 受信者IDクエリ文字列パラメータ：この値は、電子メールパートナーがランディングページのURLに追加する受信者IDを表します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ダッシュボードとブックマークの生成 </p> </td> 
   <td colname="col03"> <p>(4)[レポート設定] </p> </td> 
   <td colname="col3"> <p>統合用のダッシュボードとブックマークを自動生成します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

