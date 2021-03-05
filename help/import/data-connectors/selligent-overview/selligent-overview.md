---
description: Selligentのdata connectorは、Adobe Analyticsと共に使用します。
title: Adobe Analytics 用 Selligent Data Connector
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 97%

---


# Adobe Analytics 用 Selligent Data Connector {#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>2021年8月1日に、Adobeデータコネクタ技術の提供終了を予定しています。 [詳細情報...](/help/import/data-connectors/data-connectors-eol.md)

この統合の主なメリットは、次のとおりです。

* 電子メールマーケティングデータと分析データを 1 つのレポートインターフェイスに統合。
* 売上高やサイトの成功へのコンバージョンや貢献度によって電子メールキャンペーンを最適化。
* 動的なマーケティングセグメントに基づいて、主要訪問者やマーケティングセグメントへのリマーケティングをおこなう。

## 動的マーケティングセグメント {#section-a2216f3339304636bd5417249bd635a4}

この電子メール統合は、ビジネスの促進に役立つ動的なマーケティングセグメントをサポートします。この統合では、次のマーケティングセグメントが初期設定で使用できます。

| セグメント | 説明 |
|---|---|
| **買い物かご放棄プロファイル** | 商品を買い物かごへ入れたものの、購入をためらうユーザーに合わせて特別なキャンペーンを提示し、訪問者の購入を促すようサポートします。 |
| **購入プロファイル** | 訪問者の購入パターンによってキャンペーンのターゲットを絞り込み、リピート注文件数と平均注文額を増やします。 |
| **製品／コンテンツ表示行動プロファイル** | 製品表示およびコンテンツアクセスのプロファイルに基づいたマーケティングセグメントを通じて、見込み客にリーチします。 |
| **カスタムリマーケティングセグメント** | また、ユーザーのニーズに合わせて、カスタムリマーケティングセグメントの作成やスケジュール設定をおこなうこともできます。 |

## この統合をアクティブ化する前に {#before-you-activate-this-integration}

この統合をアクティブ化する前に、Adobe Analytics のデプロイメントと電子メールソフトウェアに対して、次の項目を確認します。

これにより、アクティブ化の前に、適切なベストプラクティスと前提条件を確実に実施し、最適な統合の成功を実現します。

## Adobe Analytics の前提条件 {#prerequisites-for-adobe-analytics}

統合をデプロイする前に Adobe Analytics で実行する必要があるアクションを示します。

| 前提条件 | メモ |
|---|---|
| レポートスイートの選択 | この統合は、レポートスイートに固有です。統合をアクティブ化する前に、目的のレポートスイートが選択されていることを確認します。 |
| Analytics 変数の設定 | この統合には、カスタムイベントとカスタム eVar、およびオプションで追加イベントと追加の eVar が必要です。Selligent 用の Analytics 変数の設定を参照してください。 |
| 認定担当者 | この統合を有効にすると、貴社と Adobe, Inc. とのサービス契約、またはアドビの信頼できるパートナーとのサービス契約に従って、該当する料金が発生する可能性があります。この統合をアクティブ化することで、お客様が会社によって認定された代表者であり、お客様の会社が上記のサービス契約で定められた料金を支払うことに合意したものとします。 |
| Adobe Data Warehouse™ を有効にする | この統合では、リマーケティングセグメントを生成するために Data Warehouse を有効にしておく必要があります。Adobe Data Warehouse を有効にしていない場合は、アドビにお問い合わせください。 |
| 受信者 ID | 統合では、Analytics 変数（eVar）内で「訪問者 ID」を取得して保存する必要があります。訪問者 ID（「受信者 ID」とも呼ばれる）は、Selligent システムから取得した電子メールアドレスをエンコードまたは数値で表したものです。この「受信者 ID」は、Selligent システムに取り込まれたサイト上でのダウンストリーム訪問者行動（買い物かごの放棄、購入など）に関連付けられており、リマーケティング目的で利用できます。セットアッププロセスの一環として、ウィザードの指示に従い、この目的の eVar を特定する必要があります。 |
| 外部トラッキング | 現在、送信する各電子メールキャンペーンに対して外部トラッキングを有効にするベストプラクティスに従っていない場合は、統合を成功させるために外部トラッキングを有効にする必要があります。詳しくは、以下の Selligent の節を参照してください。 |
| プライバシーコンプライアンス | 受信者 ID または訪問者 ID の追跡を有効にすると、この機能によってサイト訪問者の個人情報を追跡する可能性があります。また、サイト訪問者に通知したり、サイト訪問者の同意を得たりするなど、貴社がプライバシーに関して適切な手順を踏む必要があることを示します。 |

