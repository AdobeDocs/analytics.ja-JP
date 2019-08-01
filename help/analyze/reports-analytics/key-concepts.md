---
description: このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。
seo-description: このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。
seo-title: Adobe Analytics-主要概念
title: Adobe Analytics-主要概念
uuid: ef5701c5-2d3e-4847-851f-9312d55db1a8
translation-type: tm+mt
source-git-commit: d3819975bb65ccf345d60474e268ed9d1b1606a7

---


# Adobe Analytics-主要概念

このセクションには、Adobe Analytics の主要概念、概念の簡潔な説明および特定のドキュメントリンクとトピックについての詳細が含まれています。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 製品 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| Analysis Workspace | 堅牢なカスタム分析プロジェクトを構築し、インサイトを民主化するブラウザーソリューション。Reports&amp; Analyticsよりも柔軟性の高いレポートを提供します | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Reports &amp; Analytics（旧称 SiteCatalyst） | レポートおよび分析のためのブラウザーソリューション。Analytics パッケージのスターターツールです。 | [Reports&amp; Analyticsのホーム](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Adobe Analyticsデータからカスタマイズされたリクエストを作成し、Microsoft Excelを使用して視覚化できるExcelアドインです。 | [Report Builderホーム](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis（旧称 Discover） | 高度なデジタル分析用Javaベースツール。2019年第3四半期に提供終了。 | [Ad Hoc Analysisホーム](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench（旧称 Insight） | 複数チャネルに渡るオンラインとオフラインの両方の顧客インタラクションから、データの収集、処理、分析、視覚化を行うよう設計されています。 | [Data Workbench クライアント](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 保存用およびデータをフィルタリングして実行できるカスタムレポート用の、生の処理されていないデータです。ヒットレベルではありません。 | [Data Warehouseホーム](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | アプリ用の各ソリューションが Adobe Experience Cloud 上で統合されます。これにより、アプリの利用状況を把握し、改善につなげることができます。 | [Mobile Servicesホーム](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（旧称Genesis） | サードパーティアプリケーションからAnalyticsにトラッキングデータをインポートして、パフォーマンスのエンドツーエンドの可視性をエンドツーエンドで実現できます。 | [Data Connectorsホーム](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management（DTM） | Analytics、Target およびその他のタグを、ドメイン数にかかわらず、すべてのサイトにわたって管理できます。 | [DTMホーム](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | アドビのWebサイトタグおよびモバイルSDK管理機能の次世代。 | [Adobe Launchホーム](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

追加された Adobe Analytics の用語集を参照するには、[ここをクリック](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)してください。

| 用語 | 説明 | ドキュメントリンク |
|--- |--- |--- |
| prop（カスタムトラフィック） | ページごとのサイトトラフィックアクティビティを追跡するために使用されるディメンション。prop はページをまたいで保持されません。トラフィック変数の主要な用途を次に示します。 <ul><li>特定の値の「最も人気がある」を検索する単純なカウント</li><li>ユーザーがサイトをどのように遷移しているかを表示する </li></ul><br>トラフィック変数の例:ページ名、サイトセクション、ブラウザー</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar（カスタムコンバージョン） | 自分によってカスタマイズされた一定期間保持されるディメンション。有効期限オプションには、イベントの有効期限、訪問の有効期限、または X-day 有効期限が含まれ、該当の変数で実行される分析のタイプによって決定します。<br>eVarとpropの主な違い:</br><ul><li>propは、持続性が削除されるので、多くの場合パス分析に使用されます。</li><li>eVarは多くの場合コンバージョン分析に使用されます。</li></ul><br>コンバージョン変数の例:内部検索用語、内部プロモーション、外部キャンペーン（s. campaign）</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| イベント/指標（s. events） | サイト上で訪問者がとる主要アクションを測定する指標。イベントには、カウンター、数値、通貨の 3 タイプがあります。イベントは、コンバージョン変数（eVar）レポートに追加すると便利です。eVar は発生した内容に関する定性的情報を提供し、イベントは発生した内容に関する定量的情報を提供します。<br>eVarとイベントの主な違い:</br><ul><li>eVarは、誰が、何を、またはコンバージョンに影響したかを示します</li><li>発生したコンバージョンの数を測定するイベント</li></ul><br>コンバージョンイベントの例には、購入回数、アプリケーション開始、リード、売上高があります。</br> | [イベント](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| コンポーネント | プロジェクトにドラッグ&amp;ドロップできるディメンション、指標、セグメントおよび時間の精度（日付範囲）。 | [コンポーネント](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| ディメンション | eVar、prop、分類および標準的なアドビの収集された値のコレクション。 | [ディメンション](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 指標 | 実装されたイベントおよび計算指標のコレクション。 | [指標](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 計算指標 | 導入でキャプチャされた既存の指標からカスタム指標を派生させる機能。 | [計算指標](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| セグメント | 強力かつ重要な閲覧者セグメントを作成、管理、共有し、Analytics レポートに適用できます。セグメントは Analytics 製品全体で共有されます。また、Experience Cloud 全体で共有することができます。 | [セグメント化](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 時間（日付範囲） | 任意の期間に日付をフィルターし、分析で再利用できるカスタム日付範囲を作成できます。 | [日付範囲](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| ビジュアライゼーション | プロジェクトでのデータの配信に役立つリッチビジュアル。 | [ビジュアライゼーション](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| キュレーション | プロジェクトまたは仮想レポートスイートからアクセスできるコンポーネントを制限できます。 | [VRSキュレーションプロジェクト](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[のキュation比較](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Key features {#concept_216E78AD39DD453D940AE857F4C7D4DF}

<table id="table_5CD38BD3BE854E69B6925EA3F02AFC92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> レポート </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ドキュメントリンク </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 全レポートのリスト </td> 
   <td colname="col2"> Adobe Analytics で使用できる全レポートの定義。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_descriptions.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタムトラフィック（prop） </td> 
   <td colname="col2">ページ別のサイトトラフィックアクティビティのトラッキングに使用されます。prop はページをまたいで保持されません。トラフィック変数の主要な用途を次に示します。 
    <ul id="ul_A935EC5271684B9599F683C7B31400ED"> 
     <li id="li_58E0596050A34ACC821916EA61E946EF">ページビュー数、訪問回数、訪問者数、またはインスタンスに関連づけることができる値の取得。 </li> 
     <li id="li_2B4C557AAD0544BE8204C0D7CE587175">「最も使用されている」特定の値の検索。 </li> 
     <li id="li_7FA62BE657F047459DF439BFB9F332F5">ユーザーがサイト内をどのように遷移したかの確認。 </li> 
    </ul> <p>トラフィック変数の例として、ページ名、サイトセクション、ブラウザーがあります。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/traffic_var.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタムコンバージョン（eVar） </td> 
   <td colname="col2">主にコンバージョンイベントに関するレポートとカスタマイズされた期間の保持のために使用されます。有効期限オプションには、イベントの有効期限、訪問の有効期限、または X-day 有効期限が含まれ、該当の変数で実行される分析のタイプによって決定します。 <p>コンバージョン変数とトラフィック変数の主な違い： </p> 
    <ul id="ul_B0A7482A81B94C5F86C06E5507DB393D"> 
     <li id="li_272E414520AA4603AE5EC397B0F93630"> カスタムトラフィック変数は、コンバージョンではなくトラフィック指標と結び付きます。多くの場合、パス分析に使用されます。 </li> 
     <li id="li_EBBF9A35C64845FE9683540DFA89E7E9">カスタムコンバージョン変数は、トラフィックおよびコンバージョンと結び付けることができ、多くの場合コンバージョン分析に使用されます。 </li> 
    </ul> <p>コンバージョン変数の例には、内部検索用語、内部プロモーション、外部キャンペーン（s.campaign）があります。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/conversion_var_admin.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功イベント（s.events） </td> 
   <td colname="col2"> <p>サイト上で訪問者に行って欲しい主要なアクションを測定します。 </p> <p>イベントには、カウンター、数値、通貨の 3 タイプがあります。イベントは、コンバージョン変数（eVar）レポートに追加すると便利です。eVar は発生した内容に関する定性的情報を提供し、イベントは発生した内容に関する定量的情報を提供します。 </p> <p>コンバージョン変数とカスタムイベントの主な違い： </p> 
    <ul id="ul_2B95D7437DE444DD9618DBFE6A8612D1"> 
     <li id="li_5951858853334EFA931A5BC57E5C933F">コンバージョン変数は、誰が、何が、またはどれがコンバージョンに影響したかを示します。 </li> 
     <li id="li_339755C842714E0DB8DB4DFAA43AB4F7"> カスタムイベントは、発生したコンバージョンの数を測定します。 </li> 
    </ul> <p>コンバージョンイベントの例には、購入回数、アプリケーション開始、リード、売上高があります。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/success_event.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/success_event.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サイト指標 </td> 
   <td colname="col2"> 実訪問者数、購入回数、売上高などの Web サイトの定量的情報を表示します。各指標は、他の項目ベースレポートに配置できます。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_site_metrics.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サイトコンテンツ </td> 
   <td colname="col2"> サイトのどのページと領域が最もアクティブで、どのサーバーが最もよく利用されているかが表示されます。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_site_content.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> モバイル </td> 
   <td colname="col2"> モバイルデバイスまたはタブレットからアクセスされた Web サイトの情報を表示します。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_mobile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> モバイルアプリ </td> 
   <td colname="col2"> <p>モバイルアプリに関する基本的な使用状況の情報を表示します。これらのレポートは、SDK が導入され、レポートが有効になると使用できます。 </p> <p>さらに、Adobe Mobile Services によって、より包括的なアプリデータを提供する個別のモバイルアプリインターフェイスが作成されました。これにより、アプリの利用状況を把握し、改善につなげることができます。 </p> <p>インターフェイスの入手先： </p> <p><a href="https://mobilemarketing.adobe.com" format="https" scope="external"> https://mobilemarketing.adobe.com</a> </p> </td> 
   <td colname="col3"> <p>Adobe Mobile Services： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/mobile/</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パスレポート </td> 
   <td colname="col2"> Web サイトのページがアクセスされた順序が表示されます。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_paths.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 製品 </td> 
   <td colname="col2"> 売上高やチェックアウト数など各種コンバージョン指標に対する個々の商品や商品グループ（カテゴリ）の貢献を明らかにできます。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_products.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者保持率 </td> 
   <td colname="col2"> 訪問者がサイトに再訪問した回数や頻度など、顧客忠誠度についての情報を表示します。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_visitor_retention.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者プロファイル </td> 
   <td colname="col2"> 国、州、郵便番号コードおよびドメインなどの各種プロファイルカテゴリから、顧客の購入パターンを確認するのに役立つレポートです。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_visitor_profile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マーケティングチャネル </td> 
   <td colname="col2">ユーザーをサイトに誘導する外部チャネルや、コンバージョンに最も効果があるチャネルを確認するのに役立つレポートです。ファーストタッチおよびラストタッチの属性ビューが提供されます。 <p>これは、有料チャネルと自然チャネルの両方において最も包括的なビューなので、Adobe Analytics で（キャンペーンやトラフィックソースよりも）推奨される外部トラフィックソースレポートです。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/mchannel/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/mchannel/index.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> カスタムレポート、レポートリンク、ブックマーク、ダッシュボード </td> 
   <td colname="col2"> 他の Analytics インターフェイスで作業内容を保存および他者と共有するための方法です。 </td> 
   <td colname="col3">カスタムレポート： <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/reports_custom.html</a> </p> <p>レポートリンク： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/user/t_reports_share_link.html</a> </p> <p>ブックマーク </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/user/bookmarks.html</a> </p> <p>ダッシュボード </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/user/dashboard.html</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 指標名 | 定義 | ドキュメントリンク |
|---|---|---|
| 全指標のリスト | Adobe Analytics の全指標の定義。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/metrics.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics.html) |
| 実訪問者数 | 特定期間における Web サイトへの重複なしの訪問者数。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/metrics_unique_visitors.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html) |
| 訪問回数 | 1 回のランディングでの一連のページビュー。訪問は、ユーザーが最初にサイトのページを表示したときに開始し、非アクティブ状態が 30 分続いた後に終了します。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/metrics_visit.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html) |
| ページビュー数 | ページビューは、訪問者が Web サイトのページを表示したときに発生します。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/metrics_page_view.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html) |
| インスタンス | 変数が定義された回数。Adobe Analytics に変数内の値が表示されるたびに、それぞれのレポートでインスタンスが 1 つずつ増分します。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/metrics_instance.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html) |
| 計算指標 | 既存の指標から作成できるカスタム指標。例えば、売上高と訪問回数がある場合は、1 訪問あたりの平均売上高、すなわち売上高を訪問回数で割った値（売上／訪問回数）のカスタム指標を作成できます。 | [https://marketing.adobe.com/resources/help/ja_JP/analytics/calcmetrics/](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) |

## インポート オプション {#concept_7C6DF03B5F9149E2A77F36C739432059}

| オプション | 説明 | ドキュメントリンク |
|---|---|---|
| 分類インポーター | ブラウザーまたは FTP アップロードを介して、メタデータを取得したディメンションに対してインポートします。ルールビルダーとは異なり、手動で操作します。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/c_working_with_saint.html](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| ルールビルダー | ユーザー定義のルールに基づき、メタデータ分類を自動的に作成します。 | [https://marketing.adobe.com/resources/help/ja_JP/reference/classification_rule_builder.html](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| データソース | オフライン指標をディメンションに対して、または単に日別に Analytics にインポートします。 | [https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html](https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html) |
| Data Connectors | [製品](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B)を参照。 |  |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}


<table id="table_99867D82082D4756872FC3ABD83A33A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> インターフェイスレポートをダウンロード </td> 
   <td colname="col2"> Analytics からデータをエクスポートする単純な方法。 </td> 
   <td colname="col3">https://microsite.omniture.com/t2/help/en_US/survey/index.html#Downloading_a_Report_Using_ <p>Basic_Options </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Warehouse </td> 
   <td colname="col2"><a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">製品</a>を参照。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report Builder </td> 
   <td colname="col2"><a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">製品</a>を参照。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics API </td> 
   <td colname="col2"> Analytics データの自分用のカスタマイズクエリを作成します。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/developer/documentation" format="https" scope="external"> https://marketing.adobe.com/developer/ja/documentation</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> クリックストリームデータフィード </td> 
   <td colname="col2"> Analytics から最も詳細なデータを取得する方法です。Analytics からヒットレベルフィードを設定します。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/clickstream/datafeeds_reference.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> データの配信 </td> 
   <td colname="col2"> Adobe Analytics のほとんどのエクスポートオプションは、電子メールまたは FTP サイトにデータおよびレポートを配信する機能を備えています。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

<table id="table_53039DCCAC1D47F7A1E3485609D13E4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 手段／リソース </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ドキュメントリンク </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 開発者向けリソース </td> 
   <td colname="col2"> 利用可能なすべてのプラットフォーム（Web、モバイルアプリ、ビデオ、Flash など）の Analytics データの収集で利用可能なライブラリについて概説したドキュメント。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/developer.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 導入ガイド </td> 
   <td colname="col2"> データ収集変数の説明と、JavaScript でのデータ収集コードの導入についての詳細。 </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/implement/index.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AppMeasurement（s_code） </td> 
   <td colname="col2"> グローバル変数管理 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html#" format="html" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/implement/appmeasure_mjs.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> App SDK </td> 
   <td colname="col2"> アプリの設定ファイルの事前収集バージョンを含むカスタマイズされたパッケージ。 </td> 
   <td colname="col3">iOS： <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/mobile/ios/?f=requirements</a> </p> <p>Android： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Tag Management（DTM） </td> 
   <td colname="col2"><a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">製品</a>を参照。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VISTA </td> 
   <td colname="col2"> レポート変数を収集するためのサーバーサイドアプローチ。VISTA は、訪問者のセグメント化ルールを使用して、すべてのオンラインデータをリアルタイムでセグメント化します。これらのルールにより、サイトに複雑なロジックを実装することなく、選択するほぼすべての方法でデータの変更やセグメント化が可能になります。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/VISTA.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 処理ルール </td> 
   <td colname="col2"> データ収集を単純化し、管理ツールセクションからレポーティングに送信されるコンテンツを管理します。処理ルールは、設定、変更、および変数のコピーに対するインターフェイスを提供することにより、IT グループおよび Web 開発者とのやり取りの単純化に役立ちます。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/processing_rules.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> デバッガーオプション </td> 
   <td colname="col2"> 導入の検証をするための様々なデバッガーおよびパケットスニファーを利用できます。推奨デバッガーは Charles です。その他には Adobe Debugger、HTTPFox、Firebug、Omnibug、Fiddler、および HTTPWatch があります。 </td> 
   <td colname="col3">Adobe Debugger： <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/sc/implement/debugger.html</a> </p> <p>Charles： </p> <p><a href="https://www.charlesproxy.com/" format="http" scope="external"> https://www.charlesproxy.com/</a> </p> </td> 
  </tr> 
 </tbody> 
</table>
