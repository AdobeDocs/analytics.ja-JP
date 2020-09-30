---
description: このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。
title: Adobe Analytics - 主要概念
translation-type: tm+mt
source-git-commit: 232a8376d605fc2345b16fc6579b77dbe2eb7709
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Adobe Analytics - 主要概念

このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。

## Analytics ツール {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 製品 | 説明 | ドキュメントリンク |
| --- | --- | --- |
| Analysis Workspace | 強力なカスタム分析プロジェクトを構築しインサイトをデモクラタイズ（民主化）するブラウザーソリューションReports and Analyticsよりもレポートの柔軟性の高いオファー | [Analysis Workspaceホーム](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics(旧SiteCatalyst) | レポートおよび分析のためのブラウザーソリューションAnalytics パッケージのスターターツールです。 | [Reports and Analyticsホーム](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Adobe Analytics のデータからカスタムリクエストを構築し、視覚的なレポートを作成する Microsoft Excel のアドインです。 | [Report Builder ホーム](/help/analyze/report-builder/home.md) |
| Ad Hoc Analysis（旧称 Discover） | 高度なデジタル分析を実行する Java ベースのツールです。 | [Ad Hoc Analysis ホーム](/help/analyze/ad-hoc-analysis/adhoc-home.md) |
| Data Workbench（旧称 Insight） | 複数チャネルに渡るオンラインとオフラインの両方の顧客インタラクションから、データの収集、処理、分析、視覚化を行うよう設計されています。 | [Data Workbench クライアント](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | 保存用およびデータをフィルタリングして実行できるカスタムレポート用の、生の処理されていないデータです。ヒットレベルではありません。 | [Data Warehouse ホーム](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | アプリ用の各ソリューションが Adobe Experience Cloud 上で統合されます。これにより、アプリの利用状況を把握し、改善につなげることができます。 | [Mobile Services ホーム](https://docs.adobe.com/content/help/ja-JP/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（旧称 Genesis） | サードパーティのアプリケーションから Analytics にトラッキングデータをインポートします。これにより、パフォーマンスに関する一元的なエンドツーエンドの可視性が実現します。 | [Data Connectors ホーム](/help/import/data-connectors/data-connectors-eol.md) |
| Dynamic Tag Management（DTM） | Analytics、Target およびその他のタグを、ドメイン数にかかわらず、すべてのサイトにわたって管理できます。 | [DTM ホーム](/help/implement/other/dtm/dtm-implementation-overview.md) |
| Adobe Launch | アドビが提供する次世代型の Web サイトタグおよびモバイル SDK の管理機能です。 | [Adobe Launch ホーム](https://docs.adobe.com/content/help/ja-JP/launch/using/overview.html) |

## 主要用語 {#concept_E473ACBB8E4A42B4AC005538AC12F154}

追加された Adobe Analytics の用語集を参照するには、[ここをクリック](/help/technotes/terms.md)してください。

| 用語 | 説明 | ドキュメントリンク |
| --- | --- | --- |
| prop（カスタムトラフィック） | ページ別のサイトトラフィックアクティビティのトラッキングに使用されるディメンションです。prop はページをまたいで保持されません。トラフィック変数の主要な用途を次に示します。 <ul> <li>特定の値の「一番人気」を見つける単純なカウント</li> <li>ユーザーがサイト内をどのように遷移したかの可視性</li> </ul> <br>トラフィック変数の例として、ページ名、サイトセクション、ブラウザーがあります。 | [prop](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar（カスタムコンバージョン） | カスタマイズされた一定期間持続するディメンションです。有効期限オプションには、イベントの有効期限、訪問の有効期限、または X-day 有効期限が含まれ、該当の変数で実行される分析のタイプによって決定します。<br>eVar と prop の主な違い： <ul> <li>props では永続性が削除されるので、パス分析によく使用されます。</li> <li>eVar は、多くの場合、コンバージョン分析に使用されます。</li> </ul> <br>コンバージョン変数の例には、内部検索用語、内部プロモーション、外部キャンペーン（s.campaign）があります。 | [eVar](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| イベント／指標（s.events） | 指標サイト上で訪問者におこなって欲しい主要なアクションを測定する指標です。イベントには、カウンター、数値、通貨の 3 タイプがあります。イベントは、コンバージョン変数（eVar）レポートに追加すると便利です。eVar は発生した内容に関する定性的情報を提供し、イベントは発生した内容に関する定量的情報を提供します。<br>eVar とイベントの主な違い： <ul> <li>eVar は、誰が、何が、またはどれがコンバージョンに影響したかを示します</li> <li>イベントは、発生したコンバージョンの数を測定します</li> </ul> <br>コンバージョンイベントの例には、購入回数、アプリケーション開始、リード、売上高があります。 | [イベント](/help/admin/admin/c-success-events/success-event.md) |
| コンポーネント | ディメンション、指標、セグメントおよび時間の精度（日付範囲）をプロジェクトにドラッグ＆ドロップできます。 | [コンポーネント](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ディメンション | eVar、prop、分類およびアドビの標準収集値のコレクションです。 | [ディメンション](/help/components/dimensions/overview.md) |
| 指標 | 実装されたイベントと計算指標のコレクションです。 | [指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| 計算指標 | 実装を通じて取り込まれた既存の指標からカスタム指標を導き出す機能です。 | [計算指標](/help/components/c-calcmetrics/cm-overview.md) |
| セグメント | 強力かつ重要な閲覧者セグメントを作成、管理、共有し、Analytics レポートに適用する機能です。セグメントは Analytics 製品全体で共有されます。また、Experience Cloud 全体で共有することができます。 | [セグメント化](/help/components/segmentation/seg-home.md) |
| 時間（日付範囲） | 任意の期間に対して日付を絞り込み、分析で再利用できるカスタム日付範囲を作成する機能です。 | [日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| ビジュアライゼーション | プロジェクトでデータを活用するのに役立つ、豊富なビジュアルです。 | [ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| キュレーション | プロジェクトまたは仮想レポートスイートでアクセス可能なコンポーネントを制限する機能です。 | [VRSキュレーション](/help/components/vrs/vrs-components.md) <br> [プロジェクトのキュレーション](/help/analyze/analysis-workspace/curate-share/curate.md) |

## 主要レポート

| レポート | 説明 | ドキュメントリンク |
| --- | --- | --- |
| 全ディメンション／レポートのリスト | Adobe Analytics で使用できる全ディメンション／レポートの定義。 | [ディメンション](/help/components/dimensions/overview.md) |
| Advertising Analytics | Adobe Analytics 内で、Google および Bing のすべての有料検索データを並べて分析します。統合を通じて作成されるディメンションには、広告プラットフォーム、キーワード、一致タイプなどがあります。作成される指標は、AMO インプレッション数、AMO クリック数、AMO コスト、平均掲載順位、および平均品質スコアです。 | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | AAM でユーザーのオーディエンスメンバーシップによって Analytics の受信ヒットを強化します。人口統計情報（例：性別や所得水準）、サイコグラフィック情報（例：興味や趣味）、CRM データ、広告インプレッションデータなどの AAM のオーディエンスデータを任意の Analytics ワークフローに組み込むことができます。この統合によって作成されるディメンションは、オーディエンス ID とオーディエンス名です。 | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | カスタマージャーニー全体を通して意味のあるエンゲージメントがどのようにおこなわれるかを理解して、顧客を目標とする成果に導く転機をインテリジェントに識別し、マーケティング戦略を効果的に最適化できます。モデルには、最初、最後、線形、参加、J 字形、逆 J 形、U 字形、同じタッチ、カスタム、時間減衰が含まれます。 | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| 異常値検出 | 以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。AD は、Analysis Workspace のすべてのトレンドビジュアライゼーションのデフォルトでオンになっています。 | [異常値検出](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 貢献度分析 | アクセス権を持つすべての指標およびディメンションの自動分析を実行することで、異常値が「なぜ」発生したかを調べます。 | [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| コホート分析 | コホートは、特定の期間にわたって共通の特性を共有する人のグループです。コホート分析は、ユーザーのリテンションと傾向を分析する際に役立ちます。 | [コホート分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| カスタマージャーニーレポート | サイトまたはアプリケーションでのユーザーの遷移に関する情報を表示します。Analysis Workspace では、この分析に prop、eVar およびイベントを使用できます。 | [Analysis Workspaceフォールアウト](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace流](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Reports and Analyticsパス](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| マーケティングチャネル | ユーザーをサイトに誘導する外部チャネルや、コンバージョンに最も効果があるチャネルを確認するのに役立つレポートです。ファーストタッチおよびラストタッチの属性ビューが提供されます。これは、有料チャネルと自然チャネルの両方において最も包括的なビューなので、Adobe Analytics で（キャンペーンやトラフィックソースよりも）推奨される外部トラフィックソースレポートです。 | [マーケティングチャネル](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| モバイル | モバイルデバイスまたはタブレットからアクセスされた Web サイトの情報を表示します。 | [モバイルレポート](/help/components/dimensions/mobile-dimensions.md) |
| モバイルアプリ | モバイルアプリに関する基本的な使用状況の情報を表示します。これらのレポートは、SDK が導入され、レポートが有効になると使用できます。さらに、Adobe Mobile Services によって、より包括的なアプリデータを提供する個別のモバイルアプリインターフェイスが作成されました。これにより、アプリの利用状況を把握し、改善につなげることができます。[こちらで](https://mobilemarketing.adobe.com)インターフェイスにアクセスできます。 | [Adobe Mobile Services](https://docs.adobe.com/content/help/ja-JP/mobile-services/using/home.html) |
| 製品 | 売上高やチェックアウト数など各種コンバージョン指標に対する個々の商品や商品グループ（カテゴリ）の貢献を明らかにできます。 | [製品レポート](/help/components/dimensions/product.md) |
| セグメント比較 | アクセス権のあるすべての単一のセグメントおよびディメンションを自動分析することで、セグメント間の最も大きな統計的差異を見つけることができます。 | [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| サイトコンテンツレポート | サイトで最もアクティブなページや領域、および最もよく利用されているサーバーに関する情報が表示されます。 | [サイトコンテンツレポート](/help/components/dimensions/page.md) |
| サイト指標レポート | 実訪問者数、購入回数、売上高などの Web サイトの定量的情報を表示します。各指標は、他の項目ベースレポートに配置できます。 | [サイト指標レポート](/help/components/metrics/overview.md) |
| 訪問者プロファイル | 国、州、郵便番号コードおよびドメインなどの各種プロファイルカテゴリから、顧客の購入パターンを確認するのに役立つレポートです。 | [訪問者プロファイル](/help/components/dimensions/language.md) |
| 訪問者保持率 | 訪問者がサイトに再訪問した回数や頻度など、顧客忠誠度についての情報を表示します。 | [訪問者保持率](/help/components/dimensions/customer-loyalty.md) |
| プロジェクトリンク、共有、スケジュール | Analytics インターフェイスで作業内容を保存および他者と共有するための方法です。 | [ファイルの送信およびスケジュール](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## 主要指標 {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 指標名 | 定義 | ドキュメントリンク |
| --- | --- | --- |
| 全指標のリスト | Adobe Analytics の全指標の定義。 | [指標の概要](/help/components/metrics/overview.md) |
| 個別訪問者数 | 特定期間における Web サイトへの重複なしの訪問者数。 | [個別訪問者数](/help/components/metrics/unique-visitors.md) |
| 訪問数 | 1 回のランディングでの一連のページビュー。訪問は、ユーザーが最初にサイトのページを表示したときに開始し、非アクティブ状態が 30 分続いた後に終了します。 | [訪問数](/help/components/metrics/visits.md) |
| ページビュー数 | ページビューは、訪問者が Web サイトのページを表示したときに発生します。 | [ページビュー数](/help/components/metrics/page-views.md) |
| インスタンス | 変数が定義された回数。Adobe Analytics に変数内の値が表示されるたびに、それぞれのレポートでインスタンスが 1 つずつ増分します。 | [インスタンス](/help/components/metrics/instances.md) |
| 発生件数 | 変数が定義または永続化された回数。 | [発生件数](/help/components/metrics/occurrences.md) |

## インポートオプション {#concept_7C6DF03B5F9149E2A77F36C739432059}

| オプション | 説明 | ドキュメントリンク |
| --- | --- | --- |
| 分類インポーター | ブラウザーまたは FTP アップロードを介して、メタデータを取得したディメンションに対してインポートします。ルールビルダーとは異なり、手動で操作します。 | [分類インポーター](/help/components/classifications/importer/c-working-with-saint.md) |
| ルールビルダー | ユーザー定義のルールに基づき、メタデータ分類を自動的に作成します。 | [分類ルールビルダー](/help/components/classifications/crb/classification-rule-builder.md) |
| 顧客属性 | Adobe Analytics および Adobe Target で使用するために Experience Cloud にアップロードされた CRM データです。 | [顧客属性](https://docs.adobe.com/content/help/ja-JP/core-services/interface/customer-attributes/attributes.html) |
| データソース | オフライン指標をディメンションに対して、または単に日別に Analytics にインポートします。 | [データソース](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange Data Connectors | [Analytics ツール](/help/import/data-connectors/data-connectors-eol.md)を参照してください。 |  |
| ネイティブ統合 | Audience Analytics &amp; Advertising Analytics。 | 「主要レポート」の節を参照。 |

## エクスポートオプション {#concept_C62B688E259141CF92C048E8110464BE}

| オプション | 説明 | ドキュメントリンク |
| --- | --- | --- |
| UI のダウンロードとスケジュール | Analysis Workspace からデータを CSV または PDF としてエクスポート。 | [PDF ファイルまたは CSV ファイルのダウンロード](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Analytics ツールを参照してください。 |  |
| Analytics API | Analytics データの自分用のカスタマイズクエリを作成します。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Analytics ツールを参照してください。 |  |
| Analytics データフィード | Analytics から最も詳細なデータを取得する方法です。Analytics からヒットレベルフィードを設定します。 | [Analytics データフィード](/help/export/analytics-data-feed/data-feed-overview.md) |

## データコレクションおよび検証 {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 手段／リソース | 説明 | ドキュメントリンク |
| --- | --- | --- |
| 開発者向けリソース | 利用可能なすべてのプラットフォーム（Web、モバイルアプリ、ビデオ、Flash など）の Analytics データの収集で利用可能なライブラリについて概説したドキュメント。 | [開発者向けドキュメント](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 実装ガイド | データ収集変数の説明と、JavaScript でのデータ収集コードの導入についての詳細してください。 | [実装ガイド](/help/implement/home.md) |
| AppMeasurement（s_code） | グローバル変数管理。 | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| App SDK | アプリの設定ファイルの事前収集バージョンを含むカスタマイズされたパッケージ。 | <ul><li>[iOS](https://docs.adobe.com/content/help/ja-JP/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/ja-JP/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM および Adobe Launch | Analytics ツールを参照してください。 |  |
| VISTA | サーバー側のロジックを適用して、データの収集時にデータを変更またはセグメント化できます。 | [VISTA ルール](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| 処理ルール | Analytics UI で変数を設定、変更およびコピーして、収集されたデータを変更できます。 | [処理ルール](/help/admin/admin/c-processing-rules/processing-rules.md) |
| デバッガーオプション | Adobe Experience Cloudデバッガを含む、導入の検証に役立つ様々なデバッガーやパケットスニファーを使用できます。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=ja) |
| Data Insertion API | Data Insertion API は、サーバー側のデータ収集と Experience Cloud サーバーへの送信のメカニズムを提供します。サーバー側のデータ収集では、各 Web ページで JavaScript ビーコンを使用して訪問者データを Experience Cloud サーバーに送信する代わりに、Web ブラウザーのリクエストと Web サーバーの応答に基づいてデータを収集します。 | [POST を使用して Adobe Analytics データ挿入 API を実装する手順](https://helpx.adobe.com/jp/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
