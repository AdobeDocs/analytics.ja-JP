---
description: Data Connectors 統合ウィザードでは、Data Connectors 統合プロセスを順に進めることができます。
title: Silverpop 統合
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 100%

---


# Silverpop 統合 {#silverpop-integration}

Data Connectors 統合ウィザードでは、Data Connectors 統合プロセスを順に進めることができます。

統合を設定するには、次の手順を実行します。

1. Adobe Experience Cloud で、製品ドロップダウンリストから「Data Connectors™」を選択します。
1. 「**[!UICONTROL 新規追加]**」をクリックし、「**[!UICONTROL 表示]**」ドロップダウンリストで「**[!UICONTROL 名前別]**」を選択します。
1. **Silverpop Engage 2.0** アイコンを探し、Analytics レポートスイートの空のプラグインスロットにドラッグして、Data Connectors 統合ウィザードを起動します。
1. Silverpop 統合の概要ページで、テキストを確認後、チェックボックスを選択して統合に関連する料金を承認し、「次へ」をクリックします。
1. この統合に使用するレポートスイートを選択します。
1. この統合を識別するわかりやすい名前を指定し、「**[!UICONTROL この統合を作成および設定]**」をクリックします。

   このページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連して、Adobe と Silverpop の両方で料金が発生します。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。
1. 次の表に示すように、Data Connectors 統合ウィザードの各ページで、必要な情報を提供します。

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
   <td colname="col3"> <p>Data Connectors で、レポートスイートのアクティブな統合リストに表示される統合名。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>ファイルをダウンロード </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p> ファイルダウンロードのリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> 電子メールアドレス </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>既知の Silverpop ID を持たない訪問者に対するリマーケティングに使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>アカウント ID </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>Silverpop アカウント ID（Silverpop によって組織に割り当てられた一意の識別子）を指定し、「<b>次へ</b>」をクリックしてウィザードの手順 3 に進みます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>フォーム名 </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの放棄のリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>郵送 ID </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>(必須) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> バウンス </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムから読み込まれた電子メールのバウンス数合計データを保存する Analytics イベントを指定します。 </p> <p>バウンス数合計イベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>クリック済み </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムから読み込まれた電子メールのクリックデータを保存する Analytics イベントを指定します。 </p> <p>クリックイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> ファイルのダウンロード </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p> ファイルダウンロードのリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム完了 </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの放棄のリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> フォーム開始 </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>フォームの放棄のリマーケティングで使用します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>開封済み </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムから読み込まれた電子メールの開封データを保存する Analytics イベントを指定します。 </p> <p>開封済みイベントを使用すると、電子メールメッセージを開封した訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>送信済み </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムから読み込まれた電子メールの送信済みデータを保存する Analytics イベントを指定します。 </p> <p>送信済みイベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>登録解除 </p> </td> 
   <td colname="col03"> <p>（2）変数マッピング </p> </td> 
   <td colname="col3"> <p>（必須）電子メールシステムから読み込まれた電子メールの登録解除データを保存する Analytics イベントを指定します。 </p> <p>登録解除イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。組織からの今後の電子メールメッセージをオプトアウトするには、登録解除リンクをクリックします。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>セグメント </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p>この統合により、「Partner セグメント」セクションに表示されるパートナー定義のセグメントが作成されます。 </p> <p>また、統合に含める既存のレポートスイートレベルのセグメントを選択することもできます。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>アクセス要求 </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p> （必須）「<span class="uicontrol">この統合に対して製品データのダウンロードを許可</span>」を有効にします。 </p> <p>オプション：この統合に対して、売上高、注文件数、数量のダウンロードを許可します。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>データ収集 </p> </td> 
   <td colname="col03"> <p>（3）データ設定 </p> </td> 
   <td colname="col3"> <p>この統合の収集モデルとして s_code.js プラグインを使用する場合は、「<b>JavaScript プラグイン</b>」を選択します（<a href="../silverpop-overview/silverpop-analytics-code.md">Analytics プラグインコード</a>を参照）。 </p> <p>この統合に自動収集モデルを使用する場合は、「<b>自動ソリューション</b>」を選択し、この統合に使用する一意の ID を指定します。 </p> <p>このオプションを選択する場合は、この統合に使用する一意の ID を指定します。 </p> <p> <b>メッセージ ID クエリー文字列パラメーター：</b>電子メールパートナーによるランディングページ URL にメッセージ ID を追加した値です。 </p> <p> <b>受信者 ID クエリー文字列パラメーター：</b>電子メールパートナーによるランディングページ URL に受信者 ID を追加した値です。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ダッシュボードとブックマークの生成 </p> </td> 
   <td colname="col03"> <p>（4）レポート設定 </p> </td> 
   <td colname="col3"> <p>統合用のダッシュボードとブックマークを自動生成します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

