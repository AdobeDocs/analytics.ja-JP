---
description: このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。
title: Adobe Analytics - 主要概念
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics - 主要概念

このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 製品 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| Analysis Workspace | 堅牢なカスタム分析プロジェクトを構築し、インサイトを民主化するためのブラウザーソリューション。 Reports &amp; Analyticsよりも柔軟にレポートを作成できる | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Reports &amp; Analytics（旧称 SiteCatalyst） | レポートおよび分析のためのブラウザーソリューション。 Analytics パッケージのスターターツールです。 | [Reports &amp; Analyticsホーム](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Adobe Analyticsデータからカスタマイズしたリクエストを作成し、Microsoft excelを使用して視覚化できるExcelアドインです。 | [Report Builderホーム](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis（旧称 Discover） | 高度なデジタル分析を行うJavaベースのツール。 | [Ad Hoc Analysisホーム](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench（旧称 Insight） | 複数チャネルに渡るオンラインとオフラインの両方の顧客インタラクションから、データの収集、処理、分析、視覚化を行うよう設計されています。 | [Data Workbench クライアント](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 保存用およびデータをフィルタリングして実行できるカスタムレポート用の、生の処理されていないデータです。ヒットレベルではありません。 | [Data Warehouseホーム](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | アプリ用の各ソリューションが Adobe Experience Cloud 上で統合されます。これにより、アプリの利用状況を把握し、改善につなげることができます。 | [Mobile Servicesホーム](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（旧称Genesis） | サードパーティのアプリケーションからAnalyticsにトラッキングデータをインポートし、一元的なパフォーマンスをエンドツーエンドで把握できるようにします。 | [Data Connectorsホーム](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management（DTM） | Analytics、Target およびその他のタグを、ドメイン数にかかわらず、すべてのサイトにわたって管理できます。 | [DTMホーム](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | アドビが提供する次世代のWebサイトタグおよびモバイルSDK管理機能。 | [Adobe Launchホーム](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

追加された Adobe Analytics の用語集を参照するには、[ここをクリック](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)してください。

| 用語 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| prop（カスタムトラフィック） | ページごとのサイトトラフィックアクティビティの追跡に使用されるディメンション。 prop はページをまたいで保持されません。トラフィック変数の主要な用途を次に示します。 <ul><li>特定の値の「最頻使用」を見つける単純なカウント</li><li>ユーザがサイト内をどのように移動しているかを把握する </li></ul><br>トラフィック変数の例：ページ名、サイトセクション、ブラウザ</br> | [prop](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar （カスタムコンバージョン） | カスタマイズされた一定期間持続するディメンション。 有効期限オプションには、イベントの有効期限、訪問の有効期限、または X-day 有効期限が含まれ、該当の変数で実行される分析のタイプによって決定します。<br>eVarとpropの主な違い：</br><ul><li>永続性は削除されるので、propはパス分析によく使用されます。</li><li>eVarは、多くの場合、コンバージョン分析に使用されます。</li></ul><br>コンバージョン変数の例を次に示します。内部検索用語、内部プロモーション、外部キャンペーン(s.campaign)</br> | [eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| イベント/指標(s.events) | 訪問者がサイトでとるべき主要なアクションを測定する指標。 イベントには、カウンター、数値、通貨の 3 タイプがあります。イベントは、コンバージョン変数（eVar）レポートに追加すると便利です。eVar は発生した内容に関する定性的情報を提供し、イベントは発生した内容に関する定量的情報を提供します。<br>eVarとイベントの主な違い：</br><ul><li>eVarは、コンバージョンに影響を与えたユーザー、対象、または対象を示します。</li><li>イベントは、発生したコンバージョンの数を測定します。</li></ul><br>コンバージョンイベントの例には、購入回数、アプリケーション開始、リード、売上高があります。</br> | [イベント](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| コンポーネント | プロジェクトにドラッグ&amp;ドロップできるディメンション、指標、セグメントおよび時間の精度（日付範囲）。 | [コンポーネント](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| ディメンション | eVar、prop、分類およびアドビの標準収集値のコレクション。 | [ディメンション](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 指標 | 実装されたイベントと計算指標のコレクション。 | [指標](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 計算指標 | 実装を通じて取り込まれた既存の指標からカスタム指標を導き出す機能。 | [計算指標](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| セグメント | 強力かつ重要な閲覧者セグメントを作成、管理、共有し、Analytics レポートに適用できます。セグメントは Analytics 製品全体で共有されます。また、Experience Cloud 全体で共有することができます。 | [セグメント化](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 時間（日付範囲） | 任意の期間に対して日付をフィルタリングし、分析で再利用できるカスタム日付範囲を作成できます。 | [日付範囲](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| ビジュアライゼーション | プロジェクトでデータを活用するのに役立つ、豊富なビジュアル。 | [ビジュアライゼーション](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| キュレーション | プロジェクトまたは仮想レポートスイートでアクセス可能なコンポーネントを制限する機能。 | [VRS](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[curationProject](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[curationComparison](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## 主要レポート

| レポート | 説明 | ドキュメントリンク |
|--- |--- |--- |
| 全ディメンション／レポートのリスト | Adobe Analytics で使用できる全ディメンション／レポートの定義。 | [ディメンション](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | Adobe Analytics内で、GoogleおよびBingのすべての有料検索データを並べて分析します。 統合を通じて作成されるディメンションには、広告プラットフォーム、キーワード、一致タイプなどがあります。 作成される指標は、AMOインプレッション数、AMOクリック数、AMOコスト、平均 掲載順位と平均 品質スコアごとの内訳を示す自由形式の表。 | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | ユーザーのAAMのオーディエンスメンバーシップでAnalyticsの受信ヒットをエンリッチします。 人口統計情報（性別や所得レベルなど）、心理図情報（興味や趣味など）、CRMデータ、広告インプレッションデータなどのAAMオーディエンスデータを、Analyticsワークフローに組み込むことができます。 この統合によって作成されるディメンションは、オーディエンスIDとオーディエンス名です。 | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | 顧客の遍歴にわたって意味のあるエンゲージメントがどのように行われるかを把握し、顧客が成果をターゲットに導く変曲ポイントをインテリジェントに特定し、マーケティングイニシアチブを効果的に最適化できます。 モデルには、first、last、linear、participation、j形、inverse j形、u形、same touch、custom、time decayが含まれます。 | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| 異常値検出 | 以前のデータに関連して特定の指標がどのように変化したかを判断する統計的手法。 ADは、Analysis Workspaceのすべてのトレンドビジュアライゼーションでデフォルトでオンになっています。 | [異常値検出](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| 貢献度分析 | アクセス権を持つすべての指標およびディメンションの自動分析を実行することで、発生する異常値の「なぜ」を調べます。 | [貢献度分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| コホート分析 | コホートとは、特定の期間に共通の特性を共有する人のグループです。 コホート分析は、ユーザーの保持率と傾向を分析する際に役立ちます。 | [コホート分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| 顧客の遍歴レポート | ユーザーがサイトまたはアプリを通ってたパスに関する情報を表示します。 Analysis Workspaceのこの分析では、prop、eVarおよびイベントを使用できます。 | [Analysis Workspace FalloutAnalysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[FlowReports &amp; Analyticsのパス](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| マーケティングチャネル | ユーザーをサイトに誘導する外部チャネルや、コンバージョンに最も効果があるチャネルを確認するのに役立つレポートです。ファーストタッチおよびラストタッチの属性ビューが提供されます。これは、有料チャネルと自然チャネルの両方において最も包括的なビューなので、Adobe Analytics で（キャンペーンやトラフィックソースよりも）推奨される外部トラフィックソースレポートです。 | [マーケティングチャネル](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| モバイル | モバイルデバイスまたはタブレットからアクセスされた Web サイトの情報を表示します。 | [モバイルレポート | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| モバイルアプリ | モバイルアプリに関する基本的な使用状況の情報を表示します。これらのレポートは、SDK が導入され、レポートが有効になると使用できます。さらに、Adobe Mobile Services によって、より包括的なアプリデータを提供する個別のモバイルアプリインターフェイスが作成されました。これにより、アプリの利用状況を把握し、改善につなげることができます。インターフェイスにア [クセス](https://mobilemarketing.adobe.com)。 | [Adobe Mobile サービス](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | 製品 | 売上高やチェックアウト数など各種コンバージョン指標に対する個々の商品や商品グループ（カテゴリ）の貢献を明らかにできます。 | [製品レポート](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| セグメント比較 | アクセス権を持つすべての単一の指標およびディメンションを自動分析することで、セグメント間の最も大きな統計的差異を見つけます。 | [セグメント比較](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| サイトコンテンツレポート | サイトで最もアクティブなページや領域、および最もよく利用されているサーバーに関する情報が表示されます。 | [サイトコンテンツレポート](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| サイト指標レポート | 実訪問者数、購入回数、売上高などの Web サイトの定量的情報を表示します。各指標は、他の項目ベースレポートに配置できます。 | [サイト指標レポート](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| 訪問者プロファイル | 国、州、郵便番号コードおよびドメインなどの各種プロファイルカテゴリから、顧客の購入パターンを確認するのに役立つレポートです。 | [訪問者プロファイル](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| 訪問者保持率 | 訪問者がサイトに再訪問した回数や頻度など、顧客忠誠度についての情報を表示します。 | [訪問者保持率](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| プロジェクトリンク、共有、スケジュール | 他の Analytics インターフェイスで作業内容を保存および他者と共有するための方法です。 | [ファイルの送信とスケジュール](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 指標名 | 定義 | ドキュメントリンク |
|---|---|---|
| 全指標のリスト | Adobe Analytics の全指標の定義。 | [指標の概要](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| 実訪問者数 | 特定期間における Web サイトへの重複なしの訪問者数。 | [実訪問者数](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| 訪問回数 | 1 回のランディングでの一連のページビュー。訪問は、ユーザーが最初にサイトのページを表示したときに開始し、非アクティブ状態が 30 分続いた後に終了します。 | [訪問回数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| ページビュー数 | ページビューは、訪問者が Web サイトのページを表示したときに発生します。 | [ページビュー数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| インスタンス | 変数が定義された回数。Adobe Analytics に変数内の値が表示されるたびに、それぞれのレポートでインスタンスが 1 つずつ増分します。 | [インスタンス](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| 発生件数 | 変数が定義または持続された回数。 | [発生件数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## インポート オプション {#concept_7C6DF03B5F9149E2A77F36C739432059}

| オプション | 説明 | ドキュメントリンク |
|---|---|---|
| 分類インポーター | ブラウザーまたは FTP アップロードを介して、メタデータを取得したディメンションに対してインポートします。ルールビルダーとは異なり、手動で操作します。 | [分類インポーター](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| ルールビルダー | ユーザー定義のルールに基づき、メタデータ分類を自動的に作成します。 | [分類ルールビルダー](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| 顧客属性 | Experience cloudにアップロードされたCRMデータを、Adobe AnalyticsおよびAdobe targetで使用できるようにします。 | [顧客属性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| データソース | ディメンションに対して、または単に日別に、オフライン指標をAnalyticsにインポートします。 | [データソース](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange Data Connectors | 詳しくは、 [Analyticsツールを参照してください](/help/landing/an-key-concepts.md) |  |
| ネイティブ統合 | Audience Analytics &amp; Advertising Analyticsを参照してください。 | 「主要レポート」の節を参照してください。 |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| オプション | 説明 | ドキュメントリンク |
|---|---|---|
| UIのダウンロードとスケジュール | Analysis WorkspaceからのデータのCSVまたはPDFとしてのエクスポート | [PDF ファイルまたは CSV ファイルのダウンロード](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Analyticsツールを参照してください。 |
| Analytics API | Analytics データの自分用のカスタマイズクエリを作成します。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Analyticsツールを参照してください。 |  |
| Analytics データフィード | Analytics から最も詳細なデータを取得する方法です。Analytics からヒットレベルフィードを設定します。 | [Analytics データフィード](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 手段／リソース | 説明 | ドキュメントリンク |
|--- |--- |--- |
| 開発者向けリソース | 利用可能なすべてのプラットフォーム（Web、モバイルアプリ、ビデオ、Flash など）の Analytics データの収集で利用可能なライブラリについて概説したドキュメント。 | [開発者向けドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 導入ガイド | データ収集変数の説明と、JavaScript でのデータ収集コードの導入についての詳細。 | [導入ガイド](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| AppMeasurement（s_code） | グローバル変数管理 | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| App SDK | アプリの設定ファイルの事前収集バージョンを含むカスタマイズされたパッケージ。 | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTMとAdobe Launch | Analyticsツールを参照してください。 |  |
| VISTA | サーバー側のロジックを適用して、データの収集時にデータを変更またはセグメント化できます。 | [VISTA ルール](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| 処理ルール | Analytics UIで変数を設定、変更およびコピーして、収集されたデータを変更できます。 | [処理ルール](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| デバッガーオプション | Adobe Experience cloudデバッガーなど、実装の検証に役立つ様々なデバッガーやパケットスニファーを利用できます。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| Data Insertion API | Data Insertion APIは、サーバー側のデータ収集とExperience cloudサーバーへの送信のメカニズムを提供します。 サーバー側のデータ収集では、各WebページでJavaScriptビーコンを使用して訪問者データをExperience cloudサーバーに送信する代わりに、WebブラウザーのリクエストとWebサーバーの応答に基づいてデータを収集します。 | [POSTを使用してAdobe Analyticsデータ挿入APIを実装する手順](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
