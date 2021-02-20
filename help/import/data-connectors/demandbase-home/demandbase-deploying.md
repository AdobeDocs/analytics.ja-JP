---
description: この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。
title: 統合のデプロイ
uuid: 9c116ca8-4dbf-44eb-a832-574527ee88b7
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 98%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## アドビ統合ウィザードの完了 {#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectors インターフェイス内で設定ウィザードを完了する必要があります。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。
1. Demandbase 2.0 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 電子メール住所 </td> 
   <td colname="col2"> 主要連絡先の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 説明 </td> 
   <td colname="col2"> （オプション）この統合設定の説明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API キー </td> 
   <td colname="col2"> Demandbase の担当者から入手できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタム Demandbase ディメンション #N </td> 
   <td colname="col2"> 8 つのオプションディメンション用の ID があります。詳細は、「Demandbase カスタムディメンション」を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adobe Target に送信 </td> 
   <td colname="col2">「true」の場合、Demandbase ディメンションは、非表示の mbox を使用して Adobe Target にも送信されます。 <p>注意：ディメンションを収集するには、設定済みの mbox.js ファイルを Web ページに実装する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 次の「変数マッピング」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | Demandbase ディメンション | 使用可能な eVar 変数をレポートスイートから選択します。 |
   | Demandbase カスタムディメンション（オプション） | 使用可能な eVar 変数をレポートスイートから選択します。 |

1. カスタムディメンションの名前を設定します（該当する場合）。

   1. 手順 4 でカスタムディメンションを含め、手順 5 でオプションの eVar をマッピングした場合は、これらのディメンションにわかりやすい名前を付ける必要があります。例えば、カスタムディメンション 1 に「stock_ticker」と入力する場合は、「ディメンション1」を含むボックスを「株式情報」に変更する必要があります。
   1. 8 つの標準ディメンションの名前（Demandbase SID、会社名、業種など）は変更&#x200B;**しないでください**。

1. Demandbase 統合ダッシュボードを自動的に作成する場合は、このチェックボックスをオンにします（推奨）。
1. すべての設定項目を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。

## 統合コードのデプロイ {#deploying-the-integration-code}

統合ウィザードを完了したら、統合コードを Adobe Analytics デプロイメントコード（s_code）にデプロイする必要があります。

>[!NOTE]
>
>Adobe TagManager または Dynamic Tag Management を使用して Adobe Analytics を実装する場合は、これらのツールのいずれかを使用して統合コードを簡単に追加できます。

1. 「**[!UICONTROL サポート]**」タブに移動し、統合のリソース領域から `integration code v2_0_1` リソースをダウンロードして保存します。

1. 必要に応じて、コードに必要な変更を加えます。詳しくは、「統合コードの変更」（このページ）を参照してください。
1. Adobe Analytics デプロイメントコードにまだ統合モジュールが存在しない場合は、この統合モジュールを含めます。
1. 次のいずれかの方法を使用してコードをデプロイします。

   * Adobe TagManager または Dynamic Tag Management を使用してコードを追加します。
   * または、Adobe Analytics デプロイメントコードの更新を担当する組織のリソースにコードを配信します。

>[!IMPORTANT]
>
>この統合のデプロイメントを本番環境にデプロイする前に、開発／ステージング環境でテストしてください。

## 統合コードの変更 {#modifying-the-integration-code}

ほとんどの場合、Data Connector ウィザードで生成される統合コードを変更する必要はありません。

ただし、調整が必要な場合は、以下に示すコード設定を利用できます。

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード設定 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">Adobe Analytics イメージリクエストが、Analytics コレクションサーバーに対して実行する前に Demandbase データを待機する時間（ミリ秒）の最大値です。 <p>注意：この設定は、Integrate モジュールを通じて実行する可能性がある、すべての統合に適用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._key </td> 
   <td colname="col2"> Demandbase API キー。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_apiURL </td> 
   <td colname="col2"> Demandbase API の URL テンプレート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_delim </td> 
   <td colname="col2"> Demandbaseディメンション項目がAdobe Analyticsに送信される際に、その項目を区切るために使用される区切り文字。 この設定を変更すると、デフォルトの分類ルールが正しく機能しない場合があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_setTnt </td> 
   <td colname="col2">true の場合、統合コードは、非表示の mbox を使用して、Demandbase ディメンションをプロファイルパラメーターとして Adobe Target に送信しようとします。 <p>注意：これには、mbox.js コードがページ上に存在する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_tntVarPrefix </td> 
   <td colname="col2"> この文字列は、Adobe Target に送信する前に、各 Demandbase ディメンション名の前に追加されます。例えば、この設定の値が「db_」の場合、ディメンション「industry」は「db_industry」として Adobe Target に送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_dimensionsArray </td> 
   <td colname="col2"> Adobe Analytics に送信される標準の Demandbase ディメンションです。この設定は変更しないことをお勧めします。「max_size」プロパティは、切り捨てが発生する前にディメンションで使用できる文字の数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_dimensionsArrayCustom </td> 
   <td colname="col2"> Adobe Analytics に送信されるカスタムの Demandbase ディメンションです。「max_size」プロパティは、切り捨てが発生する前にディメンションで使用できる文字の数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_cName </td> 
   <td colname="col2"> Demandbase API 通信の状態を維持するために使用するセッション cookie の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_contextName </td> 
   <td colname="col2"> 標準ディメンションを Adobe Analytics に送信するために使用される contextData 変数の名前。この設定は変更しないことをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db_contextNameCustom </td> 
   <td colname="col2"> カスタムディメンションを Adobe Analytics に送信するために使用される contextData 変数の名前。この設定は変更しないことをお勧めします。 </td> 
  </tr> 
 </tbody> 
