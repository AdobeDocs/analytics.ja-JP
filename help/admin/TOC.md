---
product: analytics
audience: admin
user-guide-title: Analytics 管理ガイド
breadcrumb-title: 管理ガイド
user-guide-description: Experience Cloud Admin Console でのユーザーと製品の管理、レポートスイートの設定など、Analytics の管理タスクについて説明します。
source-git-commit: 512c348bda14654daa155f774dd384cba4aed2bd
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 96%

---


# Adobe Analytics 管理ガイド {#admin}

+ [Analytics 管理ガイド](home.md)
+ [Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
+ Adobe Admin Console {#admin-console}
   + [概要](admin-console/home.md)
   + [Adobe Analytics はじめての管理ガイド](admin-console/first-admin-guide.md)
   + [Adobe Analytics の管理者の役割](admin-console/admin-roles-in-analytics.md)
   + Analytics ツール権限の概要 {#permissions}
      + [Adobe Analytics の製品プロファイル](admin-console/permissions/product-profile.md)
      + [レポートスイートツールの製品プロファイル権限](admin-console/permissions/report-suite-tools.md)
      + [Analytics ツールの製品プロファイル権限](admin-console/permissions/analytics-tools.md)
+ Analytics 管理ツール {#admin-tools}
   + [管理ツールの概要](admin/c-admin-tools.md)
   + [コードマネージャー](admin/code-manager-admin.md)
   + [データソース](admin/data-sources.md)
   + [IP アドレスで除外](admin/exclude-ip.md)
   + [ログ](admin/logs.md)
   + [レポートアクティビティマネージャー](admin/reporting-activity.md)
   + [コンポーネントの移行](admin/component-migration.md)
   + レポートスイートマネージャー {#manage-report-suites}
      + レポートスイートの設定の編集 {#edit-report-suite}
         + 一般 {#report-suite-general}
            + [一般的なアカウント設定](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [内部 URL フィルター](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [カレンダーのカスタマイズ](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + 有料検索検知 {#paid-search-detection}
               + [有料検索検知の概要](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [有料検索検知の設定](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [メニューのカスタマイズ](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + 処理ルール {#c-processing-rules}
               + [処理ルールの概要](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + 処理ルール {#c-processing-rules-configuration}
                  + [処理ルールの仕組み](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [処理ルールの作成](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [アクティブな処理ルールの表示](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [処理ルール履歴の表示](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [処理ルールの復元](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [他のレポートスイートへの処理ルールのコピー](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [処理ルールで使用可能なディメンション](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + 処理ルールの例 {#processing-rules-examples}
                  + [処理ルールの例](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [クエリ文字列パラメーターからのキャンペーン ID の入力](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [製品の概要ページからの「製品表示」イベントの設定](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [カテゴリとページ名の連結によるサブカテゴリの追加](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [eVar 値を prop にコピーしてパスを指定](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [レポート内の値のクリーンアップ](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [クエリ文字列パラメーターを使用して内部検索用語を入力](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [コンテキストデータ変数の eVar へのコピー](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [コンテキストデータ変数を使用したイベントの設定](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [ヒットからのイベントの削除](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [処理ルールのヒントとテクニック](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + ボットルール {#bot-removal}
               + [ボットの削除](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [ボットルールの概要](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [一般的なボット署名](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [ボットの除外メソッド](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [プライバシー設定](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [タイムスタンプ設定](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + サーバー側転送 {#server-side-forwarding}
               + [サーバーサイド転送の概要](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [GDPR／ePrivacy コンプライアンスおよびサーバーサイド転送](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [サーバーサイド転送の要件](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [サーバーサイド転送のデータとコードのリファレンス](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [サーバーサイド転送の実装の確認方法](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [サーバーサイド転送の FAQ](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + トラフィック {#traffic-variables}
            + [トラフィック変数](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [トラフィック分類](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [カスタムレポートの説明](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + コンバージョン {#conversion-variables}
            + [コンバージョン変数](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [検索方法](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [コンバージョンの分類](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + ユニーク訪問者変数 {#unique-visitor-variable}
               + [ユニーク訪問者変数の指定](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [使用事例 - 訪問者 ID の抽出](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + 成功イベント {#success-events}
               + [成功イベントの概要](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [成功イベントの設定](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [イベントタイプの変更について](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [分類階層](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [リスト変数](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [マーチャンダイジング eVar](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + マーケティングチャネル {#marketing-channels}
            + [マーケティングチャネルマネージャー](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [マーケティングチャネルの処理ルール](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [マーケティングチャネルの分類](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [マーケティングチャネルの有効期限](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + トラフィック管理 {#traffic-management}
            + [概要](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [スパイクのスケジュール](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [恒常的なトラフィック](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [デフォルトの指標](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + [アプリ管理](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + [メディア管理](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [プライバシーレポート](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Document Cloud管理 {#doc-cloud-mgt}
            + [Adobe AnalyticsとのDocument Cloudの設定](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Document Cloudレポートの設定](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Advertising Analytics 設定](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + リアルタイム {#real-time-reports}
            + [リアルタイムレポートの概要](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [リアルタイムレポートの設定](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [サポートされるリアルタイム指標とディメンション](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [レポートスイートの管理](admin/c-manage-report-suites/report-suites-admin.md)
      + [ロールアップレポートスイートとグローバルレポートスイート](admin/c-manage-report-suites/rollup-report-suite.md)
      + [レポートスイートの検索の保存](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [レポートスイートの設定のダウンロード](admin/c-manage-report-suites/t-download-rs-settings.md)
      + 新しいレポートスイート {#c-new-report-suite}
         + [レポートスイートの作成](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [ロールアップレポートスイートの作成](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
         + [レポートスイートグループの作成](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [新しいレポートスイート - 設定](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [ソースレポートスイートからコピーされない設定](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + レポートスイートテンプレート {#report-suite-templates}
         + [レポートスイートテンプレートの概要](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [集積ポータル](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [コマース](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [コンテンツとメディア](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [デフォルトテンプレート](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [金融サービス](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [ジョブポータル](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [リードジェネレーション](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [サポートメディア](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + カンパニー設定 {#company-settings}
      + [カンパニー設定の概要](admin/company/c-company-settings.md)
      + [セキュリティマネージャー](admin/company/security-manager.md)
      + [Web サービス](admin/company/web-services-admin.md)
      + [Report Builder レポート](admin/company/report-builder-reports-admin.md)
      + [シングルサインオン](admin/company/single-signon-admin.md)
      + [ブランド提携](admin/company/co-branding-admin.md)
      + [レポートスイートを非表示](admin/company/c-hide-report-suites.md)
      + [設定マネージャー](admin/company/preferences-manager.md)
      + [保留中のアクション](admin/company/pending-actions-admin.md)
      + [機能アクセスレベル](admin/company/feature-access-levels.md)
   + データガバナンスプライバシーのラベル付け {#data-governance}
      + [Adobe Analytics データプライバシーワークフロー](admin/c-data-governance/an-gdpr-workflow.md)
      + [よくある質問](admin/c-data-governance/gdpr-faq.md)
      + データのラベル付け {#data-labels}
         + [Analytics コンポーネントのデータプライバシーラベル](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [レポートスイートのデータのラベル設定](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [レポートスイートのプライバシーラベルの表示／管理](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [ラベル設定に関するベストプラクティス](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [ラベル設定の例](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [名前空間](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [ID 拡張](admin/c-data-governance/gdpr-id-expansion.md)
      + [CNIL 同意除外](admin/c-data-governance/cnil-consent-exemption.md)
   + サーバーコールの使用状況 {#server-call-usage}
      + [サーバーコールの使用状況の概要](admin/c-server-call-usage/overage-overview.md)
      + [現在のサーバーコールの使用状況の表示](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [レポートスイートの使用状況の表示](admin/c-server-call-usage/report-suite-usage.md)
      + [サーバーコールの使用状況アラート](admin/c-server-call-usage/scu-alerts.md)
      + [サーバーコールの使用状況の FAQ](admin/c-server-call-usage/overage-faq.md)
   + ユーザーと製品の管理（レガシー） {#user-product-management}
      + [ユーザーと製品の管理(レガシー)](admin/user-management2/user-management.md)
      + [ユーザーアセットの転送と、アカウントの有効期限の設定](admin/user-management2/users-assets.md)
      + Adobe Admin Console へのユーザーの移行 {#migrate-users}
         + [Admin Console への Analytics ユーザーの移行](admin/user-management2/user-migration/c-migration-tool.md)
         + [Adobe ID 用に Analytics ユーザーアカウントを移行する ](admin/user-management2/user-migration/t-migrate-users.md)
         + [Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行 ](admin/user-management2/user-migration/migrate-enterprise.md)
         + [従来のログインの無効化](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [移行の影響を受ける API](admin/user-management2/user-migration/developer.md)
+ [Admin API](c-admin-api/c-admin-api.md)

