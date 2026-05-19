---
description: このヘルプページには、各Adobe Analytics ツールの推奨されるユースケースが含まれています。 ツールは、リストされている順序で考慮する必要があります。 特定のツールが要件を満たさない場合は、次のツールに移行して検討します。
title: 使用する Adobe Analytics ツールの検討
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 61%

---

# 使用する Adobe Analytics ツールの検討

このヘルプページには、各Adobe Analytics ツールの推奨されるユースケースが含まれています。 ツールは、リストされている順序で考慮する必要があります。 特定のツールが要件を満たさない場合は、次のツールに移行して検討します。

Adobe Analytics 製品の比較について詳しくは、 [Analytics 製品の比較](/help/analyze/get-started/analytics-product-comparison.md)を参照してください。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ツールの比較](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## Adobe Analytics レポートユーザーインターフェイス {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** は、レポートおよび分析のあらゆるニーズに応える中心的なユーザーインターフェイスです。 アドビでは、この製品への投資を続け、毎月、製品のアップデートをリリースしています。 Analysis Workspace で実行できないタスクがある場合は、以下に示す他のインターフェイスを検討してください。**

**[Adobe Analytics ダッシュボード](/help/analyze/mobile-app/home.md)**&#x200B;では、モバイルで直感的なスコアカードにアクセスできます。 スコアカードは、主要指標とその他のコンポーネントを並べて表示したレイアウトで構成され、タップすると、より詳細な分類やトレンドレポートを表示できます。 モバイルアプリは iOS と Android の両方のオペレーティングシステムでサポートされています。

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** は、Mac、Windows、web ブラウザーで実行される Microsoft Excel のアドインです。 Adobe Analytics データ（Excel ワークシートに挿入可能）からカスタムリクエストを作成できます。 リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。

**[レガシー Report Builder](/help/analyze/legacy-report-builder/home.md)** は、Windows でのみ実行される Microsoft Excel のアドインです。 Adobe Analytics データ（Excel ワークシートに挿入可能）からカスタムリクエストを作成できます。 リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。

**[Activity Map](/help/analyze/activity-map/overview.md)** は、Adobe Analytics 内の機能で、web ページやモバイルアプリに対するユーザーエンゲージメントを視覚的に表現します。 これにより、マーケターやアナリストは、クリック、ホバー、スクロール動作などのユーザーインタラクションを追跡および分析できます。

## Adobe Analytics へのデータの読み込み {#import}

**[分類](/help/components/classifications/classifications-overview.md)**&#x200B;は以下の場合に使用します。

* 収集値（eVar、プロパティ、マーケティングチャネル）に関連付けるメタデータがある場合。 アドビでは、[分類セット](/help/components/classifications/sets/overview.md)の使用をお勧めします。 分類ルールビルダーと分類インポーターは、分類データを Adobe Analytics に取り込む従来の方法です。

**[データソース](/help/import/data-sources/overview.md)** は以下の場合に使用します。

* Adobe Analytics に恒久的に書き込むオフラインデータがある場合。
* オプション：
   * 概要：日またはディメンションを限定したシンプルなデータアップロード
   * トランザクション ID：オンラインエンドポイントとオフラインデータを接続し、インポートしたデータをオンラインでキャプチャされた訪問者のスナップショットに完全に関連付けるデータのアップロード（オンラインで注文が完了し、オフラインで返品される）

**[Adobe Exchange の統合](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;は以下の場合に使用します。

* Adobe Analytics とのサポートされる接続を構築したサードパーティプロバイダーとやり取りする場合。 統合アプリは、通常、概要レベルのデータを恒久的かつ自動的に繰り返し Adobe Analytics に取り込みます。

**[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含む CSV 形式のファイルを受け付けます。 アドビでは、サーバーサイドコードを必要とする実装や、データ収集に AppMeasurement や Web SDK を使用できない実装には、一括挿入 API を使用することをお勧めします。

**[データ挿入 API（レガシー）](/help/import/c-data-insertion-api/c-data-insertion-api.md)**&#x200B;は以下の場合に使用します。

* データを Adobe Analytics に取り込む必要があり、AppMeasurement、Web SDK または一括データ挿入 API を使用できない場合。

**[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=ja)**&#x200B;は以下の場合に使用します。

* 顧客関係管理（CRM）データベースに企業の顧客データを取り込み、CX Enterpriseにデータをアップロードする場合。
* Adobe AnalyticsでCRM データをより詳細に分析したり、Adobe Adobe Targetのターゲティング基準として使用したい場合。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** は以下の場合に使用します。

* デモグラフィック情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの Adobe Audience Manager のオーディエンスデータを任意の Analytics ワークフローに組み込む場合。
* アップロードされたCRM データを時間ベースにする場合は、ヒットしたAnalyticsに新しい情報が送信されます。

## Adobe Analyticsからのデータのエクスポート {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** は以下の場合に使用します。

* Workspaceのカスタマイズされたレイアウトオプションが制限されている場合（Excelの制限内で、Report Builderで可能なことはすべて可能）。
* ユーザー入力またはオフラインデータソース（インプレッション数、コスト）を Adobe データに緩やかに統合する場合。 データを統合するためのより永続的なソリューションはデータソースです（Adobe Analytics へのデータの読み込みを参照）。
* 様々なディメンションのレポートから得られるデータの結合（例えば、プロモーションのインプレッションレポートとプロモーションのクリックトゥコンバージョンレポートの結合など）。
* 異なるレポートスイートからのデータを、同じテーブルで横に並べて合計または表示する方法で結合します。
* スケジュール設定による自動化が求められる場合（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** は以下の場合に使用します。

* UI に表示されない変数（IP アドレス、Experience Cloud ID、Analytics 訪問者 ID、ページの URL）へのアクセス
* UI （非正規化テーブルビュー）よりも詳細なデータにアクセスするには
* ピボットテーブル入力に適した形式でデータをダウンロードするには
* クライアントがAdobe データをサードパーティのデータビジュアライゼーションツールに入力する場合（少し要約し、ヒットレベルではない）
* すべての個別ディメンション項目へのアクセス（Adobe Analytics で「低トラフィック」を検出した場合）

**[Analytics データフィード](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** は、次の場合に使用します。

* （訪問者ID、ヒット）提供できる最も詳細なデータフィードを活用します。
* クライアントがクライアントサイドデータベースにAdobe データを保存する必要がある場合は、最も詳細なレベルで送信できます。
* クライアントがBusiness Intelligence（BI）ツールの開発や、ヒットレベルのAdobeデータをサードパーティのツールに入力する場合。

**[レポート API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** は、その他の可視化オプションがニーズを満たさない場合に使用します。 3つのAPI オプションには、次のものが含まれます。

* **完全処理**：豊富な機能を備えたデータ（訪問、訪問者、セグメントを含む）が必要な場合。 これは一般的なAnalytics UIの要約データで、30～90分以内に利用できます。 Report Builderで使用できます。
* **リアルタイム**：数秒の遅延を含むいくつかの指標とディメンションを表示する場合。 これは、30秒以内に利用可能な、部分的に処理された要約データです。 最も人気のあるゲーム、勝者、敗者から成る独自のアルゴリズムが含まれています。 Report Builderで使用できます。
* **[!UICONTROL ライブストリーム]**：部分的に処理されたヒットレベルの Analytics データのストリームを数秒以内で収集したい場合。 これは部分的に処理されたデータで、約30秒以内に利用できます。 Analytics Premiumでのみ使用できます。 データを視覚化する何らかの方法が必要です（通常はエンジニアリングサービスエンゲージメントを通じて）。

## カスタムソリューション {#custom-solutions}

エンジニアリングサービスは、次のような場合に使用します:

* その他のアドビツールではニーズが満たされない。
* 顧客が求めるカスタム体験を。
* 完全に自動化されたソリューションが必要です。
* さまざまなデバイスにリーチする必要があります。
* 複数のデータソースがある場合：
* 複雑なデータ ETL （Extract-Transform-Load）要件があります。
* カスタムブランディングが必要です。
* [!UICONTROL Analytics ライブストリーム &#x200B;]を視覚化します。