</table>

## Integrate モジュールの追加 {#including-the-integrate-module}

統合コードを使用するには、Adobe Analytics デプロイメント内に Integrae モジュールが存在する必要があります。

デプロイメントの一部として Integrate モジュールをまだお持ちでない場合は、実装のタイプに応じて、次の手順を実行してください。

### AppMeasurement v1.0 以降の場合 {#section-f28d090bf2404cabaae34cd9c66fc575}

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL CodeManager]** からダウンロードできる AppMeasurement zip ファイルを展開します。

1. [!DNL AppMeasurement_Module_Integrate.js] という名前のファイルを開きます。
1. このファイルの内容をコピーして、プライマリ [!DNL AppMeasurement.js] ファイルに貼り付けます。

   >[!NOTE]
   >
   >ファイル内の「DO NOT ALTER ANYTHING BELOW THIS LINE」というコメントの直前に貼り付けます。

### レガシーコード（H コード）の場合 {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Data Connectors UI の「リソース」領域（「サポート」タブの下）から Integrate モジュールをダウンロードします。

   ![](assets/h_code.png)

1. そのファイルの内容をコピーして、[!DNL s_code] ファイルに貼り付けます。

   >[!NOTE]
   >
   >ファイル内の「DO NOT ALTER ANYTHING BELOW THIS LINE」というコメントの直前に貼り付けます。

## 統合の確認 {#verifying-the-integration}

ライブトラッキングとレポートをチェックし、統合によってデータが正常に取得されたことを確認します。

### ライブトラッキング {#section-9c20e8ff6b404ae09387ee07d675c9e2}

DigitalPulse デバッガーツールを使用して、Demandbase ディメンションデータが Adobe Analytics 経由で送信されることを確認します。Cookie を削除した後、統合コードが導入されている Web サイトのページをリロードします。現在の IP が Demandbase によって認識される組織にマッピングされている場合、次のような結果が表示されます。

**Reports &amp; Analytics（旧称 SiteCatalyst）には、次の 2 つの Demandbase コンテキストデータ変数が含まれています。**

![](assets/debugger1.png)

**Target Mbox には、Demandbase プロファイルパラメーターを含める：**&#x200B;ページに Target を実装し、この統合を Adobe Target 用に設定している場合にのみ表示されます。アドビ統合ウィザードの手順 4 を参照してください。

![](assets/debugger2.png)

### レポート {#section-1792fe75dc3249d0ad063dfd87a89162}

アドビ統合ウィザード（手順 7）で自動的に作成されたダッシュボードを使用して、Adobe Analytics 内で Demandbase レポートを確認します。

または、Adobe Analytics のメニュー構造内で Demandbase レポートに移動できます（以下のスクリーンショットを参照）。

>[!NOTE]
>
>このデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。

![](assets/reporting1.png)

![](assets/reporting2.png)

### よくある質問 {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**「[該当なし]」とは何ですか。**

Demandbase Data Connectors は、このデフォルト値を設定することで属性が「使用不可」となったタイミングを示します。デフォルトが設定される一般的なシナリオは 2 つあります。

* Demandbase が、会社に所属していない IP ドレスからの訪問者を検出する。
* アカウント監視属性（「watch_list」で始まる）が使用されているが、その会社がアカウント監視リストに含まれていない。

**特定の属性に対し、「`[n/a]`」が他よりも頻繁に表示されるのはなぜですか。**

Demandbase は、すべての IP アドレスを分類し、訪問者が会社の IP アドレスから来ていない場合でも audience および audience_segment 属性を提供します。オーディエンスが「Residential」、「Wireless」、「Pospitary」などの値を返した場合、残りの属性は使用できない可能性があります。

訪問者のオーディエンスが「SMB」となっていても、他の属性では「`[n/a]`」と表示される場合があります。つまり、Demandbase では訪問者を中小企業に分類できますが、会社のプロファイル全体は使用できません。これは通常、複数の中小企業が同じサービスプロバイダーまたは IP アドレスのブロックを使用している場合に、小規模な企業で発生します。

### 開発者向けの考慮事項 {#section-d33fff55bc4b4db99f82dee418ef1bc2}

実装のデフォルト値を調整する必要がある場合は、次の行を更新します。

```
_db._nonOrgMatchLabel = "[n/a]";
```
