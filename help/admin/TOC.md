---
product: analytics
audience: admin
user-guide-title: Analytics 管理ガイド
breadcrumb-title: 管理ガイド
user-guide-description: Experience Cloud Admin Console でのユーザーと製品の管理、レポートスイートの設定など、Analytics の管理タスクについて説明します。
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---


# Adobe Analytics 管理ガイド {#admin}

+ [Analytics 管理ガイド](home.md)
+ [Analytics リリースノート](https://experienceleague.adobe.com/ja/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [概要](admin-console/home.md)
   + [Adobe Analytics はじめての管理ガイド](admin-console/first-admin-guide.md)
   + [Adobe Analytics の管理者の役割](admin-console/admin-roles-in-analytics.md)
   + Analytics ツール権限の概要 {#permissions}
      + [Adobe Analytics の製品プロファイル](admin-console/permissions/product-profile.md)
      + [レポートスイートツールの製品プロファイル権限](admin-console/permissions/report-suite-tools.md)
      + [Analytics ツールの製品プロファイル権限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理ツール {#admin-tools}
   + [管理ツールの概要](tools/c-admin-tools.md)
   + [コードマネージャー](tools/code-manager-admin.md)
   + [Analytics インベントリ](tools/analytics-inventory.md)
   + [データソース](tools/data-sources.md)
   + [IP アドレスで除外](tools/exclude-ip.md)
   + [ログ](tools/logs.md)
   + レポートアクティビティマネージャー {#reporting-activity-manager}
      + [概要](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [レポートアクティビティの表示](tools//reporting-activity-manager/reporting-activity.md)
      + [レポートリクエストのキャンセル](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + コンポーネントの移行 {#component-migration}
      + [移行の準備](tools/component-migration/prepare-component-migration.md)
      + [移行ワークフロー](tools/component-migration/component-migration.md)
   + レポートスイートマネージャー {#manage-report-suites}
      + レポートスイートの設定の編集 {#edit-report-suite}
         + 一般 {#report-suite-general}
            + [一般的なアカウント設定](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [内部 URL フィルター](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [カレンダーのカスタマイズ](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + 有料検索検知 {#paid-search-detection}
               + [有料検索検知の概要](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [有料検索検知の設定](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + 処理ルール {#processing-rules}
               + [概要](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [インターフェイス](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [履歴を表示](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [ルールのコピー](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [使用可能なディメンションと指標](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [ユースケース](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + ボットルール {#bot-removal}
               + [ボットの削除](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [ボットルールの理解と設定](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [一般的なボット署名](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [ボットの除外メソッド](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [プライバシー設定](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [タイムスタンプ設定](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + サーバーサイド転送 {#server-side-forwarding}
               + [サーバーサイド転送の概要](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [GDPR／ePrivacy コンプライアンスおよびサーバーサイド転送](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [サーバーサイド転送の要件](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [サーバーサイド転送のデータとコードのリファレンス](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [サーバーサイド転送の実装の確認方法](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [サーバーサイド転送の FAQ](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + トラフィック {#traffic-variables}
            + [トラフィック変数](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [トラフィック分類](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [カスタムレポートの説明](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + コンバージョン {#conversion-variables}
            + [コンバージョン変数](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [検索方法](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [コンバージョンの分類](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + ユニーク訪問者変数 {#unique-visitor-variable}
               + [ユニーク訪問者変数の指定](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [使用事例 - 訪問者 ID の抽出](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [成功イベント](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [分類階層](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [リスト変数](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [マーチャンダイジング eVar](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + マーケティングチャネル {#marketing-channels}
            + [マーケティングチャネルマネージャー](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [マーケティングチャネルの処理ルール](tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)
            + [マーケティングチャネルの分類](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [マーケティングチャネルの有効期限](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + トラフィック管理 {#traffic-management}
            + [概要](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [スパイクのスケジュール](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [恒常的なトラフィック](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [デフォルトの指標](tools/manage-rs/edit-settings/default-metrics.md)
         + アプリ管理 {#app-management}
            + [アプリレポート](tools/manage-rs/edit-settings/app-reporting.md)
            + [アプリの分類](tools/manage-rs/edit-settings/app-classifications.md)
         + [メディア管理](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [プライバシーレポート](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Document Cloud 管理 {#doc-cloud-mgt}
            + [Adobe Analytics での Document Cloud の設定](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Document Cloud レポートの設定](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Advertising Analytics 設定](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + リアルタイム {#real-time-reports}
            + [リアルタイムレポートの概要](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [リアルタイムレポートの設定](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [サポートされるリアルタイム指標とディメンション](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [レポートスイートの管理](tools/manage-rs/report-suites-admin.md)
      + [グローバルレポートスイート](tools/manage-rs/rollup-report-suite.md)
      + [レポートスイートの検索の保存](tools/manage-rs/t-report-suite-saved-search.md)
      + [レポートスイートの設定のダウンロード](tools/manage-rs/t-download-rs-settings.md)
      + 新しいレポートスイート {#c-new-report-suite}
         + [レポートスイートの作成](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [レポートスイートグループの作成](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [新しいレポートスイート - 設定](tools/manage-rs/new-rs/new-report-suite.md)
         + [ソースレポートスイートからコピーされない設定](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + レポートスイートテンプレート {#report-suite-templates}
         + [レポートスイートテンプレートの概要](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [集積ポータル](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [コマース](tools/manage-rs/rs-templates/commerce-admin.md)
         + [コンテンツとメディア](tools/manage-rs/rs-templates/content-media.md)
         + [デフォルトテンプレート](tools/manage-rs/rs-templates/default-rs-template.md)
         + [金融サービス](tools/manage-rs/rs-templates/financial-services.md)
         + [ジョブポータル](tools/manage-rs/rs-templates/job-portal.md)
         + [リードジェネレーション](tools/manage-rs/rs-templates/lead-generation.md)
         + [サポートメディア](tools/manage-rs/rs-templates/support-media.md)
   + カンパニー設定 {#company-settings}
      + [カンパニー設定の概要](tools/company/c-company-settings.md)
      + [セキュリティマネージャー](tools/company/security-manager.md)
      + [Web サービス](tools/company/web-services-admin.md)
      + [Report Builder レポート](tools/company/report-builder-reports-admin.md)
      + [シングルサインオン](tools/company/single-signon-admin.md)
      + [レポートスイートを非表示](tools/company/c-hide-report-suites.md)
      + [設定マネージャー](tools/company/preferences-manager.md)
      + [保留中のアクション](tools/company/pending-actions-admin.md)
      + [機能アクセスレベル](tools/company/feature-access-levels.md)
   + プライバシーラベリング {#privacy-labeling}
      + [概要](tools/privacy-labeling/labeling-overview.md)
      + [Analytics コンポーネントのデータプライバシーラベル](tools/privacy-labeling/labels.md)
      + [レポートスイートのプライバシーラベルの表示／管理](tools/privacy-labeling/view-settings.md)
      + [ラベル設定に関するベストプラクティス](tools/privacy-labeling/best-practices.md)
      + [ラベル設定の例](tools/privacy-labeling/examples.md)
      + [名前空間](tools/privacy-labeling/namespaces.md)
   + サーバーコールの使用状況 {#server-call-usage}
      + [サーバーコールの使用状況の概要](tools/server-call-usage/overage-overview.md)
      + [現在のサーバーコールの使用状況の表示](tools/server-call-usage/server-call-usage-dashboard.md)
      + [レポートスイートの使用状況の表示](tools/server-call-usage/report-suite-usage.md)
      + [サーバーコールの使用状況アラート](tools/server-call-usage/scu-alerts.md)
      + [サーバーコールの使用状況の FAQ](tools/server-call-usage/overage-faq.md)
   + ユーザーと製品の管理（レガシー） {#user-product-management}
      + [ユーザーと製品の管理（レガシー）](tools/user-management/user-management.md)
      + [従来のユーザーアカウント、アセットおよび有効期限の管理](tools/user-management/users-assets.md)
      + Adobe Admin Console へのユーザーの移行 {#migrate-users}
         + [Admin Console への Analytics ユーザーの移行](tools/user-management/user-migration/c-migration-tool.md)
         + [Adobe ID 用に Analytics ユーザーアカウントを移行する ](tools/user-management/user-migration/t-migrate-users.md)
         + [Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行 ](tools/user-management/user-migration/migrate-enterprise.md)
         + [従来のログインの無効化](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [移行の影響を受ける API](tools/user-management/user-migration/developer.md)
+ [管理 API](https://developer.adobe.com/analytics-apis/docs/2.0/)
