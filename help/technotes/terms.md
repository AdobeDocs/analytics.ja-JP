---
title: Adobe Analyticsで使用される用語
description: Adobe Analyticsの用語集で、使用する一般的な用語を定義します。
translation-type: tm+mt
source-git-commit: 5ca51ad6b967687004d9447964ed87b29077b330

---


# Adobe Analyticsで使用される用語

この用語集を使用して、Adobe Analyticsが使用する多くの用語のコンテキストを理解します。

* **管理コンソール:** 次を参照できます。
   * Adobe Analyticsのレポートスイート設定が管理されるレガシー管理ツール。以前のバージョンのAdobe Analyticsでは、ユーザー権限もここで管理されていました。See [Admin Tools](../admin/admin/c-admin-tools.md) in the Admin user guide.
   * 製品アクセスがプロビジョニングされ、ユーザー権限が管理されるAdobe Admin Console。See [Admin Console](../admin/admin-console/home.md) in the Admin user guide.
* **配分:** 訪問中にコンバージョン変数が複数の値を検出した場合、変数の配分設定によって保持される値が決まります。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **異常値:** 統計的モデリングを使用して検出され、データ内の予期しないトレンドを自動的に見つけます。モデルによって指標を分析し、値の下限、上限、予想される範囲を決定します。See [Anomaly Detection](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **AppMeasurement:** データを収集してアドビに送信するために使用されるコードライブラリ。See the [Homepage](../implement/home.md) of the Implement user guide.
* **ASIスロット:** 今後は存在しません。以前のバージョンのAdobe Analyticsでは、ASIスロットによって、セグメント化されたデータを表示するための一時的なレポートスイートコンテナが提供されていました。現在のバージョンのAdobe Analyticsでは、セグメントを任意のレポートに即座に適用できます。
* **分類:** 別のディメンションのコンテキスト内でディメンションを表示できます。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **バウンス:** 単一のヒットから構成される訪問。See [Bounces](../components/c-variables/c-metrics/metrics-bounces.md) in the Components user guide. 単一アクセスも参照してください。
* **計算指標:** レポートで使用する既存の指標、統計関数および数式の組み合わせを許可します。See [Calculated metrics](../components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **キャンペーン:** 次を参照できます。
   * キャンペーン変数。トラッキングコードディメンションを設定します。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * トラッキングコードディメンションのデフォルトの分類。が自動的に作成されます。
   * Adobe Campaign Cloudの一部です。More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **チャネル:** 次を参照できます。
   * サイトセクションディメンションを設定するチャネル変数。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * マーケティングチャネルを参照してください。See [Marketing Channels](../components/c-marketing-channels/c-overview.md) in the Components user guide.
* **分類:** ディメンション値のグループ化を可能にするAdobe Analyticsの機能。See [Classifications](../components/c-classifications2/c-classifications.md) in the Components user guide.
* **クリックストリームデータフィード:** データフィードを参照してください。
* **コンバージョン変数:** eVarと同義語。カスタム値を格納し、変数値が期限切れになるまで保持します。See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **相関関係:** キーワードとして使用されなくなりました。ディメンションの分類に置き換えられます。以前のバージョンのAdobe Analyticsでは、クロス集計によりトラフィック変数を分類できました。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **現在のデータ:** 一部のレポートのオプションで、まだ処理されていない最近収集したデータを含めることができます。See [Current data](../analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **カスタムリンク:** ページビュー以外のデータを含むヒットのタイプ。See the [s.tl() function](../implement/js-implementation/function-tl.md) in the Implement user guide. 「ヒット」も参照してください。
* **顧客属性:** 属性データをアップロードできるExperience Cloud機能。See [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **カスタマーサポート委任:** アドビカスタマーケアに直接問い合わせることを承認されたユーザー。See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **Data Connectors:** サードパーティがAdobe Analyticsにデータをアップロードすることを可能にする完全な開発ソリューションです。サードパーティの顧客は、データコネクターを使用してAdobe Analyticsでデータを充実させることができます。ほとんどのdata connectorsは、データソースで使用される類似ワークフローを使用します。ユーザーガイドの"Data Connectors"を参照してください。
* **データフィード:** すべてのヒットを行と変数として個別の列としてリストする生データエクスポート。最も一般的に使用されるのは、Adobe Analyticsデータをサードパーティのデータベースにエクスポートするためです。See [Data feeds](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.
* **データソース:** ユーザーがファイルからAdobe Analyticsにデータをアップロードできるようにします。ファイルは通常FTPサイトから取得されます。See [Data Sources](../import/c-data-sources/datasrc-home.md) in the Import user guide.
* **Data Warehouse:** Adobe Analyticsの機能で、より大きなレポートをリクエストできます。See [Data Warehouse](../export/data-warehouse/data-warehouse.md) in the Export user guide.
* **ディメンション:** テキストなどの変数値を含むコンポーネントタイプです。例えば、ページ名、トラッキングコード、参照ドメインなどがあります。通常、指標は対応する指標です。
* **Dynamic Tag Management:** アドビの以前のtag managementソリューション。See [DTM implementation overview](../implement/c-implement-with-dtm/dtm-implementation-overview.md) in the Implement user guide. 代わりに、Adobe Experience Platform Launchを使用することをお勧めします。
* **イベントシリアル化:** 重複イベントを収集するための対策を実装するプロセス。See [Event serialization](../implement/js-implementation/event-serialization.md) in the Implement user guide.
* **eVar:** コンバージョン変数を参照してください。
* **イベント:** 成功イベントを参照してください。
* **ExcelClient:** キーワードとして使用されなくなりました。Report Builderの前身の名前。
* **有効期限:** コンバージョン変数のコンテキストで、値がバックエンドで持続する時間。この永続性により、イベントのヒット前に変数値にイベントを関連付けることができます。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **フロー:** Analysis Workspaceで、ユーザーがサイトでたどったパスを示すビジュアライゼーションのタイプ。See [Flow visualization](../analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis:** キーワードとして使用されなくなりました。data connectorsの旧名前。
* **グローバルレポートスイート:** 複数のサイトからヒットを収集するレポートスイートに指定された非公式の用語。
* **Hコード:** AppMeasurementへの接頭辞。以前のバージョンのAdobe Analyticsでは、コードバージョンはH24、H23.1などの"Hバージョン」で測定されていました。
* **ヒット:** Adobeデータ収集サーバーに送信される単一のイメージリクエスト。ページビューとカスタムリンクは、両方ともヒットと呼ばれます。
* **イメージリクエスト:** Adobeデータ収集サーバーとの通信に使用される透明1x1ピクセルの画像。Webサイトは、この非表示の画像を、データを含む長いクエリ文字列でリクエストします。Adobeは、非表示の画像を返し、受信したクエリ文字列を解析します。
* **Insight:** 次を参照できます。
   * Data Workbenchの旧名前。
   * カスタムインサイト。カスタムトラフィック変数の履歴名。
* **KPI:** 主要業績評価指標の略語。サイトのパフォーマンスを把握するための指標。各組織には、ビジネスのさまざまな局面を測定する異なるKPIがあります。See [Create a solution design document](../implement/prepare/solution-design.md) in the Implement user guide.
* **待ち時間:** データが収集されたとき、およびレポートでデータが利用可能になったときの遅延。レポートスイートの一般的な遅延は30~90分です。See [Latency](../technotes/latency.md) in the Technotes user guide.
* **起動:** Adobeの現在の実装ソリューションであるAdobe Experience Platform Launchの略称。See [Overview](https://docs.adobe.com/content/help/en/launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
* **リストprop:** 共通のトラフィック変数を変換して、同じヒット内の複数の値をサポートする設定。設定が有効になっている場合、カスタムトラフィック変数はリストpropになります。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **リストvar:** コンバージョン変数と別の変数。リスト変数は、同じヒットで複数の値をサポートし、変数値はコンバージョン変数と同様に訪問時に保持されます。組織で使用できるリストVarsは3つのみです。See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **ログイン会社名:** 組織が使用するレポートスイートの集まり。組織によっては、複数のログイン会社が組織の異なる部署に適用される場合があります。
* **指標:** 定量データを含むコンポーネントタイプです。指標値には通常、ページビュー数、訪問回数、売上高などの数値が含まれます。通常、ディメンションは対応するディメンションです。
* **マルチスイートタギング:** 同じヒットを複数のレポートスイートに送信すること。仮想レポートスイートの概要により、この方法はほとんど必要ありません。ほとんどのマルチスイートタギングの取組みは、グローバルレポートスイートに対応するのに役立ちます。
* **標準化:** すべての指標を占めるビジュアライゼーションを整理し、それらを均等な縦横比に強制的に均等化し、トレンドを簡単に比較できるようにする方法。
* **Omniture:** キーワードとして使用されなくなりました。2009年にアドビにより取得される前にAdobe Analyticsを所有している組織。
* **パス:** フローを参照してください。
* **ランクレポート:** 通常、指標を持つディメンションの後にあるレポート形式です。このタイプのレポートでは、サイト上で最も多く閲覧されたページなどのトップアイテムを表示できます。トレンドレポートも参照してください。
* **リアルタイム:** 待ち時間がほとんどないので、設定された変数がすぐに表示されます。See [Real-time reports](../admin/admin/realtime/realtime.md) in the Admin user guide.
* **レポートスイート:** データを送信する包括的なコンテナ。Adobe Analyticsのすべてのレポートは、レポートスイートを参照します。
* **RSID:** レポートスイートIDの省略形。レポートスイートにはわかりやすい名前とレポートスイートIDがあります。
* **ページビュー:** ページビュー数を増分するヒットのタイプ。See [Page views](../components/c-variables/c-metrics/metrics-page-view.md) in the Components user guide. 「ヒット」も参照してください。
* **処理ルール:** 次を参照できます。
   * 処理ルールでは、管理コンソールの特定のルールを使用してデータ収集を変更できます。See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * マーケティングチャネルの処理ルール。ヒットが属するマーケティングチャネルを決定する一連のルールです。See [Marketing channel processing rules](../admin/admin/marketing-channels-admin.md) in the Admin user guide.
* **prop:** トラフィック変数を参照してください。
* **s. t（）:** ページビューイメージリクエストを送信するAppMeasurementライブラリ内の関数の名前。Some AppMeasurement libraries use `s.track()` instead. See [s.t()](../implement/js-implementation/function-t.md) in the Implement user guide.
* **s<span>.</span>tl（）:** リンクトラッキングイメージリクエストを送信するAppMeasurementライブラリ内の関数の名前。Some AppMeasurement libraries use `s.trackLink()` instead. See [s.tl()](../implement/js-implementation/function-tl.md) in the Implement user guide.
* **Satellite:** キーワードとして使用されなくなりました。Dynamic Tag Managementの以前の製品名。
* **セグメント:** データの特定のサブセットに焦点を当てることができます。See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **セグメントコンテナ:** 取り込むデータ量を決定するセグメントの部分。コンテナは、ページビュー、訪問または訪問者に基づいていることができます。See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **シリアル化:** イベントシリアル化を参照してください。
* **サーバーコール:** イメージリクエストまたはヒットの代替名。ほとんどの場合、請求のコンテキストで使用されます。
* **単一アクセス:** ディメンションに固有の値のみがある訪問。複数の一意の値がない限り、訪問に複数のヒットを含めることができます。See [Single access](../components/c-variables/c-metrics/metrics-single-access.md) in the Components user guide. 「バウンス」も参照してください。
* **SiteCatalyst:** キーワードとして使用されなくなりました。Adobe Analyticsの以前の製品名。
* **下位関係:** キーワードとして使用されなくなりました。ディメンションの分類に置き換えられます。以前のバージョンのAdobe Analyticsでは、下位関係によってコンバージョン変数の分類機能が与えられていました。See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **成功イベント:** ユーザーが追跡したアクション。追跡するイベントや追跡に使用する成功イベント変数を組織によって決定します。See [Custom events](../components/c-variables/c-metrics/metrics-custom.md) in the Components user guide.
* **サポート対象ユーザー:** 詳しくは、カスタマーサポート委任を参照してください。
* **トラフィック変数:** propという語。単一ヒットのカスタム値を格納します。以前のバージョンのAdobe Analyticsではprop固有の値が与えられていましたが、プラットフォームの改善により、カスタムトラフィック変数が大幅に不要になりました。ほとんどの場合、カスタムコンバージョン変数（eVar）を使用することをお勧めします。See [Custom traffic variables](../components/c-variables/dimensionslist/reports-custom-traffic.md) in the Components user guide.
* **トレンドレポート:** 通常、指標を使用して複数の日付範囲を表示するレポート形式です。このタイプのレポートでは、指標の経時的なパフォーマンスを確認できます。ランクレポートも参照してください。
* **個別訪問者**:サイトを訪問した個別個人の数を表します。単一の実訪問者は複数の訪問を持つことができます。See [Unique visitor](../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide.
* **仮想レポートスイート:** 通常のレポートスイートを参照し、データを細分化できるデータの仮想コンテナ。データは仮想レポートスイートに送信されません。代わりに、データが通常のレポートスイートに送信され、収集されたデータから仮想レポートスイートが構築されます。See [Virtual report suites](../components/vrs/vrs-about.md) in the Components user guide.
* **訪問:** サイトで発生した個別セッション数を表します。See [Visits](../components/c-variables/c-metrics/metrics-visit.md) in the Components user guide.
* **VISTAルール:** アドビが作成したカスタムロジックで、データサーバサイドのコピー、解析、フィルターを行うことができます。VISTAルールは通常、追加費用を負担します。処理ルールも参照してください。
* **ウェブビーコン:** 詳しくは、イメージリクエストを参照してください。
