---
description: 統合を通じて達成されるマーケティングの効率性について説明します。
seo-description: 統合を通じて達成されるマーケティングの効率性について説明します。
seo-title: Adobe Analytics用Lyris Data Connector
solution: Analytics
title: Adobe Analytics用Lyris Data Connector
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

統合を通じて達成されるマーケティングの効率性について説明します。

Adobe® Data Connectors™の電子メール統合は、Adobe Analyticsの行動情報とLyrisの電子メールマーケティングを組み合わせて、成功指標とターゲットオーディエンスをより関連性の高いメッセージに再定義します。

これらの市場セグメントに関連する電子メールメッセージを配信すると、まったく新しい売上機会が生まれ、新規および既存の電子メールキャンペーン間のコンバージョンと売上高が増加します。 例えば、訪問中に閲覧された製品や買い物かごに置き忘れられた製品に基づく関連する電子メールメッセージを配信すると、サイトの訪問者をすでに活用しているので、コストへの影響を最小限に抑えながら、売上高に劇的な影響を与えます。

このマーケティング効率の向上は、Adobe AnalyticsとLyrisを統合する主な利点の1つです。 さらに、この統合により、クローズドループレポート用に、電子メール指標がAdobe Analyticsデータと1時間あたりの頻度で自動的に同期されます。

## 主なメリットと機能{#key-benefits-and-features}

LyrisとAdobe Marketing Reports &amp; Analyticsを統合する主な利点について説明します。

LyrisとAdobe Analyticsの統合により、次の主なメリットが得られます。

* 電子メールマーケティングと分析データを1つのレポートインターフェイスに統合
* コンバージョンや売上高やサイトの成功への貢献度によって電子メールキャンペーンを最適化する
* 動的なマーケティングセグメントに基づいて主要訪問者やマーケティングセグメントに再マーケティング

### 動的マーケティングセグメント

電子メールの統合では、ビジネスの促進に役立つ動的なマーケティングセグメントがサポートされます。 この統合では、次のマーケティングセグメントが初期設定で使用できます。

* **買い物かご放棄プロファイル**:訪問者が買い物かごを完成させるのをためらう人々に向けて特別に設計された微調整キャンペーンを通じて顧客にコンバージョンをもたらす
* **購入プロファイル**:訪問者の購入パターンによってターゲット設定されたキャンペーンを通じて、リピート注文件数と平均注文額を増やします。
* **Product/Content View Behavioral Profile**:製品表示とコンテンツアクセスプロファイルに基づくマーケティングセグメントを通じて見込み客に連絡
* また、ユーザーのニーズに合わせ **たカスタムリマーケティング** セグメントを作成し、スケジュールを設定することもできます。

## 統合の前提条件{#integration-prerequisites}

統合を成功させるための前提条件を示します。

この統合をアクティブ化する前に、Adobe Analyticsと電子メールソフトウェアのデプロイメントに対して、次の項目を確認します。

これにより、アクティブ化の前に適切なベストプラクティスと前提条件が設定され、最適で正常な統合が実現します。

### Adobe Analyticsの前提条件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **レポートスイート固有**:この統合はレポートスイートに固有であることをお勧めします。 統合をアクティブ化する前に、目的のレポートスイートが選択されていることを確認します
* **利用可能で設定済みのAnalytics変数**:この統合には、カスタムイベントとカスタムeVar、およびオプションで追加のイベントと追加のeVarが必要です。