## Selligent 用 Analytics 変数の設定 {#configure-analytics-variables-for-selligent}

この統合では、各レポートスイートの実装に対して 2 つの eVar を予約する必要があります。

これらの eVar とは別に、Selligent のデータに応じて、Analytics で表示したいイベントをいくつか予約できます。これらの eVar およびイベントについて、以下に説明します。

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 変数名 </th> 
   <th colname="col3" class="entry"> 使用方法 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> メッセージ ID </td> 
   <td colname="col3"> 個々の電子メールメッセージキャンペーン ID を取り込む。 </td> 
   <td colname="col4"> <p><b>ステータス</b>：有効 </p> <p><b>配分</b>：最新 </p> <p><b>有効期限：</b>「ビジネス上の意思決定」がおこなわれるまで </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 受信者 ID </td> 
   <td colname="col3"> 電子メールキャンペーンをクリックした顧客の匿名 ID を取り込む。 </td> 
   <td colname="col4"> <p><b>ステータス</b>：有効 </p> <p><b>配分</b>：最新 </p> <p><b>有効期限：</b>「ビジネス上の意思決定」がおこなわれるまで </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> Selligent から送信された電子メールの数を保存する。 </td> 
   <td colname="col4"> <p><b>タイプ</b>：数値 </p> <p><b>パーティシペーション</b>：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 配信済み </td> 
   <td colname="col3"> 配信された電子メールの数を保存する。 </td> 
   <td colname="col4"> <p><b>タイプ</b>：数値 </p> <p><b>パーティシペーション</b>：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 件数 </td> 
   <td colname="col3"> 表示された電子メールの実数を保存する。 </td> 
   <td colname="col4"> <p><b>タイプ</b>：数値 </p> <p><b>パーティシペーション</b>：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> クリック数 </td> 
   <td colname="col3"> 電子メールがクリックされた回数を保存する。 </td> 
   <td colname="col4"> <p><b>タイプ</b>：数値 </p> <p><b>パーティシペーション</b>：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> バウンス </td> 
   <td colname="col3"> バウンスされた電子メールの数を保存する。 </td> 
   <td colname="col4"> <p><b>タイプ</b>：数値 </p> <p><b>パーティシペーション</b>：有効 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligent の前提条件 {#prerequisites-for-selligent}

統合をデプロイする前に Selligent アカウントから提供する必要がある情報を示します。

**有効な Selligent アカウント**

この Data Connectors 統合を使用するには、有効な Selligent アカウントが必要です。

**アカウント情報**

この統合のセットアップ中に、Selligent アカウントに関する次の情報が必要になります。

* **Adobe Service URL**：

   URL は、Selligent Marketing ソリューションへのログオンに使用する URL から取得できます。URLの「/simweb/login.aspx」部分を「/automation/omniture.asmx」に置き換えます。

   例：`http://<client-specific install url>/automation/omniture.asmx`

* **クエリー文字列パラメーター**：ランディングページ URL に追加され、メッセージ ID および受信者 ID（訪問者 ID）を表します。メッセージ ID は常に MID、受信者 ID は RID となります。

* **統合トークン** Simweb でマネージャーツールを起動し、**[!UICONTROL 設定]**／**[!UICONTROL システム設定]**／「**[!UICONTROL 一般]**」タブ／**[!UICONTROL システム]**&#x200B;に移動します。「**[!UICONTROL セキュリティ]**」から、統合トークンを検索できます。

   ![](assets/selligent-integration_token.png)
