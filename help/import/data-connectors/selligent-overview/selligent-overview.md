---
description: 'null'
title: Selligent Data Connector for Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

この統合には、次の主な利点が含まれます。

* 電子メールマーケティングおよび分析データを1つのレポートインターフェイスに統合します。
* コンバージョンや売上高やサイトの成功への貢献度によって電子メールキャンペーンを最適化する。
* 動的なマーケティングセグメントに基づいて主要訪問者やマーケティングセグメントに再マーケティングします。

## 動的マーケティングセグメント {#section-a2216f3339304636bd5417249bd635a4}

この電子メールの統合は、ビジネスの促進に役立つ動的なマーケティングセグメントをサポートします。 この統合では、次のマーケティングセグメントが初期設定で使用できます。

| セグメント | 説明 |
|---|---|
| **買い物かご放棄プロファイル** | 訪問者が買い物かごを完成させるのをためらう人々に向けて特別に設計された微調整されたキャンペーンを通じて、顧客にコンバージョンするのを支援します。 |
| **購入プロファイル** | 訪問者の購入パターンによってターゲット設定されたキャンペーンを通じて、リピート注文件数と平均注文額を増やします。 |
| **製品/コンテンツビューの行動プロファイル** | 製品表示とコンテンツアクセスプロファイルに基づくマーケティングセグメントを通じて見込み客に連絡します。 |
| **カスタムリマーケティングセグメント** | また、ユーザーのニーズに合わせたカスタムリマーケティングセグメントを作成し、スケジュールを設定することもできます。 |

## この統合をアクティブ化する前に{#before-you-activate-this-integration}

この統合をアクティブ化する前に、Adobe Analyticsと電子メールソフトウェアのデプロイメントに対して、以下の項目を確認します。

これにより、アクティブ化の前に、適切なベストプラクティスと前提条件が確実に実施されます。 これにより、最適で成功した統合が得られます。

## Adobe Analyticsの前提条件{#prerequisites-for-adobe-analytics}

統合を導入する前にAdobe Analyticsで実行する必要があるアクションを示します。

| 前提条件 | メモ |
|---|---|
| レポートスイートの選択 | この統合はレポートスイートに固有であることをお勧めします。 統合をアクティブ化する前に、目的のレポートスイートが選択されていることを確認します。 |
| Analytics変数の設定 | この統合には、カスタムイベントとカスタムeVar、およびオプションで追加のイベントと追加のeVarが必要です。 Selligent用のAnalytics変数の設定を参照してください。 |
| 認定担当者 | この統合を有効にすると、お客様の会社がAdobe, Inc.とのサービス契約またはアドビの信頼できるパートナーとのサービス契約に従って、該当する料金が発生する可能性があります。 この統合をアクティブ化すると、お客様は会社の承認された代表者であることを表します。そのため、お客様の会社は、上記のサービス契約に定める料金を支払うことに同意します。 |
| Adobe Data Warehouse™を有効にする | この統合では、リマーケティングセグメントを生成するためにData Warehouseが有効になっている必要があります。 Adobe Data Warehouseを有効にしていない場合は、アドビにお問い合わせください。 |
| 受信者 ID | 統合では、「訪問者ID」を取得し、Analytics変数(eVar)内に保存する必要があります。 訪問者ID（「受信者ID」とも呼ばれる）は、Selligentシステムからの電子メールアドレスをエンコードまたは数値で表したものです。 この「受信者ID」は、サイト上でのダウンストリーム訪問者の行動（買い物かごの放棄、購入など）に関連付けられます。Selligentシステムに取り込まれ、再マーケティングに利用できます。 セットアッププロセスの一環として、ウィザードの指示に従って、この目的のeVarを指定する必要があります。 |
| 外部トラッキング | 現在、送信する各電子メールキャンペーンに対して外部トラッキングを有効にするベストプラクティスに従っていない場合は、統合を成功させるために外部トラッキングを有効にする必要があります。 詳しくは、以下のSelligentの節を参照してください。 |
| プライバシーコンプライアンス | 受信者または訪問者IDの追跡を有効にすると、この機能でサイト訪問者の個人特定情報を追跡できることを理解する必要があります。 これは、サイト訪問者に通知したり、サイト訪問者の同意を得たりするなど、プライバシーに関して、組織が適切な手順を実行する必要があることを意味します。 |

## Selligent用のAnalytics変数の設定{#configure-analytics-variables-for-selligent}

この統合では、各レポートスイートの実装に対して2つのeVarを予約する必要があります。

これらのeVarとは別に、Selligentのデータに応じて、Analyticsで表示するいくつかのイベントが予約される場合があります。 これらのeVarおよびイベントについて、以下に説明します。

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
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> 個々の電子メールメッセージキャンペーンの識別を取り込む場合。 </td> 
   <td colname="col4"> <p><b>ステータス</b>:有効 </p> <p><b>配分</b>:最新 </p> <p><b>有効期限</b>:「ビジネス上の意思決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> 受信者 ID </td> 
   <td colname="col3"> 電子メールキャンペーンをクリックした顧客の匿名IDを取得する場合。 </td> 
   <td colname="col4"> <p><b>ステータス</b>:有効 </p> <p><b>配分</b>:最新 </p> <p><b>有効期限</b>:「ビジネス上の意思決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> Selligentから送信された電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 配信済み </td> 
   <td colname="col3"> 配信された電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 件数 </td> 
   <td colname="col3"> 表示された一意の電子メール数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Clicks </td> 
   <td colname="col3"> 電子メールがクリックされた回数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> バウンス </td> 
   <td colname="col3"> バウンスされた電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligentの前提条件{#prerequisites-for-selligent}

統合を導入する前にSelligentアカウントから提供する必要な情報が表示されます。

**有効なSelligentアカウント**

このData Connectors統合を使用するには、有効なSelligentアカウントが必要です。

**アカウント情報**

この統合のセットアップ中に、Selligentアカウントに関する次の情報が必要になります。

* **Adobe Service URL**:

   URLは、Selligent Marketingソリューションへのログオンに使用するURLから取得できます。 URLの「/simweb/login.aspx」部分を「/automation/omniture.asmx」に置き換えます。

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** クエリ文字列パラメータ：メッセージIDと受信者ID（訪問者ID）のランディングページURLに追加されます。 メッセージIDと受信者IDは、それぞれ常にMIDとRIDです。

* **統合トークン** Simweb内からManagerツールを起動し、 **[!UICONTROL Configuration]** / **[!UICONTROL System Settings]** / **[!UICONTROL General]******/System System Settingsに移動します。 「セキ **[!UICONTROL ュリティ]**」で、統合トークンを検索できます。

   ![](assets/selligent-integration_token.png)
