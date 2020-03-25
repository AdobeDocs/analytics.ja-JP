---
description: このヘルプページには、各Adobe Analyticsツールの推奨される使用例が含まれています。 ツールは、リストに表示される順に考慮する必要があります。 特定のツールがニーズを満たさない場合は、次のツールに移って検討します。
title: 使用する Adobe Analytics ツールの検討
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# 使用する Adobe Analytics ツールの検討

このヘルプページには、各Adobe Analyticsツールの推奨される使用例が含まれています。 ツールは、リストに表示される順に考慮する必要があります。 特定のツールがニーズを満たさない場合は、次のツールに移って検討します。

Adobe Analytics製品の比較について詳しくは、こちらを参照してく [ださい](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md)。

## Adobe Analytics レポートユーザーインターフェイス {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**は、レポートおよび分析のあらゆるニーズに応える中心的なユーザーインターフェイスです。アドビでは、この製品への投資を続け、毎月、製品のアップデートをリリースしています。Analysis Workspace で実行できないタスクがある場合は、以下に示す他のインターフェイスを検討してください。**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**は以下の場合に使用します。

* ナビゲーションが容易な作成済みのレポートにアクセスする必要がある初心者ユーザーの場合。
* Targetアクティビティ(Analytics for Target/A4T)の上昇率と信頼性を理解するため。
* UIのリアルタイムデータにアクセスする。
* カレンダーイベントを設定するには
* ターゲットを設定するにはを参照してください。
* ボットレポートを表示します。
* 同時ビューア、ビデオ視聴時間帯、ビューアドロップオフの個別のビデオビジュアライゼーションにアクセスするには
* スケジュールされたレポートで発行リストを活用する場合。

**[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**は以下の場合に使用します。

* モバイルアプリデータのサイロ表示が必要な場合。
* モバイルアプリSDKの実装を管理する場合。
* アプリ内メッセージ、プッシュメッセージ、場所のターゲット設定など、モバイル広告を設定する場合。
* アプリデータ（サンバースト）に対して、よりインタラクティブなビジュアライゼーションが必要な場合。
* 地図上の目標点を可視化する。
* 全期間値指標の場合。

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**は以下の場合に使用します。

* 50,000行のデータをエクスポートするには
* プロジェクト作業のタブ構成が必要な場合。
* サイト分析レポート（3Dパスレポート）を使用する場合。

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**は以下の場合に使用します。

* 最も柔軟性の高いAnalyticsツールオプション（訪問者レベルのヒットレベルの分析まで）
* CRMからPOSからWebへのオンラインおよびオフラインのインタラクションのマルチチャネルデータセットを作成する場合。
* 高度なアトリビューション（ルールベースおよびアルゴリズムモデル）。
* 予測、統計モデリング（傾向スコアリング、クラスタリング、相関関係など）。
* 待ち時間分析（イベントの前/後の時間）。
* Adobe Experience Cloud全体での複雑なセグメントの識別と書き出し。

## Adobe Analyticsへのデータのインポート {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[分類](/help/components/c-classifications2/c-classifications.md)**は以下の場合に使用します。

* 収集値（eVar、prop、マーケティングチャネル）に関連付けるメタデータがある場合
* オプション:

   * ルールビルダー：変数（区切り値など）に対して予測可能な形式設定値が収集されている場合に使用します。 このアプローチを使用すると、一度ルールを設定し、そのほとんどを「設定し忘れる」ことができます。
   * ブラウザーインポーター：予測可能な値がない場合か、1 回限りの更新が必要な有限の値リストがある場合に使用します。このアプローチでは、新しい値の分類を継続的に監視する必要があります。

**[データソース](/help/import/c-data-sources/datasrc-home.md)**は以下の場合に使用します。

* Adobe Analytics に恒久的に書き込むオフラインデータがある場合
* オプション:

   * 概要：日別または限られたディメンション別の単純なデータのアップロード
   * トランザクションID:オンラインエンドポイントをオフラインデータに接続し、インポートしたデータをオンラインでキャプチャした訪問者スナップショットに完全に関連付けるデータアップロード（例：オンラインでの注文が完了し、オフラインで返される）
   * フル処理：タイムスタンプ付きのデータソース。アドビのサーバーによって収集されたヒットとして処理されます。 つまり、データが訪問者の遍歴に直接挿入されます。

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)（以前の Genesis）**は以下の場合に使用します。

