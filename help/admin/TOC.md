---
product: analytics
audience: admin
user-guide-title: Analytics 管理ガイド
breadcrumb-title: 管理ガイド
user-guide-description: Experience Cloud Admin Console でのユーザーと製品の管理、レポートスイートの設定など、Analytics の管理タスクについて説明します。
source-git-commit: 927e7e374919d89798c69c1959c54426b4e51a3e
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 98%

---


# Adobe Analytics 管理ガイド {#admin}

+ [Analytics 管理ガイド](home.md)
+ [Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
+ Analytics 管理者の概要 {#admin-overview}
   + [使用する Adobe Analytics ツールの検討](c-analytics-product-comparison/which-analytics-tool.md)
   + [Analytics 製品の比較と必要システム構成](c-analytics-product-comparison/analytics-product-comparison.md)
+ [必要システム構成](sys-reqs.md)
+ 管理ツール {#admin-tools}
   + [管理ツール](admin/c-admin-tools.md)
   + [課金](admin/billing-admin.md)
   + ボットの削除 {#bot-removal}
      + [ボットの削除](admin/bot-removal/bot-removal.md)
      + [ボットルールの概要](admin/bot-removal/bot-rules.md)
      + [一般的なボット署名](admin/bot-removal/bot-signatures.md)
      + [ボットの除外メソッド](admin/bot-removal/bot-exclusion-methods.md)
   + [コードマネージャー](admin/code-manager-admin.md)
   + コンバージョン変数 {#conversion-variables}
      + [コンバージョン変数（eVar）](admin/conversion-var-admin/conversion-var-admin.md)
      + [コンバージョン変数の編集](admin/conversion-var-admin/t-conversion-variables-admin.md)
      + [コンバージョンの分類](admin/conversion-var-admin/conversion-classifications.md)
      + [分類階層](admin/conversion-var-admin/classification-hierarchies.md)
      + [リスト変数](admin/conversion-var-admin/list-var-admin.md)
      + [マーチャンダイジング eVar](admin/conversion-var-admin/merchandising-evars.md)
   + [通貨コード](admin/currency.md)
   + [カスタムレポートの説明](admin/custom-desc-admin.md)
   + [カレンダーのカスタマイズ](admin/custom-calendar.md)
   + [データソース](admin/data-sources.md)
   + [デフォルトの指標](admin/default-metrics.md)
   + [IP アドレスで除外](admin/exclude-ip.md)
   + [検索方法](admin/finding-methods.md)
   + [一般的なアカウント設定](admin/general-acct-settings-admin.md)
   + [内部 URL フィルター](admin/internal-url-filter-admin.md)
   + [ログ](admin/logs.md)
   + [マーケティングチャネル](admin/marketing-channels-admin.md)
   + [メニューのカスタマイズ](admin/customize-menus.md)
   + [指標の表示](admin/metric-visibility.md)
   + [アプリ管理](admin/mobile-management.md)
   + 有料検索検知 {#paid-search-detection}
      + [有料検索検知の概要](admin/paid-search-detection/paid-search-detection.md)
      + [有料検索検知の設定](admin/paid-search-detection/t-paid-search-detection.md)
   + [発行リスト](admin/publishing-list.md)
   + [公開ウィジェット](admin/publishing-widgets-admin.md)
   + [設定マネージャー](admin/preferences-manager.md)
   + [プライバシー設定](admin/privacy-settings.md)
   + [プライバシーレポート](admin/privacy-reporting.md)
   + 処理ルール {#processing-rules}
      + [処理ルールの概要](admin/c-processing-rules/processing-rules.md)
      + 処理ルールの設定 {#processing-rules-configuration}
         + [処理ルールの仕組み](admin/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
         + [処理ルールの作成](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
         + [アクティブな処理ルールの表示](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
         + [処理ルール履歴の表示](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
         + [処理ルールの復元](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
         + [他のレポートスイートへの処理ルールのコピー](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
      + [処理ルールで使用可能なディメンション](admin/c-processing-rules/processing-rule-dimensions.md)
      + 処理ルールの例 {#processing-rules-examples}
         + [処理ルールの例](admin/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
         + [クエリ文字列パラメーターからのキャンペーン ID の入力](admin/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
         + [製品の概要ページからの「製品表示」イベントの設定](admin/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
         + [カテゴリとページ名の連結によるサブカテゴリの追加](admin/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
         + [eVar 値を prop にコピーしてパスを指定](admin/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
         + [レポート内の値のクリーンアップ](admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
         + [クエリ文字列パラメーターを使用して内部検索用語を入力](admin/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
         + [コンテキストデータ変数の eVar へのコピー](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
         + [コンテキストデータ変数を使用したイベントの設定](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
         + [ヒットからのイベントの削除](admin/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
      + [処理ルールのヒントとテクニック](admin/c-processing-rules/processing-rules-tips.md)
   + リアルタイムレポート {#real-time-reports}
      + [リアルタイムレポートの概要](admin/realtime/realtime.md)
      + [リアルタイムレポートの設定](admin/realtime/t-realtime-admin.md)
      + [サポートされるリアルタイム指標とディメンション](admin/realtime/realtime-metrics.md)
   + [レポートアクティビティマネージャー](admin/reporting-activity.md)
   + [予定レポートキュー](admin/scheduled-reports-admin.md)
   + サーバー側転送 {#server-side-forwarding}
      + [サーバー側転送の概要](admin/c-server-side-forwarding/ssf.md)
      + [GDPR／ePrivacy コンプライアンスおよびサーバー側転送](admin/c-server-side-forwarding/ssf-gdpr.md)
      + [サーバー側転送の要件](admin/c-server-side-forwarding/ssf-requirements.md)
      + [サーバー側転送のデータとコードのリファレンス](admin/c-server-side-forwarding/ssf-reference.md)
      + [サーバー側転送の実装の確認方法](admin/c-server-side-forwarding/ssf-verify.md)
      + [サーバー側転送の FAQ](admin/c-server-side-forwarding/ssf-faq.md)
   + [シンプル化されたレポートメニュー](admin/t-simplified-menu.md)
   + [ソーシャルの管理](admin/social-management.md)
   + 成功イベント {#success-events}
      + [成功イベントの概要](admin/c-success-events/success-event.md)
      + [成功イベントの設定](admin/c-success-events/t-success-events.md)
      + [イベントタイプの変更について](admin/c-success-events/event-type.md)
   + [タイムスタンプオプション](admin/timestamp-optional.md)
   + トラフィック変数 {#traffic-variables}
      + [トラフィック変数（prop）の概要](admin/c-traffic-variables/traffic-var.md)
      + [トラフィック変数レポートの有効化](admin/c-traffic-variables/t-traffic-variable.md)
      + [トラフィック分類](admin/c-traffic-variables/traffic-classifications.md)
   + ユニーク訪問者変数 {#unique-visitor-variable}
      + [ユニーク訪問者変数の指定](admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
      + [使用事例 - 訪問者 ID の抽出](admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
   + [ビデオ管理](admin/video-management.md)
+ Admin Console での Adobe Analytics {#admin-console}
   + [Admin Console での Adobe Analytics](admin-console/home.md)
   + 権限 {#permissions}
      + [Admin Console での Analytics 権限](admin-console/permissions/summary-tables.md)
      + [Adobe Analytics の製品プロファイル](admin-console/permissions/product-profile.md)
      + [レポートスイートツールの製品プロファイル権限](admin-console/permissions/report-suite-tools.md)
      + [Analytics ツールの製品プロファイル権限](admin-console/permissions/analytics-tools.md)
   + [Adobe Analytics first admin guide](admin-console/first-admin-guide.md)
   + [Adobe Analyticsの管理者の役割](admin-console/admin-roles-in-analytics.md)
+ カンパニー設定 {#company-settings}
   + [カンパニー設定の概要](company/c-company-settings.md)
   + [機能アクセスレベル](company/feature-access-levels.md)
   + [Web サービス](company/web-services-admin.md)
   + [Report Builder レポート](company/report-builder-reports-admin.md)
   + [シングルサインオン](company/single-signon-admin.md)
   + [保留中のアクション](company/pending-actions-admin.md)
   + [ブランド提携](company/co-branding-admin.md)
   + [レポートスイートを非表示](company/c-hide-report-suites.md)
   + [セキュリティマネージャー](company/security-manager.md)
+ レポートスイートの管理 {#manage-report-suites}
   + [レポートスイートマネージャー](c-manage-report-suites/report-suites-admin.md)
   + [ロールアップレポートスイートとグローバルレポートスイート](c-manage-report-suites/rollup-report-suite.md)
   + [ロールアップレポートスイートの作成](c-manage-report-suites/t-rollups.md)
   + レポートスイートテンプレート {#report-suite-templates}
      + [レポートスイートテンプレートの概要](c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [集積ポータル](c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [コマース](c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
      + [コンテンツとメディア](c-manage-report-suites/c-report-suite-templates/content-media.md)
      + [デフォルトテンプレート](c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
      + [金融サービス](c-manage-report-suites/c-report-suite-templates/financial-services.md)
      + [ジョブポータル](c-manage-report-suites/c-report-suite-templates/job-portal.md)
      + [リードジェネレーション](c-manage-report-suites/c-report-suite-templates/lead-generation.md)
      + [サポートメディア](c-manage-report-suites/c-report-suite-templates/support-media.md)
   + [レポートスイートの検索の保存](c-manage-report-suites/t-report-suite-saved-search.md)
   + [個々のレポートスイートの設定](c-manage-report-suites/individual-rs-settings.md)
   + [レポートスイートの設定のダウンロード](c-manage-report-suites/t-download-rs-settings.md)
   + 新しいレポートスイート {#new-report-suite}
      + [レポートスイートの作成](c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
      + [新しいレポートスイート - 設定](c-manage-report-suites/c-new-report-suite/new-report-suite.md)
      + [ソースレポートスイートからコピーされない設定](c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
   + [レポートスイートグループの作成](c-manage-report-suites/t-create-rs-group.md)
+ ユーザーと製品の管理（レガシー） {#user-product-management}
   + [ユーザーと製品の管理](user-management2/user-management.md)
   + Adobe Admin Console へのユーザーの移行 {#migrate-users}
      + [Admin Console への Analytics ユーザーの移行](user-management2/user-migration/c-migration-tool.md)
      + [Adobe ID 用に Analytics ユーザーアカウントを移行する ](user-management2/user-migration/t-migrate-users.md)
      + [Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行 ](user-management2/user-migration/migrate-enterprise.md)
      + [従来のログインの無効化](user-management2/user-migration/t-disable-legacy-login.md)
      + [移行の影響を受ける API](user-management2/user-migration/developer.md)
+ データガバナンス {#data-governance}
   + [Adobe Analytics と GDPR](c-data-governance/an-gdpr-overview.md)
   + [Adobe Analytics と CCPA](c-data-governance/an-ccpa-overview.md)
   + [CNIL 同意除外](c-data-governance/cnil-consent-exemption.md)
   + [よくある質問](c-data-governance/gdpr-faq.md)
   + [Adobe Analytics データプライバシーワークフロー](c-data-governance/an-gdpr-workflow.md)
   + [レポートスイートのデータガバナンス設定の表示／管理](c-data-governance/gdpr-view-settings.md)
   + [レポートスイートのデータのラベル設定](c-data-governance/gdpr-setup-reportsuite.md)
   + [アクセス要求および削除要求の送信](c-data-governance/gdpr-submit-access-delete.md)
   + [Analytics 変数のデータプライバシーラベル](c-data-governance/gdpr-labels.md)
   + [名前空間](c-data-governance/gdpr-namespaces.md)
   + [ID 拡張](c-data-governance/gdpr-id-expansion.md)
   + [ラベル設定に関するベストプラクティス](c-data-governance/gdpr-analytics-ids.md)
   + [ラベル設定の例](c-data-governance/gdpr-labeling-example.md)
   + [データプライバシーと Data Connectors（Genesis）](c-data-governance/data-connectors-gdpr.md)
   + [データプライバシーの用語](c-data-governance/gdpr-terminology.md)
+ サーバーコールの使用状況 {#server-call-usage}
   + [サーバーコールの使用状況の概要](c-server-call-usage/overage-overview.md)
   + [現在のサーバーコールの使用状況の表示](c-server-call-usage/server-call-usage-dashboard.md)
   + [レポートスイートの使用状況の表示](c-server-call-usage/report-suite-usage.md)
   + [サーバーコールの使用状況アラート](c-server-call-usage/scu-alerts.md)
   + [サーバーコールの使用状況の FAQ](c-server-call-usage/overage-faq.md)
+ トラフィック管理 {#traffic-management}
   + [トラフィックの管理](c-traffic-management/traffic-management.md)
   + [トラフィックスパイクのスケジュール](c-traffic-management/t-traffic-schedule-spike.md)
   + [過去のサーバーコールの推定とトラフィックスパイクのスケジュール](c-traffic-management/traffic-spike-estimate-past-server-calls.md)
   + [恒常的なトラフィック増加の指定](c-traffic-management/t-traffic-permanent.md)
   + [トラフィック増加に対して必要なリードタイム](c-traffic-management/traffic-lead-time.md)
+ [管理 API](c-admin-api/c-admin-api.md)
