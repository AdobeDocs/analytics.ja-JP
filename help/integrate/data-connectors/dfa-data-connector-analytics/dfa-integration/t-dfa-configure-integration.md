---
description: DFA Data Connectors 統合を順を追って説明します。
seo-description: DFA Data Connectors 統合を順を追って説明します。
seo-title: DFA 統合の設定
title: DFA 統合の設定
uuid: 4c2ac58a-87c6-46f3-9033-9404beb18c39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# DFA 統合の設定{#configure-the-dfa-integration}

DFA Data Connectors 統合を順を追って説明します。

設定ページには、統合の概要とその他の情報に関する便利なリンクがあります。この統合に関連して、Adobe と DoubleClick の両方で料金が発生します。両方の組織の営業担当者に問い合わせて、料金体系を把握するようにしてください。

1. Log in to the [!DNL Adobe Analytics].
1. **[!UICONTROL 管理者]** / **[!UICONTROL Data Connectors]**&#x200B;をクリックします。

   ![](assets/data_connectors.png)

1. **[!UICONTROL DoubleClick DFA]**&#x200B;を探し、「新規追加」をクリック ****&#x200B;します。

   ![手順の結果](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. 次の表に、ウィザードを使用して統合を完了するために必要な情報を示します。

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ウィザードのページ # </th> 
   <th colname="col2" class="entry"> フィールド </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 統合名 </td> 
   <td colname="col3"> Genesis で、レポートスイートの有効な統合リストに表示される統合名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 統合電子メールアドレス </td> 
   <td colname="col3"> この統合に関連するすべての通知を受信する電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ユーザー名 </td> 
   <td colname="col3"> この統合で使用する DFA API ユーザー名。API ログインのユーザーを有効にするには、DFA インターフェイスの API 属性をチェックします。API ログインを有効にすると、パスワードフィールドが表示されるので、ユーザーのパスワードを入力します。このパスワードは、認証のためにウィザードでユーザー名と共に入力します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> パスワード </td> 
   <td colname="col3"> DFA API パスワード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 広告主 ID </td> 
   <td colname="col3"> <p>DFA 広告主 ID または親の Floodlight 設定 ID。Data Connectors は、この ID を使用して、トラッキングする DFA 広告主を識別します（統合のバージョン 1.5）。この広告主IDは、統合のバージョン2.0では使用されません。親のFloodlight設定IDは検索および使用されます。画面上の指示を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA 広告変数 </td> 
   <td colname="col3"> DFA キャンペーン属性、インプレッション数およびクリック数データを受け取る Analytics eVar。通常、これはトラッキングコード eVar（<span class="varname"> s. campaign </span>）を使用することもできますが、使用可能な任意のeVarを選択できます。また、Data Connectors は、選択した eVar に次の DFA 関連の分類を追加します。 <p><b>キャンペーン</b>：共通のメッセージングを届ける複数のサイトに提供される広告のコレクション。 </p> <p><b>サイト名</b>：広告が提供されたサイト。 </p> <p><b>広告名</b>：DFA アカウントで定義された広告名。 </p> <p><b>サイトプレースメント名</b>：広告が提供された Web サイトおよびページ。 </p> <p><b>配信ツール</b>：DoubleClick for Advertisers。 </p> <p><b>チャネル</b>：バナー広告。 </p> <p><b>コスト構造</b>：CPM、CPC または固定。広告のコスト構造に基づきます。 </p> <p><b>クリエイティブ名</b>：広告／プレースメント／クリエイティブ ID に関連付けられたクリエイティブの名前。 </p> <p><b>DFA／SearchCenter 重複除外</b>：DFA クリックスルーまたはビュースルーが発生した場合に、DFA によって SearchCenter 変数の値が配置されるように指定します。詳しくは、<a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">SearchCenter 重複除外</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> インプレッション数 </td> 
   <td colname="col3"> DFA インプレッション数指標データを受け取るカスタムイベント。インプレッション数は、広告が提供された回数を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> クリック数 </td> 
   <td colname="col3"> DFA クリック数指標データを受け取るカスタムイベントを選択します。クリック数は、訪問者が DFA のリダイレクトによって測定された広告をクリックした回数を示します。クリック数指標は、Analytics クリックスルー指標と相関関係があります。 <p>注意： DFA クリック数と Analytics クリックスルーは、データの収集方法が異なるので、厳密に一致しない可能性があります。For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> ビュースルー変数 </td> 
   <td colname="col3"> <p>DFA ビュースルーデータを受け取る Analytics eVar。ビュースルー変数は、ビュースルーがサイトのコンバージョン率にどれくらい影響するかを確認するのに役立ちます。 </p> <p>Data Connectors は、DFA 広告変数に追加するのと同じ DFA 関連の分類をこの eVar に追加します（上述を参照）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 前回の表示からの時間（ビュースルー時間グループ変数） </td> 
   <td colname="col3"> DFA の前回の表示からの時間データを受け取る Analytics eVar。前回の表示からの時間は、最後の広告ビュースルーから経過した時間を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> ビュースルー数 </td> 
   <td colname="col3"> DFA ビュースルー数指標データを受け取るカスタムイベント。ビュースルーイベントをビュースルー変数と共に使用して、直接クリックスルーに影響しないが、その後の時間にサイトへのトラフィック上昇に一役買った可能性のあるキャンペーンはどれかを確認します。 <p>Data Connectors は、選択したカスタムイベントの名前を「ビュースルー数」に変更します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA クエリ失敗 </td> 
   <td colname="col3"> （オプション）レポートされた DFA クエリ失敗メッセージコードを受け取る Analytics eVar。可能性のある DFA メッセージコードを次に示します。 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>：DoubleClick cookie がありません。 </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>：ユーザーはオプトアウトしました。 </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>：キャンペーン履歴がありません。 </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>：クエリエラー（タイムアウト、サーバーダウン、その他）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> タイムアウトイベント </td> 
   <td colname="col3"> <p>Analyticsカウンターイベント<span class="varname"> s. maxDelay </span> タイマーが期限切れになり、DFAサーバーから応答が受け取られなかった問題を修正しました。Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