* Adobe Analyticsとのサポート対象の接続を構築したサードパーティプロバイダーと連携する場合。 通常、Data Connectorsは、定期的に、概要レベルのデータを永続的かつ自動的にAdobe Analyticsに組み込みます。

**[Data Insertion API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**は以下の場合に使用します。

* データを Adobe Analytics にアップロードする必要があるときに Adobe AppMeasurement またはモバイル SDK コードを使用できない場合。

**[顧客属性](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**は以下の場合に使用します。

* 企業の顧客データを顧客関係管理(CRM)データベースに取り込み、そのデータをExperience Cloudにアップロードする場合。
* Analyticsでの詳細な分析や、Adobe Targetでのターゲット条件としてCRMデータを使用する場合。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**は以下の場合に使用します。

* 人口統計情報（性別や所得レベルなど）、心理図情報（興味や趣味など）、CRMデータ、広告インプレッションデータなどのAdobe Audience Manager(AAM)オーディエンスデータをAnalyticsワークフローに組み込む場合。
* アップロードしたCRMデータを時間ベースにする場合は、この統合によってヒットによってAnalyticsに新しい情報が送信されます。

## Adobe Analyticsからのデータの書き出し {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**は以下の場合に使用します。

* Workspaceのカスタマイズされたレイアウトオプションが制限されている場合（Report Builderでは、Excelの制限内であれば何でも可能）。
* ユーザー入力またはオフラインデータソース（インプレッション数、コスト）を Adobe データに緩やかに統合する場合。データを統合するためのより恒久的なソリューションはデータソースです（「Adobe Analytics へのデータのインポート」を参照）を参照してください。
* 様々なディメンションレポート（例えば、プロモーションインプレッションレポートとプロモーションクリックトゥコンバージョンレポートを結合）からのデータを結合する。
* クロスレポートスイートビューの場合。
* スケジュールによる自動化が必要な場合(XLSX、XLSM、CSV、PDF、TXT、XML、MHT)。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**は以下の場合に使用します。

* UI に表示されない変数（IP アドレス、Experience Cloud ID、Analytics 訪問者 ID、ページの URL）へのアクセス
* UIよりも詳細なデータにアクセスするには（非正規化テーブル表示）
* ピボットテーブルの入力に適した形式でデータをダウンロードするには
* クライアントがアドビのデータをサードパーティのデータ視覚化ツール（ヒットレベルではなく、若干要約されたもの）に入力する場合
* すべての個別ディメンション値へのアクセス（Adobe Analytics で「低トラフィック」を検出した場合）

**[Analytics データフィード](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**は、次の場合に使用します。

* 提供できる最も詳細なデータフィード（訪問者ID、ヒット）を利用する。
* クライアント側のデータベースにアドビのデータを保存したい場合は、送信できる最も詳細なレベルで保存します。
* 顧客がビジネスインテリジェンス(BI)ツールを開発したり、ヒットレベルのアドビデータをサードパーティのツールに入力したい場合。

**[レポート API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**は、その他の可視化オプションがニーズを満たさない場合に使用します。次の3つのAPIオプションがあります。

* **処理済み**:機能豊富なデータ（訪問、訪問者、セグメントを含む）を必要とする場合。 これは一般的なAnalytics UIの要約データで、30 ～ 90分以内に利用できます。 Report Builderを通じて使用できます。
* **リアルタイム**:」をクリックします。 これは、30秒以内に利用可能な、部分的に処理され要約されたデータに制限されます。 最も人気のある、勝者、敗者の固有アルゴリズムが含まれます。 Report Builderを通じて使用できます。
* **[!UICONTROL Live Stream]**:部分的に処理されたヒットレベルのAnalyticsデータを数秒以内に収集する場合。 これは部分的に処理されたデータで、30秒以内に提供されます。 Analytics Premiumでのみ使用できます。 データを視覚化する方法が必要です。通常、エンジニアリングサービスの関与を通じて使用します。

## カスタムソリューション {#section_4A212F26A15947599DFB0399A0440CB6}

エンジニアリングサービスは、次のような場合に使用します：

* その他のアドビツールではニーズが満たされない。
* カスタムエクスペリエンスが必要。
* 完全に自動化されたソリューションが必要です。
* 多くのデバイスにアクセスしたい。
* 複数のデータソースがある。
* 複雑なデータETL(Extract-Transform-Load)要件がある。
* カスタムブランドを使用する。
* 視覚化したい [!UICONTROL Analytics Live Stream]。
