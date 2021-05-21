---
description: このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。
title: 使用する Adobe Analytics ツールの検討
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '1162'
ht-degree: 100%

---

# 使用する Adobe Analytics ツールの検討

このヘルプページでは、各 Adobe Analytics ツールの推奨される使用例が紹介されています。ここにリストされている順にツールを検討するとよいでしょう。あるツールがニーズを満たさない場合は、次のツールの使用を検討します。

Adobe Analytics の製品比較について詳しくは、[こちら](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md)を参照してください。

## Adobe Analytics レポートユーザーインターフェイス {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** は、レポートおよび分析のあらゆるニーズに応える中心的なユーザーインターフェイスです。アドビでは、この製品への投資を続け、毎月、製品のアップデートをリリースしています。Analysis Workspace で実行できないタスクがある場合は、以下に示す他のインターフェイスを検討してください。**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** は以下の場合に使用します。

* ナビゲーションが容易な作成済みのレポートにアクセスする必要がある初心者ユーザーの場合。
* UI でリアルタイムデータにアクセスする。
* カレンダーイベントをセットアップする。
* ターゲットをセットアップする。
* ボットレポートを表示する。
* ビデオ視聴時間帯、ビューアドロップオフの独自のビデオビジュアライゼーションにアクセスする。
* 予定レポートで発行リストを活用する。

**[Data Workbench](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/home.html)** は以下の場合に使用します。

* 柔軟性の最も高い Analytics ツールとして使用（訪問者レベル、ヒットレベル分析に至るまで対応）。
* CRM から POS さらに Web へのオンラインおよびオフラインインタラクションのマルチチャネルデータセットを作成する。
* 高度なアトリビューション（ルールベースモデルおよびアルゴリズムモデル）。
* 予測、統計的モデリング（傾向スコアリング、クラスタリング、相関関係など）。
* 待ち時間分析（イベント前後の時間）。
* Adobe Experience Cloud 全体での複雑なセグメントの識別およびエクスポート。

## Adobe Analytics へのデータのインポート {#import}

**[分類](/help/components/classifications/c-classifications.md)** は以下の場合に使用します。

* 収集値（eVar、プロパティ、マーケティングチャネル）に関連付けるメタデータがある場合。
* オプション：

   * ルールビルダー：変数に収集中の書式設定された予測可能な値（例えば、区切り値など）がある場合に使用します。このアプローチでは、ルールを一度設定したら、後はほとんど自動化できます。
   * ブラウザーインポーター：予測可能な値がない場合か、1 回限りの更新が必要な有限の値リストがある場合に使用します。このアプローチでは、新しい値の分類を継続的に監視する必要があります。

**[データソース](/help/import/c-data-sources/datasrc-home.md)** は以下の場合に使用します。

* Adobe Analytics に恒久的に書き込むオフラインデータがある場合。
* オプション：

   * 概要：単純なデータのアップロード（日単位または限定ディメンション）。
   * トランザクション ID：オンラインエンドポイントをオフラインデータに接続し、インポートしたデータを、オンラインでキャプチャした訪問者スナップショットに完全に関連付けるデータアップロード（例えば、注文がオンラインで完了し、オフラインで返されるなど）。
   * フル処理：タイムスタンプ付きのデータソース。Adobe サーバーで収集されたヒットのように処理されます。つまり、データが訪問者のジャーニーに直接挿入されます。

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)** は以下の場合に使用します。

* Adobe Analytics とのサポートされる接続を構築したサードパーティプロバイダーとやり取りする場合。Data Connectors は、通常、サマリレベルのデータを、定期的、恒久的かつ自動的に Adobe Analytics に取り込みます。

**[Data Insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md)** は以下の場合に使用します。

* データを Adobe Analytics にアップロードする必要があるときに Adobe AppMeasurement またはモバイル SDK コードを使用できない場合。

**[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* データ挿入 API と一括データ挿入 API はどちらも、サーバーサイドの収集データを Adobe Analytics に送信する手段です。 データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含んだ CSV 形式のファイルを受け付けます。 サーバーサイド収集の新しい実装に取り組む場合は、一括データ挿入 API を使用することをお勧めします。

**[顧客属性](https://docs.adobe.com/content/help/ja-JP/core-services/interface/customer-attributes/attributes.html)** は以下の場合に使用します。

* 顧客関係管理（CRM）データベースに取り込んだエンタープライズ顧客データを Experience Cloud にアップロードする場合。
* CRM データを Analytics でより詳しく分析する場合または Adobe Target のターゲティング条件として使用する場合。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** は以下の場合に使用します。

* 人口統計情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの Adobe Audience Manager（AAM）のオーディエンスデータを任意の Analytics ワークフローに組み込む場合。
* この統合によって新しい情報が Analytics にヒットごとに送信されるので、アップロードされた CRM データを時間ベースにする場合。

## Adobe Analytics からのデータのエクスポート {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** は以下の場合に使用します。

* Workspace のカスタマイズされたレイアウトオプションが制限的である場合（Report Builder では Excel の範囲内であればどのようなレイアウトも可能）。
* ユーザー入力またはオフラインデータソース（インプレッション数、コスト）を Adobe データに緩やかに統合する場合。データを統合するためのより恒久的なソリューションはデータソースです（「Adobe Analytics へのデータのインポート」を参照）。
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

エンジニアリングサービスは、次のような場合に使用します：

* その他のアドビツールではニーズが満たされない。
* カスタムエクスペリエンスが必要。
* 完全に自動化されたソリューションを求めている。
* 多くのデバイスにリーチしたい。
* 複数のデータソースがある。
* 複雑なデータの ETL（抽出-変換-読み込み）に関する要件がある。
* カスタムブランディングが必要。
* [!UICONTROL Analytics ライブストリーム]の可視化が必要。
