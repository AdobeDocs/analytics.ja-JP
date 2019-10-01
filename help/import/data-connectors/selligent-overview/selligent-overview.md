---
description: 'null'
seo-description: 'null'
seo-title: Selligent Data Connector for Adobe Analytics
solution: Analytics
title: Selligent Data Connector for Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

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
| 認定担当者 | この統合を有効にすると、お客様の会社がAdobe, Inc.とのサービス契約またはアドビの信頼できるパートナーとのサービス契約に従って、該当する料金が発生する可能性があります。 By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above. |
| Adobe Data Warehouse™を有効にする | This integration requires the Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled the Adobe Data Warehouse, contact Adobe for details. |
| Recipient ID | The integration requires that we capture and store a "Visitor ID" within a Analytics variable (eVar). The Visitor ID (often referred to as the "Recipient ID") is an encoded or numeric representation of an email address from the Selligent system. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled back into the Selligent system and can be leveraged for remarketing purposes. As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard. |
| External Tracking | If you’re not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Selligent section below for details. |
| Privacy Compliance | You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors. |

## Selligent用のAnalytics変数の設定{#configure-analytics-variables-for-selligent}

This integration requires 2 eVars to be reserved for each report suite implementation.

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
   <td colname="col2"> Recipient ID </td> 
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
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>Participation: Enabled</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerequisites for Selligent{#prerequisites-for-selligent}

Lists the necessary information to supply from your Selligent account before you can deploy the integration.

**Valid Selligent Account**

In order to use this Data Connectors integration, you must have a valid Selligent account.

**アカウント情報**

You will require the following information about your Selligent account during this integration setup:

* **Adobe Service URL:**

   The URL can be derived from the URL used to log on to the Selligent Marketing solution. Replace the “/simweb/login.aspx” part of the url with “/automation/omniture.asmx”

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** Query String Parameters: These are appended in the landing page URL for Message ID and Recipient ID(Visitor ID). These are always MID and RID for Message ID and Recipient ID respectively.

* **Integration Token Launch the Manager tool from inside Simweb and go to Configuration &gt; System Settings &gt; General tab &gt; System.****************** Under Security, you can find the Integration token.****

   ![](assets/selligent-integration_token.png)