* **Authorized Representator**:この統合を有効にすると、お客様の会社がAdobe, Inc.とのサービス契約またはアドビの信頼できるパートナーとのサービス契約に従って、該当する料金が発生する可能性があります。 この統合をアクティブ化すると、お客様は会社の承認された代表者であることを表します。そのため、お客様の会社は、上記のサービス契約に定める料金を支払うことに同意します。
* **Adobe Analytics data warehouse**:この統合では、リマーケティングセグメントを生成するために、Adobe Analyticsのdata warehouseが有効になっている必要があります。 data warehouseを有効にしていない場合は、アドビにお問い合わせください。
* **受信者ID**:統合では、「訪問者ID」を取得し、Analytics変数(eVar)内に保存する必要があります。 訪問者ID（「受信者ID」とも呼ばれる）は、Lyrisシステムからの電子メールアドレスをエンコードまたは数値で表したものです。 この「受信者ID」は、サイト上でのダウンストリーム訪問者の行動（買い物かごの放棄、購入など）に関連付けられます。これはLyrisシステムに取り込まれ、再マーケティングに利用できます。 セットアッププロセスの一環として、ウィザードの指示に従って、この目的のeVarを指定する必要があります。
* **外部トラッキング**:現在、送信する各電子メールキャンペーンに対して外部トラッキングを有効にするベストプラクティスに従っていない場合は、統合を成功させるために外部トラッキングを有効にする必要があります。 詳しくは、以下のLyrisのセクションを参照してください
* **プライバシーコンプライアンス**:受信者または訪問者IDの追跡を有効にすると、この機能でサイト訪問者の個人特定情報を追跡できることを理解する必要があります。 これは、サイト訪問者に通知を行ったり、サイト訪問者の同意を得たりするなど、組織が適切な手順を実行する必要があるというプライバシーに影響します。

### Lyris emailLabsの前提条件 {#section-84abae9401224a3699fed861f715ebde}

* **有効なLyrisアカウント**:このData Connectors統合を使用するには、有効なLyrisアカウントが必要です。
* **アカウント情報**:この統合のセットアップ中に、Lyrisアカウントに関する次の情報が必要になります。

   * *Lyris API Key*:データの入力に使用
   * *クエリ文字列パラメータ*:メッセージIDと受信者ID（訪問者ID）のランディングページURLに追加されます。
   * *Lyris Server/URL*:Lyrisシステムで使用するサーバー値
   * *Lyris Site ID*:「顧客ID」とも呼ばれ、Lyris HQのインスタンスの一意の値です。 これは、EmailLabsの「アカウントホーム」セクションの「顧客情報」にあります。

## Lyris用のAdobe Analytics変数の設定{#configure-adobe-analytics-variables-for-lyris}

各レポートスイートの実装で予約するeVarとイベントについて説明します。

この統合では、各レポートスイートの実装に対して少なくとも2つのeVarを予約する必要があります。 これらのeVarとは別に、Analyticsで表示するLyrisデータに応じて、いくつかのイベントが予約される場合があります。 以下の表に、これらのeVarとイベントを示します。

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 変数名 </th> 
   <th colname="col3" class="entry"> 変数の使用方法 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> 個々の電子メールメッセージキャンペーンの識別を取り込むには </td> 
   <td colname="col4"> <p>ステータス：有効 </p> <p>配分：最新 </p> <p>有効期限：「ビジネス上の意思決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 電子メールキャンペーンをクリックした顧客の匿名IDを取り込むには </td> 
   <td colname="col4"> <p>ステータス：有効 </p> <p>配分：最新 </p> <p>有効期限：「ビジネス上の意思決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 送信済み電子メール </td> 
   <td colname="col3"> 店番。 リリスから送られたメールの </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 開封済み電子メール </td> 
   <td colname="col3"> 店番。 開かれた電子メールの </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 開封済みの個別電子メール </td> 
   <td colname="col3"> 店番。 開かれた一意の電子メールの </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 電子メールクリックスルー </td> 
   <td colname="col3"> 店番。 電子メールがクリックされた回数 </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 電子メールのバウンス </td> 
   <td colname="col3"> ノーを保存する。 バウンスされた電子メールの </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris — 電子メール購読解除 </td> 
   <td colname="col3"> ノーを保存する。 無効にされた電子メール購読の数 </td> 
   <td colname="col4">タイプ：数値 <p>パーティシペーション：有効 </p> </td> 
  </tr> 
 </tbody> 
</table>
