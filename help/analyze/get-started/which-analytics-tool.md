---
description: このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。
title: 使用する Adobe Analytics ツールの検討
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: ht
source-wordcount: '1122'
ht-degree: 100%

---

# 使用する Adobe Analytics ツールの検討

このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。

Adobe Analytics 製品の比較について詳しくは、 [Analytics 製品の比較](/help/analyze/get-started/analytics-product-comparison.md)を参照してください。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ツールの比較](https://video.tv.adobe.com/v/30746?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## Adobe Analytics レポートユーザーインターフェイス {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** は、レポートおよび分析のあらゆるニーズに応える中心的なユーザーインターフェイスです。アドビでは、この製品への投資を続け、毎月、製品のアップデートをリリースしています。Analysis Workspace で実行できないタスクがある場合は、以下に示す他のインターフェイスを検討してください。**

**[Adobe Analytics ダッシュボード](/help/analyze/mobile-app/home.md)**&#x200B;では、モバイルで直感的なスコアカードにアクセスできます。スコアカードは、主要指標とその他のコンポーネントを並べて表示したレイアウトで構成され、タップすると、より詳細な分類やトレンドレポートを表示できます。モバイルアプリは iOS と Android の両方のオペレーティングシステムでサポートされています。

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** は、Mac、Windows、web ブラウザーで実行される Microsoft Excel のアドインです。Adobe Analytics データ（Excel ワークシートに挿入可能）からカスタムリクエストを作成できます。リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。

**[レガシー Report Builder](/help/analyze/legacy-report-builder/home.md)** は、Windows でのみ実行される Microsoft Excel のアドインです。Adobe Analytics データ（Excel ワークシートに挿入可能）からカスタムリクエストを作成できます。リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。

**[Activity Map](/help/analyze/activity-map/overview.md)** は、Adobe Analytics 内の機能で、web ページやモバイルアプリに対するユーザーエンゲージメントを視覚的に表現します。これにより、マーケターやアナリストは、クリック、ホバー、スクロール動作などのユーザーインタラクションを追跡および分析できます。

## Adobe Analytics へのデータの読み込み {#import}

**[分類](/help/components/classifications/classifications-overview.md)**&#x200B;は以下の場合に使用します。

* 収集値（eVar、プロパティ、マーケティングチャネル）に関連付けるメタデータがある場合。アドビでは、[分類セット](/help/components/classifications/sets/overview.md)の使用をお勧めします。分類ルールビルダーと分類インポーターは、分類データを Adobe Analytics に取り込む従来の方法です。

**[データソース](/help/import/data-sources/overview.md)** は以下の場合に使用します。

* Adobe Analytics に恒久的に書き込むオフラインデータがある場合。
* オプション：
   * 概要：単純なデータのアップロード（日単位または限定ディメンション）。
   * トランザクション ID：オンラインエンドポイントをオフラインデータに接続し、インポートしたデータを、オンラインでキャプチャした訪問者スナップショットに完全に関連付けるデータアップロード（例えば、注文がオンラインで完了し、オフラインで返されるなど）。

**[Adobe Exchange の統合](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;は以下の場合に使用します。

* Adobe Analytics とのサポートされる接続を構築したサードパーティプロバイダーとやり取りする場合。統合アプリは、通常、概要レベルのデータを恒久的かつ自動的に繰り返し Adobe Analytics に取り込みます。

**[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含む CSV 形式のファイルを受け付けます。アドビでは、サーバーサイドコードを必要とする実装や、データ収集に AppMeasurement や Web SDK を使用できない実装には、一括挿入 API を使用することをお勧めします。

**[データ挿入 API（レガシー）](/help/import/c-data-insertion-api/c-data-insertion-api.md)**&#x200B;は以下の場合に使用します。

* データを Adobe Analytics に取り込む必要があり、AppMeasurement、Web SDK または一括データ挿入 API を使用できない場合。

**[顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=ja)**&#x200B;は以下の場合に使用します。

* 顧客関係管理（CRM）データベースに取り込んだエンタープライズ顧客データを Experience Cloud にアップロードする場合。
* CRM データを Analytics でより詳しく分析する場合または Adobe Target のターゲティング条件として使用する場合。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** は以下の場合に使用します。

* デモグラフィック情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの Adobe Audience Manager のオーディエンスデータを任意の Analytics ワークフローに組み込む場合。
* この統合によって新しい情報が Analytics にヒットごとに送信されるので、アップロードされた CRM データを時間ベースにする場合。

## Adobe Analytics からのデータのエクスポート {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** は以下の場合に使用します。

* Workspace のカスタマイズされたレイアウトオプションが制限的である場合（Report Builder では Excel の範囲内であればどのようなレイアウトも可能）。
* ユーザー入力またはオフラインデータソース（インプレッション数、コスト）を Adobe データに緩やかに統合する場合。データを統合するためのより永続的なソリューションはデータソースです（Adobe Analytics へのデータの読み込みを参照）。
* 様々なディメンションのレポートから得られるデータの結合（例えば、プロモーションのインプレッションレポートとプロモーションのクリックトゥコンバージョンレポートの結合など）。
* 異なるレポートスイートからのデータを、同じテーブルで横に並べて合計または表示する方法で結合します。
* スケジュール設定による自動化が求められる場合（XLSX、XLSM、CSV、PDF、TXT、XML、MHT）。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** は以下の場合に使用します。

* UI に表示されない変数（IP アドレス、Experience Cloud ID、Analytics 訪問者 ID、ページの URL）へのアクセス
* UI よりも詳細なデータへのアクセス（非正規化テーブル表示）
* ピボットテーブルの入力に適した形式でのデータのダウンロード 
* 顧客が Adobe データをサードパーティ製のデータ可視化ツールに入力することを希望する場合（ヒットレベルではなく、若干要約されたデータ）
* すべての個別ディメンション項目へのアクセス（Adobe Analytics で「低トラフィック」を検出した場合）

**[Analytics データフィード](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** は、次の場合に使用します。

* アドビが提供する最も詳細なデータフィード（訪問者 ID、ヒット）の利用。
* 顧客がアドビのデータを（送信可能な最も詳細なレベルで）顧客側のデータベースに格納したい場合。
* 顧客がビジネスインテリジェンス（BI）ツールの開発を希望する場合や、ヒットレベルのアドビのデータをサードパーティ製ツールに入力しようと考えている場合。

**[レポート API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** は、その他の可視化オプションがニーズを満たさない場合に使用します。次の 3 つの API オプションがあります。

* **処理済み**：機能豊富なデータ（訪問、訪問者、セグメントなど）が必要な場合。これは典型的な Analytics UI の要約データで、30 分から 90 分で提供されます。Report Builder を通じて使用できます。
* **リアルタイム**：いくつかの指標とディメンションを数秒の待ち時間で表示させる場合。これは、限定的な、部分的に処理され要約されたデータで、30 秒以内で提供されます。最頻使用、勝者、敗者の固有アルゴリズムが含まれます。Report Builder を通じて使用できます。
* **[!UICONTROL ライブストリーム]**：部分的に処理されたヒットレベルの Analytics データのストリームを数秒以内で収集したい場合。これは部分的に処理されたデータで、30 秒以内で提供されます。Analytics Premium でのみ使用可能です。データを可視化する何らかの方法が必要になります。通常は、エンジニアリングサービスを使用しておこないます。

## カスタムソリューション {#custom-solutions}

エンジニアリングサービスは、次のような場合に使用します:

* その他のアドビツールではニーズが満たされない。
* カスタムエクスペリエンスが必要。
* 完全に自動化されたソリューションを求めている。
* 多くのデバイスにリーチしたい。
* 複数のデータソースがある。
* 複雑なデータの ETL（抽出-変換-読み込み）に関する要件がある。
* カスタムブランディングが必要。
* [!UICONTROL Analytics ライブストリーム]の可視化が必要。
