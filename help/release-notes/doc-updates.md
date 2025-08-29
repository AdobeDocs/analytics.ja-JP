---
title: Adobe Analytics テクニカルドキュメントのアップデート
description: Adobe Analytics ドキュメントセットの大幅なアップデート。
short-title: Analytics documentation updates
feature: Release Notes
exl-id: fe8e3c4c-6782-46f7-8e28-4f8f54807788
mini-toc-levels: 3
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: ht
source-wordcount: '6506'
ht-degree: 100%

---

# Adobe Analytics テクニカルドキュメントのアップデート

2019年1月以降の Adobe Analytics ドキュメントセットのアップデートについて説明します。

* [!UICONTROL Customer Journey Analytics] について詳しくは、[こちら](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja)を参照してください。
* ストリーミングメディアサービスについて詳しくは、[Analytics でのオーディオとビデオの測定](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja)を参照してください。

## ドキュメントの主な更新の詳細

### 2025年 {#year2025}

| 機能 | 説明 |
| --- | --- |
| **2025年8月** | |
| 廃止の警告 | [分類ルールビルダー](/help/components/classifications/crb/classification-rule-builder.md)および[分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)の節の記事に廃止の警告を追加しました。 |
| **2025年7月** | |
| 処理ルール | 処理ルールのドキュメントを完全に一新し、インターフェイスと現在のユースケースについて詳しく説明しました。 |
| デバッガー | Analysis Workspace でプロジェクトデバッガーを有効、使用、無効にする方法に関する新しい記事です。 |
| フロービジュアライゼーションパフォーマンスの推奨事項 | 1 つのフロービジュアライゼーションで 10 個を超えるノードを展開すると、レポート時間に影響を与える可能性があるという情報を追加しました。 |
| レビューと更新 | Analysis Workspace ドキュメントのレビューと更新です。必要に応じて、ドキュメントは Analysis Workspace の Customer Journey Analytics ドキュメントと同期されるようになりました。 |
| **2025年6月** | |
| 新しいショートカットアクション | Analysis Workspace の新しいキーボードショートカットを使用すると、プロジェクトで上下に [Workspace パネルを移動](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#move-panel-actions)できるようになりました。 |
| **2025年3月** |  |
| Analytics インベントリ | [Analytics インベントリ](https://experienceleague.adobe.com/ja/docs/analytics/admin/admin-tools/analytics-inventory)では、プロジェクトとコンポーネント、レポートスイート、ユーザーの数など、Adobe Analytics 環境の包括的な概要を提供します。 |
| Customer Journey Analytics アップグレードガイド | Adobe Analytics から Customer Journey Analytics にアップグレードするための[ステップバイステップガイド](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations?lang=ja#recommended-upgrade-steps-for-most-organizations)を生成できます。 |
| Data Warehouse の書き出しの日付形式を明確化しました | Data Warehouse の書き出しにおける時間ベースのディメンション値には、非標準の日付形式が使用されています。Data Warehouse の書き出しから日付の値を解釈する方法を説明する情報を追加しました。 <p>[Data Warehouse でのコンポーネントのサポート](/help/export/data-warehouse/component-support.md)の[異なる方法でサポートされるディメンション（非標準の日付形式）](/help/export/data-warehouse/component-support.md#dimensions-supported-in-a-different-way-non-standard-date-formatting)を参照してください。</p> |
| IP 除外に関する情報を更新しました | [IP 除外](/help/admin/admin/exclude-ip.md)が有効になるまでに最大 5 分かかることと、変更は新しいヒットにのみ適用されること（除外を設定する前に取得されたデータは影響を受けない）を説明する情報を追加しました。 <p>また、読みやすさを向上させるために、コンテンツのレイアウトも更新しました。</p> |
| **2025年2月** |  |
| データフィードの一時停止と再アクティブ化に関する情報の更新 | [データフィードの一時停止と再アクティブ化](/help/export/analytics-data-feed/df-manage-feeds.md#activate-a-data-feed)を実行する際のライブフィードの動作を明確にしました。フィードの一時停止から再アクティブ化を実行するまで、データ処理は行われません。 |
| トランザクション ID の保持期間の変更 | トランザクション ID の保持期間である 90 日は、25 か月に延長されました。transactionID 変数はトランザクションを一意に識別し、ヒットがデータソースを介してアップロードされたデータに結び付けられるようにします。詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/analytics/implementation/vars/page-vars/transactionid?lang=ja)と[こちら](https://experienceleague.adobe.com/ja/docs/analytics/import/data-sources/transactionid?lang=ja)を参照してください。 |
| Livestream API - クライアント実装 | Livestream データを使用するには、[Livestream クライアント実装](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/)を使用します。 |
| Classifications API の更新 | [サーバーから個々の分類フィールドまたはキーを削除](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/)できるようになりました。これにより、DELETE メソッドを使用して分類データセット全体を削除する代替手段が提供されます。 |
| **2025年1月** |  |
| Data Feeds API リファレンス | [Data Feeds API のリファレンス](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs)が使用可能になりました。 |
| 新しい Report Builder でのスケジュールに関する新しいドキュメント | [スケジュール](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/schedule-reportbuilder)すると、新しい Report Builder ワークブックをスケジュールできるだけではありません。さらに、従来のワークブックを変換する際に、古いスケジュールされたタスクのメタデータを取得することもできます。 |
| Analysis Workspace でのレポート（テンプレートとも呼ばれる）の改善 | レポート（[テンプレート](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/templates/use-templates?lang=ja)とも呼ばれる）で様々な改善が行われました。 |


### 2024 {#year2024}

| 機能 | 説明 |
| --- | --- |
| **2024年10月** |  |
| Analysis Workspace のパフォーマンスのリクエスト要因に関する新しい情報 | [Analysis Workspace のパフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)の記事の新しい[リクエスト要因](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md#request-factors)の節では、リクエストの処理方法と、処理時間に影響を与える様々な要因について説明します。 |
| 新しい Report Builder | Mac、Windows、web ブラウザーでサポートされている、合理化された Report Builder アドインの[新しいドキュメント](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/rb-overview)。 |
| **2024年8月** | |
| アラートマネージャー | [アラートマネージャー](/help/components/c-alerts/alert-manager.md)に関するドキュメントを合理化しました。明確さと精度を高める更新が行われました。 |
| **2024年7月** | |
| 成功イベント | [成功イベント](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)に関するドキュメントを合理化しました。明確さと精度を高める更新が行われました。 |
| 場所を管理する際は、少なくとも 1 つのアカウントタイプを選択する必要があります | 管理者が[書き出しと読み込みに使用するアカウントタイプを制限](/help/components/locations/locations-manager.md#limit-the-account-types-that-are-available-to-users)している場合、少なくとも 1 つのアカウントタイプを選択する必要があることを明確にしました。 |
| クイック計算指標に関する情報を追加しました | [計算指標ビルダーで作成された計算指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects)と [1 つのプロジェクト内でクイック計算指標として作成された計算指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)との違いを明確にするために、[指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md)の情報を更新しました。また、クイック計算指標を作成する方法に関する詳細も追加しました。<p>計算指標ビルダーで作成した計算指標はコンポーネントリストで使用でき、組織全体のプロジェクトに適用できます。一方、クイック計算指標として作成した計算指標は、作成されたプロジェクト内でのみ使用できます。</p><p>また、[指標を作成](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)の情報を更新して、同様の説明を追加しました。</p> |
| 「リファラータイプ」ディメンションに threads.net を追加しました | [「リファラータイプ」ディメンション](/help/components/dimensions/referrer-type.md)で使用されるソーシャルネットワークのリストに threads.net を追加しました。 |
| データフィードの管理に関するドキュメントを更新しました。 | [データフィードの管理](/help/export/analytics-data-feed/df-manage-feeds.md)の情報を更新して、明確化しました。 <p>更新内容は次のとおりです。</p><ul><li>情報を簡単にスキャンして使用できるように、様々なタスクに対して個別のセクションを作成しました。</li><li>再アクティブ化されたライブフィードの動作の変更に関する情報を追加しました。これらの変更は現在、限定提供となっており、まだすべてのお客様が利用できるわけではありません。</li><li>データフィードを削除する前に、そのステータスがアクティブである必要があることを示す情報を追加しました。</li> |
| 一般的なエラーメッセージを更新しました。 | [一般的なエラーメッセージ](/help/analyze/analysis-workspace/workspace-faq/error-messages.md)に対するマイナーな更新を行いました。 |
| **2024年6月** | |
| ストリーミングメディアサービスの機能を参照する製品名を更新しました。 | ストリーミングメディアデータを収集して Analysis Workspace に表示するストリーミングメディア機能のセットを参照する際に、「メディア分析」と「ストリーミングメディア」のインスタンスを「ストリーミングメディアコレクションアドオン」と「ストリーミングメディアコレクション」という名前に置き換えました。 <p>これらの更新は、Adobe Analytics のドキュメントと[ストリーミングメディアコレクションのドキュメント](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-overview)の全体で利用できます。</p> |
| アラートに関するドキュメントの改善 | アラートに関するドキュメントを更新および改善しました。これらの更新には、[アラートの作成](/help/components/c-alerts/alert-builder.md)、[アラートの管理](/help/components/c-alerts/alert-manager.md)、[概要情報](/help/components/c-alerts/intellligent-alerts.md)に関する情報が含まれます。 |
| 非推奨`cookieDomainPeriods` | AppMeasurement が Cookie を設定する適切なドメインを自動的に検出するようになったので、[`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) 変数は非推奨（廃止予定）になりました。 |
| Data Connectors ドキュメントの廃止 | Data Connectors のサポート終了ページを[販売終了した製品](https://experienceleague.adobe.com/ja/docs/discontinued/using/data-connectors)に移動しました。 |
| **2024年5月** | |
| データフィードとデータウェアハウスで Google Cloud Platform の組織ポリシー制約を使用する際に必要な情報 | [データフィード](/help/export/analytics-data-feed/create-feed.md)と[データウェアハウス](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)のドキュメントに、アドビ所有の Google Cloud Platform 組織 ID を追加しました。 <p>この情報は、Google Cloud Platform で[組織ポリシーの制約](https://cloud.google.com/storage/docs/org-policy-constraints)を使用している組織にのみ必要です。</p> |
| プロジェクトへのコンポーネントの追加に関するドキュメント | [Analysis Workspace のプロジェクトに様々なタイプのコンポーネントを追加](/help/analyze/analysis-workspace/components/use-components-in-workspace.md)する方法について、一般情報を追加しました。 |
| Advertising Analytics ドキュメントの更新 | [Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-workflow.md) ユーザーインターフェイスの更新に合わせてドキュメントを更新しました。 |
| XDM オブジェクト変数のコンテキストデータ変数への明示的なマッピング | [XDM オブジェクト変数マッピングを使用してコンテキストデータ変数を明示的に設定](/help/implement/aep-edge/xdm-var-mapping.md#explicit-mapping)する機能を文書化しました。 |
| Adobe Analytics から Customer Journey Analytics へのアップグレードに関する新しいドキュメント | Adobe Analytics から Customer Journey Analytics にアップグレードする組織の場合、組織の現在の Adobe Analytics 実装と長期目標に基づいて、複数のアップグレードオプションと多くの考慮事項があることに留意する必要があります。<p>次の内容に対する理解を深めるのに役立つ、新しいドキュメントリソースが利用できるようになりました。</p><ul><li>存在する様々なアップグレードパス</li><li>組織の現在の Adobe Analytics 実装に基づいて利用可能なアップグレードパス</li><li>各アップグレードパスのメリットとデメリット</li><li>各アップグレードパスの段階的なガイダンス</li><li>履歴データの処理に関する考慮事項</li><li>その他</li></ul><p>[詳しくは、Customer Journey Analytics へのアップグレードを参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted)。</p> |
| カスタム日付範囲に関するドキュメントを更新 | 現在の製品の機能とデザインに一致させるために、[カスタム日付範囲の作成](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md)に関連するスクリーンショットと手順を更新しました。 |
| **2024年4月** | |
| 分類セットの「所有者」に関連するドキュメントを削除しました。 | 「所有者」フィルターと列を[分類セットマネージャー](/help/components/classifications/sets/manage/set-manager.md)から削除し、「所有者」フィールドを[分類セット設定](/help/components/classifications/sets/manage/settings.md)から削除しました。 <p>ドキュメントを更新し、このフィルター、列、フィールドを削除しました。</p> |
| クラウドの読み込み場所と書き出し場所の設定に関するドキュメントの折りたたみ可能な節を削除しました。 | クラウドアカウントタイプの説明に関する[クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md)の折りたたみ可能な節を削除しました。 |
| **2024年3月** | |
| AppMeasurement のアップデート | AppMeasurement アップデート v2.26.0 の[リリースノート](/help/implement/appmeasurement-updates.md)。<br/>[`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md) 設定変数ドキュメントへの参照と更新が含まれます。 |
| 「使用場所」列に関する使用状況情報は、2023年9月以降のみ使用可能です。 | [プロジェクトのランディングページ](/help/analyze/landing.md)の&#x200B;**使用場所**&#x200B;列に関する使用状況情報は、2023年9月までしか遡らないことを明確にしました。 |
| **2024年2月** | |
| Data Warehouse リクエストの管理に関する情報の更新 | デフォルトでは、ユーザーは [Data Warehouse リクエストを管理](/help/export/data-warehouse/data-warehouse-requests-manage.md)する際に自分が作成したリクエストのみを表示できることを明確にしました。 |
| プロジェクト共有ドキュメントの更新 | [共有プロジェクトの表示](/help/analyze/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you)方法についての情報を追加しました。<p>また、[個々または複数のプロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)に関する情報も整理しました。</p> |
| データウェアハウスとデータフィードで、Azure SAS と Azure RBAC にファイルをアップロードする権限要件を追加しました。 | Azure SAS と Azure RBAC にファイルをアップロードする正確な権限要件を追加しました。[データウェアハウスの宛先を設定をする](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)場合や[データフィードの宛先を設定する](/help/export/analytics-data-feed/create-feed.md)場合に使用します。 |
| データウェアハウスとデータフィードで、ファイルを Amazon S3 と GCP バケットにアップロードする権限要件を追加しました。 | ファイルを Amazon S3 バケットと Google Cloud Platform バケットにアップロードする正確な権限要件を追加しました。[データウェアハウスの宛先を設定する](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)場合や[データフィードの宛先を設定する](/help/export/analytics-data-feed/create-feed.md)場合に使用します。 |
| **2024年1月** | |
| コンポーネントの移行を個々の IMS 組織に適用 | [コンポーネントの移行](/help/admin/admin/component-migration/component-migration.md)では IMS 組織間の移行がサポートされていないことを明確にしました。 |
| 特定の情報は管理者のみが利用できることを明確化 | [計算指標マネージャー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)および[セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md)で説明している「前回の使用」列と「使用場所」列は、システム管理者のみが使用できることを示す情報を追加しました。 |
| メディア分平均オーディエンスドキュメントの更新 | [メディア分平均オーディエンスパネル](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)の情報を更新して、明確化しました。<p>改善点を以下に示します。</p> <ul><li>情報の組織化の改善</li><li>タスクベースの情報を示す手順の追加</li></ul> |

### 2023年 {#year2023}

| 機能 | 説明 |
| --- | --- |
| **2023年12月** | |
| ボットルールに関するドキュメントの改善 | [ボットルールの理解と設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)の情報を更新して、明確化しました。<p>改善点を以下に示します。</p> <ul><li>説明的にした記事のタイトルを更新</li><li>情報の組織化の改善</li><li>タスクベースの情報を示す手順の追加</li><li>ボットルールをアップロードする際の CSV ファイル要件に関する詳細を追加</li></ul> |
| 新しいレポートの節 | [テンプレートの使用](/help/analyze/analysis-workspace/templates/use-templates.md)と[会社テンプレートの作成](/help/analyze/analysis-workspace/templates/create-templates.md)に関する情報を含む、新しいレポートの節を追加しました。 |
| 異常値検出と貢献度分析に関するドキュメントの更新 | 異常値検出と貢献度分析に関するドキュメントは、以前、Virtual Analyst に関する節に記載していました。次の変更を行いました。 <ul><li>Virtual Analyst という用語はドキュメントから削除しました。</li><li>[異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)に関する節は、Analysis Workspace の節のすぐ下に移動しました。</li><li>貢献度分析ドキュメントは、異常値検出ドキュメントに統合しました。</li></ul> |
| 「Attribution IQ」を「アトリビューション」に変更 | ドキュメント全体にわたって「Attribution IQ」のすべてのインスタンスを「[アトリビューション](/help/analyze/analysis-workspace/attribution/overview.md)」に変更しました。 |
| **2023年11月** | |
| Activity Map のアクティブ化／有効化に関するトピックの更新 | [Web SDK](/help/analyze/activity-map/getting-started.md)（手動および Adobe Experience Platform タグ拡張機能経由の両方）コンテンツを追加しました。 |
| **2023年10月** | |
| レポートアクティビティマネージャーにログ情報を追加しました。 | レポートアクティビティマネージャーの[レポートアクティビティのキャンセルとその後の制限](/help/admin/admin/reporting-activity-manager/reporting-activity-cancel-requests.md)が[ログ](/help/admin/admin/logs.md)にキャプチャされるという情報を追加しました。 |
| Data Warehouse コンポーネントのサポートの更新 | Data Warehouse の一部のコンポーネントの可用性を追加し、他のコンポーネントの可用性を削除しました。これらの変更は、[Data Warehouse でのコンポーネントのサポート](/help/export/data-warehouse/component-support.md)に反映しています。 <ul><li>訪問の深さディメンションのサポートを追加しました（サポートされていないディメンションのリストから訪問の深さを削除しました）</li><li>パーティシペーション指標のサポートを削除しました（サポートされていない指標のリストにパーティシペーション指標を追加しました）</li><li>年、四半期、月、週、日、時間、分の各時間ベースのディメンションがサポートされるようになりました（サポートされていないディメンションのリストからこれらのディメンションを削除しました）。 <p>以前は、精度が選択されていた場合、データウェアハウスでは、フリーフォームテーブルの最初の列でのみこれらのディメンションをサポートしていました。現在、これらのディメンションは常にサポートされています。</p><p>ただし、これらのディメンションを使用する場合、日付の出力は標準ではありません。年は 1900 年でオフセットされ、月は 0 から始まります。</li></ul> |
| **2023年9月** | |
| メディア再生滞在時間パネルの記事の構造を更新しました。 | メディア再生滞在時間というフォルダーを削除し、フォルダーの内容を 1 つの記事である[メディア再生滞在時間](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)パネルに統合しました。 <p>この変更は、その他のパネルのドキュメントに沿ったものになります。</p> |
| 基本を学ぶコンテンツの機能強化 | 管理者、アナリスト、エンドユーザー、開発者向けの主な基本を学ぶタスクとリソースの概要を説明する情報を追加しました。以下の新しい記事を利用できます。 <ul><li>[基本を学ぶ（役割別）](/help/analyze/get-started/get-started-by-role.md)</li><li>[Analytics インターフェイスについて](/help/analyze/get-started/analytics-interface.md)<li>[ユースケース](/help/analyze/get-started/use-cases.md)</li></ul> |
| ストリーミングメディアコレクションのレポートドキュメントの改善 | API ドキュメントを独自の節に統合し、一部の記事の順序を調整するなど、ストリーミングメディアコレクションガイドの「レポート」節の内容の一部を再編成しました。 <p>製品内の名前に合わせて、Media Workspace テンプレートの記事の名前を [Workspace のメディアレポート](https://experienceleague.adobe.com/docs/media-analytics/using/media-reports/media-workspace-templates.html?lang=ja)に変更しました。 </p> |
| **2023年8月** | |
| データフィードの明確化 | [開始日と終了日の定義](/help/export/analytics-data-feed/create-feed.md)を更新し、履歴データのデータフィードを処理する際に、データが収集されている過去の任意の日付に開始日を設定できることを明確化しました。 |
| Adobe Experience Platform Edge Network のデータ処理 | Adobe Analytics が [Edge Network からのデータを処理](../implement/aep-edge/overview.md)する方法に関するコンテンツを追加しました。 |
| メディア再生滞在時間パネル | 読みやすさを向上させるために、[メディア再生滞在時間パネル](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)のコンテンツを更新しました。 |
| スケジュールされたプロジェクトの管理に関するコンテンツの移動 | Analytics コンポーネントガイドに[スケジュールされたプロジェクト](/help/components/scheduled-projects-manager.md)という新しい記事を作成しました。このコンテンツは、以前は Analytics ツールガイドの[プロジェクトのスケジュール](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)という記事に記載されていました。 |
| 実装方法の比較 | 様々な実装方法を比較するドキュメントを更新しました。[詳細情報](../implement/prepare/comparison.md) |
| データフィード用の SFTP を設定する際、アドビカスタマーケアが必要ないことを明記しました | [SFTP を使用した外部 FTP アカウントへのアドビデータの送信](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)で、データフィード用の SFTP を設定するために、お客様がアドビカスタマーケアとのやり取りが不要であることを明記しました。 <p>また、SFTP は推奨しなくなり、データフィードを設定する際にはクラウドの宛先を使用する必要があるというメモも追加しました。</p> |
| ストリーミングメディアコレクションのドキュメントの改善 | ストリーミングメディアコレクションのドキュメントに、次の改善を加えました。 <ul><li>明確さを改善し、Customer Journey Analytics に関連する情報を含めるために、[一般的な概要](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja)を更新しました。</li><li>Edge の実装と Analytics のみの実装を明確に区別するために、[実装の概要](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=ja)を更新しました。また、様々な実装方法を説明する図も含めました。</li><li>[Edge の実装](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/edge-recommended/prerequisites-edge.html?lang=ja)および [Analytics のみの実装](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/analytics-only/prerequisites-analytics.html?lang=ja)に固有の前提条件を追加しました。また、[一般的な前提条件](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/prereqs.html?lang=ja)も更新しました。</li><li>[Media SDK、タグを使用した拡張機能、OTT SDK の取得](https://experienceleague.adobe.com/docs/media-analytics/using/getting-started/download-sdks.html?lang=ja)の記事にある表を更新し、*サポートされるソリューション*&#x200B;と&#x200B;*実装方法*&#x200B;の新しい列を追加しました。</li><li>ドキュメントの[実装](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/overview.html?lang=ja)領域の記事の内容と構成を合理化しました。これに、Edge の実装および Analytics のみの実装別の実装の分類を含めました。</li><li>[トラッキング](https://experienceleague.adobe.com/docs/media-analytics/using/tracking/track-core-overview.html?lang=ja)の下で必要のなかった余分な階層レベルを削除し、変更した URL のリダイレクトをこの節に追加しました。</li><ul> |
| **2023年7月** | |
| Adobe Experience Platform Edge Network API | [Adobe Experience Platform Edge Network API](../implement/aep-edge/api/overview.md) を使用して Adobe Analytics によるデータ収集を実装するタイミングと方法に関する、より包括的なドキュメントを追加しました。例えば、デスクトップアプリケーション、IoT デバイス、セットトップボックスに Adobe Analytics を使用したデータ収集を実装します。 |
| グローバル会社 ID | ログインしている Analytics 会社の[グローバル会社 ID を検索する方法](../admin/admin/company/web-services-admin.md)を文書化しました。この ID は、Analytics 2.0 API で必要です。 |
| FTP のサイズ制限を更新しました | デフォルトの [FTP データ保存制限](/help/export/ftp-and-sftp/ftp-limits.md)を 100 GB に変更しました。 |
| 新しい AppMeasurement 変数 | 変数 `decodeLinkParameters` は、実装がリンクトラッキング変数でマルチバイト文字をエンコードするというエッジケースに対応しています。[詳細情報](../implement/vars/config-vars/decodelinkparameters.md) |
| 分類データを取り込むためのクラウドアカウントストレージの場所の設定 | 分類セットの自動処理に使用するクラウドアカウントストレージの場所を管理できるようになりました。[詳細情報](/help/components/locations/configure-import-accounts.md) |
| データ修復フィルターの機能強化 | データ修復に次の 3 つのフィルタリング機能強化を追加しました。[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) |
| **2023年6月** | |
| 分類セットの新機能 | [分類セット](/help/components/classifications/sets/overview.md)を更新し、次のいくつかの新機能を追加しました。<ul><li>**統合**：分類セットを単一の統合された分類セットに結合します。統合された分類セットは、他の分類セットと同様に使用することも、Customer Journey Analytics のルックアップデータセットとして使用することもできます。[詳細情報](../components/classifications/sets/consolidations/manage.md)</li><li>**ルール**：分類セット内のルールに基づいて値を自動的に分類します。[詳細情報](../components/classifications/sets/manage/rules.md)</li><li>**自動読み込み**：クラウドストレージの宛先から分類データを自動的に読み込みます。[詳細情報](../components/classifications/sets/manage/schema.md)</li></ul> |
| 計算指標のアップデート | スクリーンショットやプロシージャの手順の更新など、計算指標に関する様々な記事が更新されました。これらの変更は、ドキュメントを現在の Adobe Analytics 機能とインラインにするために行われました。 |
| データフィード書き出しの安全な宛先 | データフィードを次のクラウドストレージの宛先に送信できるようになりました。<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>以前に使用可能だった宛先（FTP、SFTP、S3、Azure Blob）は、推奨されなくなりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=ja) |
| Workspace のボットレポート | ボットレポートが Analysis Workspace で使用できるようになりました。この機能には、次のようないくつかの追加機能が付属しています。<ul><li>新しいディメンション：[ボット名](/help/components/dimensions/bot-name.md)</li><li>2 つの新しい指標：[ボットページビュー数](/help/components/metrics/bot-page-views.md)および[ボットの発生件数](/help/components/metrics/bot-occurrences.md).</li><li>新しい計算指標テンプレート：[ボットページビュー数の割合](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新しい Workspace レポート：ボットレポート</li></ul>新しいディメンションと指標には、2023年3月以降にバックフィルされたデータが含まれます。 |
| **2023年5月** | |
| ディープリンク（モバイルアプリ）ドキュメント | ユーザーが、アプリ内のスコアカードプロジェクトに直接アクセスできるスコアカードへのリンクを送信できるようにします。[詳細情報](/help/analyze/mobile-app/create-scorecard.md#shareable-link) |
| Analytics ダッシュボードアプリ（モバイルアプリ）の更新されたホーム画面に関するドキュメント | 更新された新しいホーム画面では、すべてのスコアカードが、統合された 1 つのスコアカードリストに表示されます。[詳細情報](/help/analyze/mobile-app/executive.md#use-dashboards) |
| Spectrum アイコン | 必要に応じて、ドキュメント内のユーザーインターフェイスアイコンのスクリーンショットを、アドビの [Spectrum Design System](https://spectrum.adobe.com/page/icons/) の同等のアイコンへの参照に置き換えました。 |
| レポートアクティビティマネージャー | このベータ版ドキュメント、特に[個々のレポートスイートのレポートアクティビティの表示](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=ja#view-reporting-activity-for-individual-report-suites)に関する節を更新しました。 |
| Analysis Workspace の概要 | より一般的な概要情報と関連コンテンツへのリンクを含むように、[Analysis Workspace の概要](/help/analyze/analysis-workspace/home.md)の概要を更新しました。 |
| プロジェクトの作成 | Analysis Workspace で[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)を行う方法を詳しく説明する新しい記事を作成しました。 |
| 左側のパネルでのコンポーネントの並べ替え | 左側のパネルでのコンポーネントのリストの並べ替えに関する情報を追加しました。詳しくは、[コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)の「コンポーネントリストの検索、フィルタリング、並べ替え」の節を参照してください。 |
| フリーフォームテーブルからの動的ディメンションを含む行の削除 | 「x」アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除する方法に関する情報を追加しました。[テーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)の「テーブルから特定の行をすばやく除外する」の節を参照してください。 |
| パネル内にビジュアライゼーションを追加するボタン | Analysis Workspace の各パネルの下部にある、ビジュアライゼーションをすばやく追加できる新しいボタンに関する情報を追加しました。[ビジュアライゼーションの概要](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)の「パネルへのビジュアライゼーションの追加」セクションを参照してください。 |
| **2023年4月** | |
| ユーザーアセットの転送と、アカウントの有効期限の設定 | [ユーザーアセットの転送と、アカウントの有効期限の設定](/help/admin/admin/user-management2/users-assets.md)を行う方法に関する情報を追加しました。 |
| Adobe Analytics 2.0 API に関する 2 つの新しいエンドポイントガイド | <ul><li>[Analytics Dimension API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics Metrics API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> |
| プロジェクトセグメント（アドホックおよびクイックセグメント） | プロジェクトセグメントに関するドキュメントを合理化し、重複した情報を削除しました。アドホックセグメントの作成手順は、[クイックセグメントの作成](/help/analyze/analysis-workspace/components/segments/quick-segments.md)手順と統合しました。 |
| 動的検索 | [動的検索](/help/export/analytics-data-feed/c-df-contents/dynamic-lookups.md)に関する追加情報を追加しました。以前は、情報は、複数の動的検索の 1 つであるモバイル属性に対してのみ存在していました。 |
| **2023年3月** | |
| Activity Map の Web SDK サポート | [Adobe Analytics の実装](/help/implement/home.md)を更新しました。 |
| トラフィック変数（prop）の概要 | 記事の内容を明確にし、改善するための節と段階的な手順を追加しました。「トラフィック変数レポートの有効化」という記事の内容を統合し、その記事を削除しました。[トラフィック変数（prop）の概要](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)を参照してください。 |
| 内部 URL フィルター | 記事の内容を明確にし、改善するための節と段階的な手順を追加しました。[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)を参照してください。 |
| モバイルスコアカードでのデータストーリーの作成 | [データストーリー](/help/analyze/mobile-app/create-scorecard.md#create-data-stories)は、中心的なテーマや指標に基づいて作成された、サポート対象データポイント、ビジネスコンテキスト、関連指標のコレクションです。 |
| デフォルトの計算指標 | [アドビが提供するデフォルトの計算指標](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)を説明するコンテンツを追加しました。 |
| データ辞書 | <p>データ辞書の[概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)、[表示](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md)、[編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)、[監視](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)など、データ辞書に関する新しいドキュメントを追加しました。</p><p>データ辞書機能を説明するために、[コンポーネントの説明の追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md)の情報を更新しました。</p> |
| プロジェクトのリンク共有（ログインは不要） | <p>Analysis Workspace へのアクセス権を持たないユーザーとプロジェクトの読み取り専用リンクを共有する方法を説明するために、既存のドキュメントを更新しました。</p> <p>ユーザードキュメントの更新内容には、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)と[共有可能なリンクの作成](/help/analyze/analysis-workspace/curate-share/shareable-links.md)が含まれています。</p> <p>[環境設定](/help/analyze/analysis-workspace/user-preferences.md)に管理者向けのオプションを追加しました。</p> |
| **2023年2月** | |
| 実装 | [Web およびモバイル用 Adobe Analytics の実装](../implement/home.md)方法に関する内容を更新しました。 |
| Workspace のカレンダーと日付範囲 | 内容を更新して、相対的な日付範囲、数式計算の更新およびカレンダー UI の変更について説明しました。[パネルを基準とする相対的な日付範囲について](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)を参照してください。 |
| モバイルスコアカード | 比較日付範囲の表示／非表示を切り替える方法について説明する新しい節をドキュメントに追加しました。Customer Journey Analytics の[比較日付範囲の表示](/help/analyze/mobile-app/create-scorecard.md)を参照してください。 |
| 1.4 API | [Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) は完全に書き直され、現在 Adobe Developer で公開されています。 |
| 実装タイプでのトラッキング | Experience Cloud ID サービスに対応するために、[異なる実装タイプでのトラッキング](../implement/use-cases/cross-type-implementation.md)の使用例を更新しました。 |
| **2023年1月** | |
| テーブルのフィルタリングと並べ替え | [テーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)に関する記事の内容を更新しました（手順の追加や使用可能なオプションの説明など）。この記事の名前を「テーブルのページネーション、フィルタリングおよび並べ替え」から変更しました。 |
| フォルダー | [フォルダー管理](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)用の専用ページ。 |
| ユーザー環境設定 | 多くの追加のユーザー環境設定は、現在は、[環境設定](/help/analyze/analysis-workspace/user-preferences.md)で使用できます。 |
| プロジェクトの自動保存 | コンテンツが更新され、[プロジェクトの保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)に自動保存機能を含めるようにしました。 |
| ランディングページ | 新しい[ランディングページの更新](/help/analyze/landing.md) |

### 2022 {#year22}

| 機能 | 説明 |
| --- | --- |
| **2022年11月** | |
| 同意管理変数 | [同意管理のオプトイン](/help/components/dimensions/cm-opt-in.md)と[同意管理のオプトアウト](/help/components/dimensions/cm-opt-out.md)の専用ページ。 |
| 複数通貨の更新 | [複数通貨のサポート](/help/implement/vars/config-vars/currencycode.md)に関するページが更新されました。 |
| **2022年10月** |  |
| Data Workbench | [提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja) |
| クライアントヒント | 新しい[概要とよくある質問](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=ja)。 |
| 主要指標の概要 | [主要指標の概要](/help/analyze/analysis-workspace/visualizations/key-metric.md)ビジュアライゼーションに関する新しいトピック  |
| 分類セット | 新しいユーザー[分類セット](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=ja)エクスペリエンスは、分類とルールを管理できる単一のインターフェイスを提供し、顧客が所有する分類データの可視性を向上させます。 |
| モバイルアプリ：カスタム詳細ビュー | [カスタム詳細ビュー](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=ja)に関する新しいトピック。 |
| VISTA | [VISTA ルール](/help/technotes/vista.md)の基本を説明する新しいページ。 |
| **2022年9月** | |
| コンビネーショングラフ | [コンボグラフ](/help/analyze/analysis-workspace/visualizations/combo-charts.md)のビジュアライゼーションに関する新しいトピック。 |
| 新しくなったプラグイン | [getvalonce](/help/implement/vars/plugins/getvalonce.md) 実装プラグインの更新済みバージョン。 |
| 新しい設定変数 | [collectHighEntropyUserAgentHints](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) に関するドキュメント |
| 高エントロピーのクライアントヒント | アドビが User-Agent に加えて[クライアントヒント](/help/technotes/client-hints.md)を使用してデバイス情報を特定している方法に関する新しいトピック。 |
| 処理順序 | [処理順序](/help/technotes/processing-order.md)に関する単一のヘルプトピックを提供するために、様々なヘルプページが集約されています。 |
| **2022年8月** | |
| Edge コレクション用 XDM でのリスト変数のサポート | Web SDK を使用してデータを収集するお客様が、XDM を使用してリスト変数のコンテンツを指定できるようにします。[詳細情報](../implement/vars/page-vars/list.md#list-variables-using-the-web-sdk) |
| 製品文字列変数を設定する際の、Edge コレクション用 XDM の SKU フィールドの使用 | Web SDK を使用してデータを収集するお客様が SKU 値を使用して、products 変数の product フィールドを設定できるようにします。[詳細情報](../implement/vars/page-vars/products.md#products-using-the-web-sdk) |
| **2022年6月** |  |
| Edge コレクション用 XDM でのマーチャンダイジング変数 | [Edge コレクション用 XDM でのマーチャンダイジング変数のサポート](/help/components/dimensions/evar-merchandising.md)に関するドキュメント |
| Experience Platform Edge ドキュメント | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md)、[Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md)、[Edge API](/help/implement/aep-edge/api/overview.md) 経由の Adobe Analytics の実装に関する新しい記事。 |
| フロービジュアライゼーションのドキュメントを更新しました | [新規 UI](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md) に基づく |
| モバイルスコアカードでの注釈の共有に関するドキュメント | [ワークスペースで作成される注釈は、モバイルスコアカード](/help/analyze/analysis-workspace/components/annotations/mobile-annotations.md)で表示できます。 |
| **2022年5月** | |
| Edge Network を介したライフサイクルディメンションおよび指標の入力 | Edge Network に送信されたモバイルライフサイクルデータが、Analytics レポートに表示されるようになりました。XDM フィールドを既存のモバイルライフサイクルレポートにマッピングする方法について詳しくは、[Analytics 変数のマッピング](/help/implement/aep-edge/xdm-var-mapping.md)を参照してください。 |
| **2022年4月** | |
| Adobe Analytics ランディングページの更新 | [Analysis Workspace と Reports &amp; Analytics の共同ランディングページ](/help/analyze/landing.md)を更新し、操作性とナビゲーションのしやすさを改善しました。 |
| [!UICONTROL ページの概要]パネルに関する新しいトピック | [ページの概要パネル](/help/analyze/analysis-workspace/c-panels/page-summary.md) |
| [!UICONTROL 次／前の項目]パネルに関する新しいトピック | [次／前のディメンション項目パネル](/help/analyze/analysis-workspace/c-panels/next-previous.md) |
| **2022年3月** | |
| サポートされる HTTPS 暗号化アルゴリズムに関する新しいトピック | 暗号セキュリティレベルが「高」に設定されているお客様向けにサポートされている HTTPS 暗号化アルゴリズム。 |
| Analysis Workspace での注釈に関する新しいドキュメント | [Analysis Workspace の注釈](/help/analyze/analysis-workspace/components/annotations/overview.md) を使用すると、コンテキストデータのニュアンスとインサイトを組織に効果的に伝えることができます。 |
| Adobe Analytics ランディングページの更新 | Analysis Workspace と Reports &amp; Analytics の共同ランディングページを [更新](/help/analyze/landing.md) し、操作性とナビゲーションのしやすさを改善しました。 |
| [!UICONTROL 次の項目] または [!UICONTROL 前の項目]ワークスペースパネル | このパネルでは、選択したディメンション項目の後に続く項目、または先行する項目を探索できます。 |
| [!UICONTROL ページの概要]ワークスペースパネル | このパネルでは、選択したページに関する詳細な分析結果を提供します。 |
| 古い予定レポートの一時停止に関する新しいトピック | **2022年4月15日（PT）**&#x200B;より、アドビは、作成日から 2 年以上が経過した予定レポートをすべて一時停止する予定です。 |
| **2022年2月** | |
| モバイルスコアカードプロジェクトのプレビューモード | [プレビューモード](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=ja#preview) では、スコアカードを保存して共有する前に、エクスペリエンスをプレビューできます。 |
| API プロジェクトエンドポイント | API を使用して、Analysis Workspace プロジェクトを追加、編集または削除します。[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) |
| 過去のスケジュール済み Report Builder タスクの一時停止に関する更新されたトピック | **2022年4月15日**&#x200B;より、アドビは、[2 年以上前に作成されたすべてのスケジュール済み Report Builder タスクを一時停止](/help/analyze/legacy-report-builder/r-arb-scheduled-reports.md)する予定です。 |

### 2021年 {#year2021}

| 機能 | 説明 |
| --- | --- |
| **2021年10月** |  |
| 2021年10月21日 | Analysis Workspace の [クイックセグメント](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=ja) に関する新しいドキュメントが公開されました |
| 2021年10月21日 | Analysis Workspace の [メディア再生滞在時間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=ja) パネルに関する新しいドキュメントが公開されました。 |
| 2021年10月7日 | [モバイルスコアカードのビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=ja#apply-visualizations) に関する新しいドキュメント |
| **2021年8月** |  |
| 2021年8月18日 | トップレベルの構造を改訂し、1 つの [ランディングページ](https://experienceleague.adobe.com/docs/analytics.html?lang=ja) に統合しました。 |
| 2021年8月18日 | [A4T と仮想レポートスイート](/help/components/vrs/vrs-a4t.md) に関する新しいトピック |
| 2021年8月18日 | [アトリビューションのベストプラクティス](/help/analyze/analysis-workspace/attribution/best-practices.md) に関する新しいトピック |
| 2021年8月5日 | [繰り返しインスタンスのカウント](https://experienceleague.adobe.com/docs/analytics/components/metrics/count-repeat-instances.html?lang=ja) に関する新しいトピック |
| 2021年8月5日 | 新しい分類アーキテクチャで有効になっているレポートスイートに使用できないオプションを示すために、[テンプレート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-download-saint-data.html?lang=ja)、[ブラウザーインポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=ja) および [ブラウザーエクスポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-export.html?lang=ja) に関する分類ドキュメントを更新しました。 |
| 2021年8月2日 | [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ja) のリブランディングを反映するように複数のページを更新しました |
| **2021年7月** |  |
| 2021年7月23日 | [マーチャンダイジング eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=ja) に関する新しい詳細な説明 |
| 2021年7月15日 | 新しい[Adobe Analytics ランディングページ](/help/analyze/landing.md)に新しいドキュメントを追加しました |
| **2021年6月** |  |
| 2021年6月15日 | [マーケティングチャネルのベストプラクティス](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=ja)を更新しました |
| 2021年6月3日 | [データフィードの実装](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=ja)についての詳細な説明のドキュメントと[こちら](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=ja#BucketOwnerFullControl)を更新しました。 |
| 2021年5月25日 | [レポートで eVar の大文字と小文字の区別](https://experienceleague.adobe.com/docs/analytics/components/dimensions/evar.html?lang=ja)に関するドキュメントを更新しました。 |
| 2021年5月13日 | [Data Warehouse API リクエスト](https://developer.adobe.com/analytics-apis/docs/1.4/guides/reporting/data-warehouse/)を更新しました。「Hours」をサポートするようになりました。 |
| **2021年3月** | |
| 2021年3月、4月 | Adobe Analytics ダッシュボード[エグゼクティブガイド](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/executive.html?lang=ja)および[キュレーターガイド](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html?lang=ja)の更新 |
| 2021年3月25日 | [!UICONTROL コンポーネント]／[!UICONTROL ユーザー環境設定]ページに関する新しいドキュメント。これにより、ユーザーの [!UICONTROL Analysis Workspace] 設定と関連コンポーネントを管理できます。[!UICONTROL ユーザー環境設定]は、すべての新しいプロジェクトおよびパネルに適用されます。<br>**メモ：**&#x200B;次の設定は、[!UICONTROL ユーザー環境設定]ページに移動しました。<ul><li>レポート設定：3 桁ごとの区切り記号（現在は&#x200B;_数値形式_&#x200B;と呼ばれる）</li><li>レポート設定：CSV 区切り記号</li><li>ワークスペースプロジェクト：ヘルプ／ヒントを有効にする</li><li>ワークスペースプロジェクト：空のパネル「_このパネルを使用して新しいプロジェクトを開始_」オプション</li></ul> |
| 2021年3月25日 | [!UICONTROL ヒストグラムスマートバケット予測]は、データ分散に使用するバケットの正しい幅と数を自動的に識別することで、カーディナリティ指標の高いヒストグラムの処理に役立ちます。低カーディナリティ指標の場合、ビジュアライゼーションは以前と同じように動作します。 |
| 2021年3月25日 | [データ修復 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) の更新（URL、クエリ文字列、記号などでのフィルタリング） |
| 2021年3月25日 | 新しい[使用ログ API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/usage-logs.md) ドキュメント |
| **2021年2月** | |
| 2021年2月4日 | コンポーネントの選択：[!UICONTROL クイックインサイト]にあるドロップダウン／ドロップゾーンコンポーネントは、[!UICONTROL ワークスペース]のすべてのドロップゾーンに追加されました。この機能強化により、互換性のあるコンポーネントのドロップダウンリストから選択したり、スペースをドロップゾーンとして引き続き使用したりできます。 |
| **2021年1月** | |
| 2021年1月14日 | Analytics ダッシュボードのドキュメントに言語選択オプションを追加しました。 |
| 2021年1月14日 | 公開画像 URL を参照して、画像を ワークスペースプロジェクトに追加する方法に関するドキュメントを追加しました。 |
| 2021年1月14日 | ワークスペースのビジュアライゼーションのソースマネージャーと設定マネージャーの結合：ビジュアライゼーションの [!UICONTROL データソース] マネージャー（ドット）と設定マネージャー（歯車）が単一のポップオーバーに結合し、一箇所でソースと設定を簡単に管理できます。 |

### 2020年 {#year2020}

| 機能 | 説明 |
| --- | --- |
| **2020年12月** | |
| 2020年12月7日 | 「adobedc.net」エンドポイントを含めるか代用するすべての関連ページを修正しました。 |
| 2020年12月8日 | ワークスペースの[新しいプロジェクトを作成](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=ja)ページを更新しました。 |
| **2020年11月** | |
| 2020年11月24日 | ワークスペースの[パネルの概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)ページを更新しました。 |
| 2020年11月24日 | 新しい実装レビューのドキュメント： <ul><li>[完全な実装レビュー](https://experienceleague.adobe.com/docs/analytics/implementation/review/full-review.html?lang=ja)</li><li>[重点的な実装レビュー](https://experienceleague.adobe.com/ja/docs/analytics/implementation/review/focused-review)</li></ul> |
| 2020年11月24日 | Analysis Workspace の [ビジュアライゼーションの概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja) ページを更新しました。 |
| 2020年11月12日 | [継承された Adobe Analytics の実装](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/existing-implementation.html?lang=ja)の新しいページ。 |
| 2020年11月2日 | [FTP の分類](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html?lang=ja)に関するドキュメントを更新しました。 |
| **2020年10月** | |
| 2020年10月23日 | ワークスペースの線のビジュアライゼーション：[移動平均トレンドラインオプション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html?lang=ja)：この設定は、 [!UICONTROL 折れ線グラフ] のビジュアライゼーションのトレンドライン設定に追加されました。移動平均は、ローリング平均とも呼ばれ、特定数のデータポイント（「**[!UICONTROL 期間]**」セクションで決定される）を使用して、それらを平均し、その平均値を折れ線グラフのポイントとして使用します。 |
| 2020年10月23日 | ワークスペース[パフォーマンスヘルプ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=ja)ページには、プロジェクトのパフォーマンスに影響を与える様々な要因と最適化のためのヒントへのリンクが示されています。 |
| 2020年10月23日 | Adobe Analytics ダッシュボードのドキュメントに機能強化を追加しました。ワークスペースのモバイルスコアカードで、スコアカードのスタイルがアプリと一致するようになりました。 |
| **2020年9月** | |
| 2020年9月17日 | [単一のディメンションに対して 50,000 個の項目をダウンロード](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja#download-items)：セグメントとフィルターが適用されたフリーフォームテーブルで、単一のディメンションに対して 50,000 個の項目をダウンロードできるようになりました。これにより、Analysis Workspace 外の 400 行を超えるデータにアクセスできます。 |
| 2020年9月17日 | [折れ線グラフのビジュアライゼーションの強化](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/line.html?lang=ja): <ul><li>[!UICONTROL 線] の視覚化の X 軸と Y 軸の表示／非表示を切り替えることができます。これは、特に、[!UICONTROL 線]の視覚化がよりコンパクトな場合に役立ちます。</li><li>任意の折れ線グラフのビジュアライゼーションに最小値と最大値のラベルを重ねて、指標の山と谷をすばやく強調表示できます。</li><li>様々な回帰トレンドラインを折れ線グラフのビジュアライゼーションに重ねて、データのトレンドをより簡単に確認できます。「[!UICONTROL 線形]」、「[!UICONTROL 対数]」、「[!UICONTROL 指数]」、「[!UICONTROL 累乗]」、「[!UICONTROL 多項式]」などのオプションがあります。</li></ul> |
| 2020年9月17日 | ワークスペースの新しい日付範囲：5 つの新しい日付範囲を追加しました。これにより、今日の日付の部分データを含まない日付範囲（過去 7 日間、過去 14 日間、過去 30 日間、過去 60 日間、過去 90 日間）から選択できます。 |
| 2020年9月17日 | [ワークスペースのメディア同時ビューアパネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers.html?lang=ja)に関する新しいドキュメント |
| **2020年8月** | |
| 2020年8月31日 | クロスデバイス分析の[フィールドベースのステッチドキュメント](https://experienceleague.adobe.com/docs/analytics/components/cda/field-based-stitching.html?lang=ja)に機能強化を追加しました。 |
| **2020年7月** | |
| 2020年7月21日 | [クロスデバイス分析](/help/components/cda/overview.md)の主なアップデートとリビジョン。[フィー ルドベースのステッチ](/help/components/cda/field-based-stitching.md)を追加しました。 |
| 2020年7月16日 | ワークスペースの新しい日付範囲プリセット。[!UICONTROL 今週／月／四半期／年（今日を除く）]の 4 つの新しい日付範囲を追加しました。これにより、今日の日付の部分データを含まない日付範囲から選択できます。 |
| **2020年6月** | |
| 2020年6月25日 | ワークスペースの[クイックインサイトパネル](/help/analyze/analysis-workspace/c-panels/quickinsight.md)に関する新しいドキュメント。これは、Analysis Workspace のアナリスト以外のユーザーと新規ユーザーに対して、ビジネスの質問に素早く簡単に答える方法を学ぶためのガイダンスを提供します。 |
| 2020年6月25日 | ワークスペースの [Analytics for Target パネル](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)に関する新しいドキュメント。上昇率と信頼性を使用して、Adobe Target のアクティビティとエクスペリエンスを分析できます。 |
| 2020年6月18日 | [Attribution：アルゴリズムアトリビューション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html?lang=ja)に関する新しいドキュメント |
| 2020年6月18日 | [Attribution：カスタムルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=ja#lookback-windows)に関する新しいドキュメント |
| 2020年6月18日 | 共有 ワークスペースプロジェクトの[プロジェクトの役割](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja)に関する新しいドキュメント。ワークスペースプロジェクトを共有する際は、受信者を、使用するプロジェクトエクスペリエンスに応じて、編集、複製、表示の 3 つのプロジェクトの役割のいずれかに受信者を配置できるようになりました。 |
| 2020年6月18日 | [「表示のみ」の ワークスペースプロジェクト](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/view-only-projects.html?lang=ja)に関する新しいドキュメント。プロジェクトは、「表示可能」としてのみユーザーと共有できます。「表示」受信者が共有プロジェクトを開くと、左側のパネルが表示されず、操作が制限された状態となる、より制限が厳格なプロジェクトエクスペリエンスが提供されます。 |
| 2020年6月18日 | 共有 ワークスペースプロジェクトの[プロジェクトの役割](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja)に関する新しいドキュメント。ワークスペースプロジェクトを共有する際は、受信者を、使用するプロジェクトエクスペリエンスに応じて、編集、複製、表示の 3 つのプロジェクトの役割のいずれかに受信者を配置できるようになりました。 |
| 2020年6月18日 | [ワークスペースプロジェクトの共同編集](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja)に関する新しいドキュメント。「編集可能」の役割に追加された受信者は、それらのユーザーと共有されているプロジェクトを上書き保存できます。これは、管理者と非管理者の両方に適用されます。 |
| **2020年5月** |  |
| 2020年5月31日 | [一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) に関する新しいドキュメント |
| 2020年5月21日 | [Adobe Analytics ダッシュボード](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=ja)に関する新しいドキュメント |
| 2020年5月21日 | Analysis Workspace の[アクセシビリティの向上](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/aw-accessibility.html?lang=ja)に関する新しいドキュメント。キーボードナビゲーション、カラーコントラスト、スクリーンリーダーのサポートの向上が含まれます。 |
| **2020年4月** |  |
| 2020年4月28日 | [コンテンツ速度](/help/components/metrics/content-velocity.md)指標に関するドキュメントを追加しました。 |
| 2020年4月16日 | 空白の状態から[!UICONTROL フリーフォームテーブル]を自動的に作成する方法に関するドキュメント。以前は、空のプロジェクトや空のパネルにコンポーネントを直接ドロップすることはできず、最初にフリーフォームテーブルを追加する必要がありました。空のプロジェクトまたはパネルにコンポーネントを直接ドロップできるようになりました。フリーフォームテーブルは推奨される形式で自動的に作成されます。また、空の[!UICONTROL フリーフォームテーブル]にドロップした場合の混合コンポーネントタイプ（ディメンションや指標など）の処理方法も改善されました。 |
| **2020年3月** |  |
| 2020年3月12日 | [Experience Cloud へのセグメントの公開](/help/components/segmentation/segmentation-workflow/seg-publish.md)にアップデートを追加しました。 |
| 2020年3月12日 | CDA のステッチ待機時間のアップデート。 |
| 2020年3月12日 | ワークスペースでの複数のレポートスイートのサポート. 複数のレポートスイートのデータを単一のプロジェクトに取り込み、並べて表示できるようになりました。[詳細情報...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=ja) |
| 2020年3月12日 | ワークスペースのテンプレートトレーニングチュートリアル。この新しい標準テンプレートでは、ワークスペースで最初の分析を作成するための一般的な用語と手順を順に説明します。これは、「新規プロジェクト」モーダルの標準テンプレートとして利用可能であり、リストに他のプロジェクトがない新規ユーザーのために現在用意されているサンプルプロジェクトの代わりになるものです。[詳細情報...](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) |
| **2020年2月** |  |
| 2020年2月27日 | [Adobe Analytics Labs](/help/analyze/labs.md) に関するドキュメントを追加しました。 |
| 2020年2月25日 | [`useLinkTrackSessionStorage`](/help/implement/vars/config-vars/uselinktracksessionstorage.md) 変数を追加しました。 |
| 2020年2月20日 | クロスデバイス間分析を使用する組織向けの新しいワークスペーステンプレート. このテンプレートは、CDA による訪問の関連付けと、CDA 専用のディメンションと指標に関する教育の有効性を示します。CDA を使用するレポートスイートが必要です。詳しくは、 [クロスデバイス分析の設定](/help/components/cda/setup.md) を参照してください。 |
| 2020年2月20日 | ワークスペースの新しいホットキー:<ul><li>すべてのパネルを折りたたむ／展開する：`alt + m`</li><li>アクティブパネルを折りたたみ／展開： `alt + ctrl + m`</li><li>左パネルを検索： `ctrl + /`</li><li>次のパネルに移動： `alt + Right Key`</li><li>前のパネルに移動： `alt + Left Key`</li></ul>[詳細情報...](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=ja) |
| 2020年2月20日 | ワークスペースの機能強化： <ul><li>パネルまたはビジュアライゼーションを ワークスペースにドロップすると、左パネルがコンポーネントへと自動的に切り替わり、よりシームレスなワークフローが実現するようになります。</li><li>テンプレートコンポーネントに対するアクションを実行できるようになりました（例：タグ付け、お気に入りに登録、承認）。</li><li>フィルター適用済みの指標およびセグメントリストには、必要な項目が見つからない場合に新しいコンポーネントを追加するボタンが表示されます。</li></ul> |
| 2020年2月20日 | ワークスペースデバッガーがヘルプメニューに追加され、ワークスペースリクエストのデバッグがよりシームレスに有効化できるようになりました。[詳細情報...](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md) |
| 2020年2月18日 | [`writeSecureCookies`](/help/implement/vars/config-vars/writesecurecookies.md) 変数を追加しました。 |
| 2020年2月12日 | [マーケティングチャネルドキュメント](/help/components/c-marketing-channels/c-getting-started-mchannel.md)のアップデートと再編成。 |
| 2020年2月12日 | [この ワークスペースページ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=ja)に新しいホットキーを追加しました。 |
| 2020年2月7日 | [クロスデバイス分析のセットアップ](/help/components/cda/setup.md)と [FAQ](/help/components/cda/faq.md) のアップデート。 |
| 2020年2月4日 | [実装ユーザーガイド](/help/implement/home.md)を完全に書き直しました。 |
| 2020年1月22日 | フリーフォームテーブルページを更新し、新しい[フリーフォームテーブルビルダー](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)の情報を含めました。 |
| **2020年1月** | |
| 2020年1月24日 | ワークスペースの[行設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=ja#cja-workspace)ページを更新しました。 |
| 2020年1月16日 | [フリーフォームテーブルビルダー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=ja)に関する新しいドキュメント。Table Builder を有効にすれば、多くのディメンション、分類、指標およびセグメントをドラッグ＆ドロップして、より複雑なビジネスの質問に回答するテーブルを作成できます。データはすぐには更新されません。代わりに、「**[!UICONTROL ビルド]**」をクリックした後に更新が行われ、どのテーブルを作成したいかがわかると、時間を節約できます。さらに、この機能では次のことが可能です。<ul><li>**プレビュー**：時間をかけて実際のデータをレンダリングする前に表形式でプレビューできます。</li><li>**柔軟な行と分類の設定**：各ディメンション行に対して行と分類レベルを設定できます。以前は、ワークスペースで適用されたデフォルトは、データが返されるまで変更できませんでした。</li><li>**位置で分類**：ディメンション行を、_特定の項目_&#x200B;ではなく常に&#x200B;_位置で分類_（デフォルト）するように設定できます。</li><li>**手動の静的行の並べ替え**：静的な行を手動で並べ替え、必要に応じて表示できます。以前は、静的な行は指標の列またはアルファベット順でのみ並べ替えることができました。</li></ul> |
| 2020年1月14日 | [Adobe Analytics とブラウザーの cookie](/help/technotes/cookies/cookies.md) を追加しました。 |
| 2020年1月14日 | [使用する Adobe Analytics ツール](/help/analyze/get-started/which-analytics-tool.md)ページを変更しました。 |

### 2019年 {#year2019}

| 機能 | 説明 |
| --- | --- |
| 2020年12月19日 | デフォルトの [FTP データ保存制限](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-limits.html?lang=ja)を 10 GB に変更しました。 |
| 2019年11月29日 | [データフィードのドキュメント](/help/export/analytics-data-feed/data-feed-overview.md)を改定しました。 |
| 2019年11月25日 | IP ログイン制限実施の提供終了に関する新しいトピック. |
| 2019年11月21日 | [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja) の新しいドキュメントセット。 |
| 2019年11月21日 | [Audience Analytics ワークフローの FAQ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=ja) を更新し、LiveStream での可用性を示しました。 |
| 2019年10月25日 | [Adobe Analytics の主要概念](/help/technotes/terms.md)ページを更新しました。 |
| 2019年10月10日（PT） | フリーフォームテーブルの合計の更新：2 つの合計（**[!UICONTROL テーブルの合計]**&#x200B;と&#x200B;**[!UICONTROL 総計]**）が含まれるようになりました。テーブルの合計行は、適用された[レポートフィルター](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.html?lang=ja)を考慮します。以前は、セグメントのみが合計に影響を与えていました。[詳細](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=ja)<br/>さらに、「**[!UICONTROL 列設定]**」に。「**[!UICONTROL 合計行を表示]**」および「**[!UICONTROL 総計を表示]**」オプションが追加されました。<br/>フリーフォーム合計に対するこの変更により、出力された CSV や PDF データだけでなく、依存するビジュアライゼーション（例：リンクされた **[!UICONTROL 概要番号]**&#x200B;ビジュアライゼーションなど）も更新されます。 |
| 2019年10月10日（PT） | ワークスペースでは、「未指定 (なし)」を簡単に削除できる機能がレポートフィルターのオプションとして追加されました。 |
| 2019年10月10日（PT） | ワークスペースでは、紫色の精度コンポーネント（分、時間、日、週、月、四半期、年）は非推奨（廃止予定）となりました。紫色の時間コンポーネントを以前使用したことがある場合、**何も行う必要はありません**。<br/>この変更により、紫色の「**[!UICONTROL 日時]**」セクションの名前が、「**[!UICONTROL 日付範囲]**」に変更されました。 |
| 2019年10月1日 | [ワークスペースの合計](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/workspace-totals.html?lang=ja#cja-workspace)に関する新しい記事。 |
| 2019年9月28日 | [JavaScript 実装の設定変数](/help/implement/vars/config-vars/configuration-variables.md)に関する新しい記事を追加しました。 |
| 2019年9月19日 | [論理グループコンテナ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html?lang=ja#logic-group-containers)について説明するようにセグメント化に関するドキュメントを改訂しました。 |
| 2019年9月12日 | [クロスデバイス分析](/help/components/cda/overview.md)に関する新しいドキュメント |
| 2019年9月12日 | [計算指標の合計](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html?lang=ja)ドキュメントの更新。 |
| 2019年8月28日 | [Analytics 向けプログレッシブ Web アプリ（PWA）](/help/technotes/pwa.md)に関する新しい記事を追加しました。 |
| 2019年8月8日 | [計算指標の合計](/help/components/c-calcmetrics/cm-totals.md)に関する新しい記事を追加しました。 |
| 2019年8月8日 | [タイムスタンプが有効なセッションデータ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)について明確化しました。 |
| 2019年8月8日 | Workspace では、静的ドロップダウンフィルターに配置できる項目の最大数を 50 から 200 に増加しました。この強化は、すべての国（195）やすべての都道府県（52）をフィルターに追加するなどの状況への対応を可能にします。 |
| 2019年8月2日 | [Analytics 用語集](/help/technotes/terms.md)を大幅に更新しました。 |
| 2019年7月22日 | [Analysis Workspace テンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)ドキュメントに Magento：マーケティングとコマーステンプレートが追加されました。 |
| 2019年7月18日 | [コホートテーブル設定](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)が更新されました。 |
| 2019年7月18日 | ワークスペースの左側のパネルに、_過去 18 か月の項目を表示_&#x200B;するためのオプションが追加されました。以前は、ルックバック期間は最大 6 か月でした。これにより、昨年のページやキャンペーンとの比較が簡単になります（最大 18 か月前）。 |
| 2019年7月18日 | Analysis Workspace に追加された、[Magento：マーケティングとコマース](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja)という新しいワークスペーステンプレートに関するドキュメント。Magento e コマースのお客様向けに特別に設計されたものですが、小売業者のお客様は独自のインサイトを業務に役立てることができます。 |
| 2019年6月13日 | ワークスペースの左側のパネルの検索に、新しい事前設定済みのフィルターを追加しました。現在表示できるもの（ディメンション、指標、承認済みなど）以外に、計算指標、顧客属性、eVar、Prop、ビデオなどの新しいフィルターが追加され、必要なコンポーネントを探すのがより簡単になります。 |
| 2019年6月4日 | 新しいガイド[サードパーティの分析プラットフォームから Adobe Analytics への移行](/help/technotes/ga-to-aa/home.md)が作成されました。 |
| 2019年5月31日 | [データフィード列リファレンス](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)が改定されました。 |
| 2019年5月9日 | フロービジュアライゼーション設定に新しい設定を追加しました：繰り返しインスタンスを含める。[フロー設定](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)を参照 |
| 2019年4月11日 | ワークスペースの最適化のベストプラクティスに関する機能強化：パフォーマンスの最適化 |
| 2019年4月11日 | [ワークスペースのパフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)が更新されました。 |
| 2019年3月14日 | 地域データ収集が大幅に更新されました。 |
| 2019年2月7日 | [一般アカウント設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)の「IP アドレスの最後のオクテットを 0 に置き換える」と「IP アドレスの難読化」設定が若干更新されました。 |
| 2019年2月1日 | [getPercentPageViewed](../implement/vars/plugins/getpercentpageviewed.md) 実装プラグインが大幅に更新されました。 |
| 2019年1月17日 | [コホート分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) - コホート分析が大きく改善され、以下の機能が実現しました。<ul><li>セグメントのインクルージョン指標とリターン指標を別々に適用できます。 </li><li>リテンションの代わりにチャーン（離反）を表示できます。</li><li>待ち時間テーブル（インクルージョンイベントの前後の変化）を表示できます。</li><li>コホートディメンションをカスタマイズできます（時間だけでなく eVar の値で訪問者をグループ化できます）。</li><li>ローリングコホート計算を実行する：元のコホートではなく直前の期間からのリテンション／チャーンを計算します。 </li><li>セグメントの適用に加え、インクルージョンフィールドとリターンフィールドに複数の指標を追加できます。（計算指標はサポートされません）。</li></ul> |
| 2019年1月17日 | [表示密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md). この新しい設定を使用すると、左側のパネル、フリーフォームテーブルおよびコホートテーブルでの垂直方向のパディングを減らし、1 画面に表示されるデータの量を増やすことができます。プロジェクト／プロジェクト情報および設定から利用できます。 |
| 2019年1月17日 | [Attribution での複数値の変数のサポート](/help/analyze/analysis-workspace/attribution/overview.md)。Analytics の一部のディメンションでは、1 回のヒットに複数の値（listVar、product 変数、リスト prop、マーチャンダイジング eVar など）を含めることができます。Analysis Workspace では、このような変数にヒットレベルで Attribution を適用できるようになりました。 |
