---
description: このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。
title: Adobe Analytics - 主要概念
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics - 主要概念

このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。

## Analytics ツール {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 製品 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| Analysis Workspace | 強力なカスタム分析プロジェクトを構築しインサイトをデモクラタイズ（民主化）するブラウザーソリューションReports &amp; Analytics よりも柔軟性の高いレポートを提供します。 | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/analysis-workspace-features.translate.html) |
| Reports &amp; Analytics（旧称 SiteCatalyst） | レポートおよび分析のためのブラウザーソリューションAnalytics パッケージのスターターツールです。 | [Reports &amp; Analytics ホーム](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/getting-started.translate.html) |
| Report Builder | Adobe Analytics のデータからカスタムリクエストを構築し、視覚的なレポートを作成する Microsoft Excel のアドインです。 | [Report Builder ホーム](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis（旧称 Discover） | 高度なデジタル分析を実行する Java ベースのツールです。 | [Ad Hoc Analysis ホーム](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench（旧称 Insight） | 複数チャネルに渡るオンラインとオフラインの両方の顧客インタラクションから、データの収集、処理、分析、視覚化を行うよう設計されています。 | [Data Workbench クライアント](https://marketing.adobe.com/resources/help/ja_JP/insight/client/) |
| Data Warehouse | 保存用およびデータをフィルタリングして実行できるカスタムレポート用の、生の処理されていないデータです。ヒットレベルではありません。 | [Data Warehouse ホーム](https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | アプリ用の各ソリューションが Adobe Experience Cloud 上で統合されます。これにより、アプリの利用状況を把握し、改善につなげることができます。 | [Mobile Services ホーム](https://docs.adobe.com/content/help/ja-JP/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（旧称 Genesis） | サードパーティのアプリケーションから Analytics にトラッキングデータをインポートします。これにより、パフォーマンスに関する一元的なエンドツーエンドの可視性が実現します。 | [Data Connectors ホーム](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management（DTM） | Analytics、Target およびその他のタグを、ドメイン数にかかわらず、すべてのサイトにわたって管理できます。 | [DTM ホーム](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | アドビが提供する次世代型の Web サイトタグおよびモバイル SDK の管理機能です。 | [Adobe Launch ホーム](https://docs.adobe.com/content/help/ja-JP/launch/using/overview.html) |

## 主要用語 {#concept_E473ACBB8E4A42B4AC005538AC12F154}

追加された Adobe Analytics の用語集を参照するには、[ここをクリック](https://docs.adobe.com/content/help/ja-JP/analytics/technotes/terms.html)してください。

| 用語 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| prop（カスタムトラフィック） | ページ別のサイトトラフィックアクティビティのトラッキングに使用されるディメンションです。prop はページをまたいで保持されません。トラフィック変数の主要な用途を次に示します。 <ul><li>特定の値の「一番人気」を見つける単純なカウント</li><li>ユーザーがサイト内をどのように遷移したかの可視性 </li></ul><br>トラフィック変数の例として、ページ名、サイトセクション、ブラウザーがあります。</br> | [prop](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar（カスタムコンバージョン） | カスタマイズされた一定期間持続するディメンションです。有効期限オプションには、イベントの有効期限、訪問の有効期限、または X-day 有効期限が含まれ、該当の変数で実行される分析のタイプによって決定します。<br>eVar と prop の主な違い：</br><ul><li>props では永続性が削除されるので、パス分析によく使用されます。</li><li>eVar は、多くの場合、コンバージョン分析に使用されます。</li></ul><br>コンバージョン変数の例には、内部検索用語、内部プロモーション、外部キャンペーン（s.campaign）があります。</br> | [eVar](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| イベント／指標（s.events） | 指標サイト上で訪問者におこなって欲しい主要なアクションを測定する指標です。イベントには、カウンター、数値、通貨の 3 タイプがあります。イベントは、コンバージョン変数（eVar）レポートに追加すると便利です。eVar は発生した内容に関する定性的情報を提供し、イベントは発生した内容に関する定量的情報を提供します。<br>eVar とイベントの主な違い：</br><ul><li>eVar は、誰が、何が、またはどれがコンバージョンに影響したかを示します</li><li>イベントは、発生したコンバージョンの数を測定します</li></ul><br>コンバージョンイベントの例には、購入回数、アプリケーション開始、リード、売上高があります。</br> | [イベント](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/success-events/success-event.html) |
| コンポーネント | ディメンション、指標、セグメントおよび時間の精度（日付範囲）をプロジェクトにドラッグ＆ドロップできます。 | [コンポーネント](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| ディメンション | eVar、prop、分類およびアドビの標準収集値のコレクションです。 | [ディメンション](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 指標 | 実装されたイベントと計算指標のコレクションです。 | [指標](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 計算指標 | 実装を通じて取り込まれた既存の指標からカスタム指標を導き出す機能です。 | [計算指標](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/cm-overview.html) |
| セグメント | 強力かつ重要な閲覧者セグメントを作成、管理、共有し、Analytics レポートに適用する機能です。セグメントは Analytics 製品全体で共有されます。また、Experience Cloud 全体で共有することができます。 | [セグメント化](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html) |
| 時間（日付範囲） | 任意の期間に対して日付を絞り込み、分析で再利用できるカスタム日付範囲を作成する機能です。 | [日付範囲](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| ビジュアライゼーション | プロジェクトでデータを活用するのに役立つ、豊富なビジュアルです。 | [ビジュアライゼーション](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| キュレーション | プロジェクトまたは仮想レポートスイートでアクセス可能なコンポーネントを制限する機能です。 | [VRS キュレーション](https://docs.adobe.com/content/help/ja-JP/analytics/components/virtual-report-suites/vrs-components.html)<br>[プロジェクト キュレーション](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[比較](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## 主要レポート

| レポート | 説明 | ドキュメントリンク |
|--- |--- |--- |
| 全ディメンション／レポートのリスト | Adobe Analytics で使用できる全ディメンション／レポートの定義。 | [ディメンション](https://marketing.adobe.com/resources/help/ja_JP/reference/reports_descriptions.html) |
| Advertising Analytics | Adobe Analytics 内で、Google および Bing のすべての有料検索データを並べて分析します。統合を通じて作成されるディメンションには、広告プラットフォーム、キーワード、一致タイプなどがあります。作成される指標は、AMO インプレッション数、AMO クリック数、AMO コスト、平均掲載順位、および平均品質スコアです。 | [Advertising Analytics](https://docs.adobe.com/help/ja-JP/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | AAM でユーザーの オーディエンスメンバーシップによって Analytics の受信ヒットを強化します。人口統計情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの AAM のオーディエンスデータを任意の Analytics ワークフローに組み込むことができます。この統合によって作成されるディメンションは、オーディエンス ID とオーディエンス名です。 | [Audience Analytics](https://docs.adobe.com/content/help/ja-JP/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | カスタマージャーニー全体を通して意味のあるエンゲージメントがどのようにおこなわれるかを理解して、顧客を目標とする成果に導く転機をインテリジェントに識別し、マーケティング戦略を効果的に最適化できます。モデルには、最初、最後、線形、参加、J 字形、逆 J 形、U 字形、同じタッチ、カスタム、時間減衰が含まれます。 | [Attribution IQ](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/panels/attribution.html) |
| 異常値検出 | 以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。AD は、Analysis Workspace のすべてのトレンドビジュアライゼーションのデフォルトでオンになっています。 | [異常値検出](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| 貢献度分析 | アクセス権を持つすべての指標およびディメンションの自動分析を実行することで、異常値が「なぜ」発生したかを調べます。 | [貢献度分析](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| コホート分析 | コホートは、特定の期間にわたって共通の特性を共有する人のグループです。コホート分析は、ユーザーのリテンションと傾向を分析する際に役立ちます。 | [コホート分析](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| カスタマージャーニーレポート | サイトまたはアプリケーションでのユーザーの遷移に関する情報を表示します。Analysis Workspace では、この分析に prop、eVar およびイベントを使用できます。 | [Analysis Workspace のフォールアウト](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Analysis Workspace の流れ](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[Reports &amp; Analytics でのパス](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-paths.html) |
| マーケティングチャネル | ユーザーをサイトに誘導する外部チャネルや、コンバージョンに最も効果があるチャネルを確認するのに役立つレポートです。ファーストタッチおよびラストタッチの属性ビューが提供されます。これは、有料チャネルと自然チャネルの両方において最も包括的なビューなので、Adobe Analytics で（キャンペーンやトラフィックソースよりも）推奨される外部トラフィックソースレポートです。 | [マーケティングチャネル](https://docs.adobe.com/content/help/ja-JP/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| モバイル | モバイルデバイスまたはタブレットからアクセスされた Web サイトの情報を表示します。 | モバイルレポート | （https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-mobile.html） |
| モバイルアプリ | モバイルアプリに関する基本的な使用状況の情報を表示します。これらのレポートは、SDK が導入され、レポートが有効になると使用できます。さらに、Adobe Mobile Services によって、より包括的なアプリデータを提供する個別のモバイルアプリインターフェイスが作成されました。これにより、アプリの利用状況を把握し、改善につなげることができます。[こちらで](https://mobilemarketing.adobe.com)インターフェイスにアクセスできます。 | [Adobe Mobile Services](https://docs.adobe.com/content/help/ja-JP/mobile-services/using/home.html) | 製品 | 売上高やチェックアウト数など各種コンバージョン指標に対する個々の商品や商品グループ（カテゴリ）の貢献を明らかにできます。 | [製品レポート](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-products.html) |
| セグメント比較 | アクセス権のあるすべての単一のセグメントおよびディメンションを自動分析することで、セグメント間の最も大きな統計的差異を見つけることができます。 | [セグメント比較](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| サイトコンテンツレポート | サイトで最もアクティブなページや領域、および最もよく利用されているサーバーに関する情報が表示されます。 | [サイトコンテンツレポート](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| サイト指標レポート | 実訪問者数、購入回数、売上高などの Web サイトの定量的情報を表示します。各指標は、他の項目ベースレポートに配置できます。 | [サイト指標レポート](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| 訪問者プロファイル | 国、州、郵便番号コードおよびドメインなどの各種プロファイルカテゴリから、顧客の購入パターンを確認するのに役立つレポートです。 | [訪問者プロファイル](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| 訪問者保持率 | 訪問者がサイトに再訪問した回数や頻度など、顧客忠誠度についての情報を表示します。 | [訪問者保持率](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| プロジェクトリンク、共有、スケジュール | Analytics インターフェイスで作業内容を保存および他者と共有するための方法です。 | [ファイルの送信およびスケジュール](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## 主要指標 {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 指標名 | 定義 | ドキュメントリンク |
|---|---|---|
| 全指標のリスト | Adobe Analytics の全指標の定義。 | [指標の概要](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/metrics/metrics-overview.html) |
| 個別訪問者数 | 特定期間における Web サイトへの重複なしの訪問者数。 | [個別訪問者数](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| 訪問数 | 1 回のランディングでの一連のページビュー。訪問は、ユーザーが最初にサイトのページを表示したときに開始し、非アクティブ状態が 30 分続いた後に終了します。 | [訪問数](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/metrics/metrics-visit.html) |
| ページビュー数 | ページビューは、訪問者が Web サイトのページを表示したときに発生します。 | [ページビュー数](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/metrics/metrics-page-view.html) |
| インスタンス | 変数が定義された回数。Adobe Analytics に変数内の値が表示されるたびに、それぞれのレポートでインスタンスが 1 つずつ増分します。 | [インスタンス](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/metrics/metrics-instance.html) |
| 発生件数 | 変数が定義または永続化された回数。 | [発生件数](https://docs.adobe.com/content/help/ja-JP/analytics/components/variables/metrics/metrics-occurrences.html) |

## インポートオプション {#concept_7C6DF03B5F9149E2A77F36C739432059}

| オプション | 説明 | ドキュメントリンク |
|---|---|---|
| 分類インポーター | ブラウザーまたは FTP アップロードを介して、メタデータを取得したディメンションに対してインポートします。ルールビルダーとは異なり、手動で操作します。 | [分類インポーター](https://marketing.adobe.com/resources/help/ja_JP/reference/c_working_with_saint.html) |
| ルールビルダー | ユーザー定義のルールに基づき、メタデータ分類を自動的に作成します。 | [分類ルールビルダー](https://marketing.adobe.com/resources/help/ja_JP/reference/classification_rule_builder.html) |
| 顧客属性 | Adobe Analytics および Adobe Target で使用するために Experience Cloud にアップロードされた CRM データです。 | [顧客属性](https://docs.adobe.com/content/help/ja-JP/core-services/interface/customer-attributes/attributes.html) |
| データソース | オフライン指標をディメンションに対して、または単に日別に Analytics にインポートします。 | [データソース](https://docs.adobe.com/content/help/ja-JP/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange Data Connectors | [Analytics ツール](/help/landing/an-key-concepts.md)を参照してください。 |  |
| ネイティブ統合 | Audience Analytics &amp; Advertising Analytics。 | 「主要レポート」の節を参照。 |

## エクスポートオプション {#concept_C62B688E259141CF92C048E8110464BE}

| オプション | 説明 | ドキュメントリンク |
|---|---|---|
| UI のダウンロードとスケジュール | Analysis Workspace からデータを CSV または PDF としてエクスポート。 | [PDF ファイルまたは CSV ファイルのダウンロード](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Analytics ツールを参照してください。 |
| Analytics API | Analytics データの自分用のカスタマイズクエリを作成します。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Analytics ツールを参照してください。 |  |
| Analytics データフィード | Analytics から最も詳細なデータを取得する方法です。Analytics からヒットレベルフィードを設定します。 | [Analytics データフィード](https://docs.adobe.com/content/help/ja-JP/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## データコレクションおよび検証 {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 手段／リソース | 説明 | ドキュメントリンク |
|--- |--- |--- |
| 開発者向けリソース | 利用可能なすべてのプラットフォーム（Web、モバイルアプリ、ビデオ、Flash など）の Analytics データの収集で利用可能なライブラリについて概説したドキュメント。 | [開発者向けドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 実装ガイド | データ収集変数の説明と、JavaScript でのデータ収集コードの導入についての詳細してください。 | [実装ガイド](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/home.html) |
| AppMeasurement（s_code） | グローバル変数管理 | [AppMeasurement](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| App SDK | アプリの設定ファイルの事前収集バージョンを含むカスタマイズされたパッケージ。 | <ul><li>[iOS](https://docs.adobe.com/content/help/ja-JP/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/ja-JP/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM および Adobe Launch | Analytics ツールを参照してください。 |  |
| VISTA | サーバー側のロジックを適用して、データの収集時にデータを変更またはセグメント化できます。 | [VISTA ルール](https://marketing.adobe.com/resources/help/ja_JP/reference/VISTA.html) |
| 処理ルール | Analytics UI で変数を設定、変更およびコピーして、収集されたデータを変更できます。 | [処理ルール](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| デバッガーオプション | Adobe Experience Cloud デバッガーなど、実装の検証に役立つ様々なデバッガーやパケットスニファーを利用できます。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=ja) |
| Data Insertion API | Data Insertion API は、サーバー側のデータ収集と Experience Cloud サーバーへの送信のメカニズムを提供します。サーバー側のデータ収集では、各 Web ページで JavaScript ビーコンを使用して訪問者データを Experience Cloud サーバーに送信する代わりに、Web ブラウザーのリクエストと Web サーバーの応答に基づいてデータを収集します。 | [POST を使用して Adobe Analytics データ挿入 API を実装する手順](https://helpx.adobe.com/jp/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
