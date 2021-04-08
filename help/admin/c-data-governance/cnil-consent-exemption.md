---
description: デバイスやブラウザーでの不必要な Cookie の保存や読み取りに対するユーザーの同意についてのガイドラインと推奨事項について説明します。
title: ユーザーの同意と Cookie に関する CNIL ガイドライン
translation-type: ht
source-git-commit: fefc2433ef42bae232a9a9afc1040be8d04b2bbe
workflow-type: ht
source-wordcount: '637'
ht-degree: 100%

---


# CNIL 同意除外

2020 年 10 月 1 日（PT）、フランスのデータ保護局（以下「CNIL」）は、ユーザーのデバイスやブラウザーで不必要な Cookie や類似のテクノロジーを保存または読み取ることに対するユーザーの同意の取得に関する Cookie ガイドラインの改訂版（以下「ガイドライン」）と推奨事項の最終版（以下「推奨事項」）を公開しました。

ガイドラインでは、同意要件に対する制限付きの適用除外（以下「同意除外」）を規定しています。 同意除外は、Web パブリッシャーの代わりにサイトやアプリのオーディエンスを測定することのみを目的とする Analytics Cookie に適用されます。 ガイドラインでは、同意除外を適用するには次の条件を満たす必要があることを規定しています。

* 最大 25 か月間のデータ保持期間。現在のデータ保持設定は、Analytics／管理者／データガバナンスで確認できます。[データ保持](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=ja)
* ECID のサードパーティ cookie を無効にします。「[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=ja#id-service-api)」、「[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=ja#id-service-api) [」「disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=ja#id-service-api)」
* 13 か月の Cookie 制限が、周期的ではなく固定の日付に設定されています。 `cookieLifetime` 変数を使用して、Analytics の Cookie の有効期限を上書きできます。  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=ja)
* 限定的な範囲。 Cookie の範囲を 1 つのサイトまたはアプリケーションに限定する必要があります。 [ブラウザーの Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=ja&quot;\l&quot;third-party-cookie-implementations)
* 匿名化. IP アドレスの最終オクテットを匿名化します。 [一般的なアカウント設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=ja)
* 訪問者 ID をレポートに表示しない。  訪問者 ID は、デフォルトでは、Adobe Workspaces と Adobe Reports and Analytics に表示されません。  訪問者 ID は、データフィードと Data Warehouse で使用できます。  データフィードおよび Data Warehouse へのアクセスは、 [Admin Console で設定されるアクセス権限](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ja&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)で制限できます [データフィード列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja#columns%2C-descriptions%2C-and-data-types)
* 位置情報パラメーター。位置情報の精度は郵便番号レベルにすぎません。[郵便番号](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=ja&quot;\l&quot;zip-in-adobe-experience-platform-launch)オプションおよび [一般的なアカウント設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=ja&quot;\l&quot;admin-tools)
* オプトインオプションの設定。  オプトインサービスを使用すると、ユーザーがサイトを訪問した際にユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを決定する訪問者プロトコルを設定できます。[オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)
* データ共有の防止。  Adobe Audience Manager とのデータ共有を防止するには、[プライバシーレポート](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=ja&quot;\l&quot;variables)の `opt.dmp` コンテキスト変数を使用して、ヒットの共有を妨げます。
* アクセス機能と削除機能。 アクセスリクエストと削除リクエストに Privacy Service を利用します。 [Analytics および Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=ja)

## データ収集に関するその他の考慮事項

さらに次の考慮事項が適用されます。

* セグメント化や仮想レポートスイート用のオプトアウトデータからオプトインデータを分離したり、別のエンドポイントにルーティングしたりするために、Analytics 変数でオプトインステータスを収集することを検討してください。
* 事前の同意なしにサイト外またはアプリ外での測定（例：オフサイトキャンペーン、電子メールキャンペーン、iFrame など）はおこないません。
* 変数での個人情報の収集は、同意なしには許可されません。[ユーザーの同意に基づいて Experience Cloud アクティビティを制御する](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=ja&quot;\l&quot;implementation#implementation)
* データは、匿名の統計情報を生成する目的でのみ使用され、他のデータとの組み合わせはおこないません。
* データは、アクションの相互参照には使用されません。
* GPS 位置情報データは収集されません。
* エンドユーザーの同意が得られた場合は、上記の設定を変更し、制限を緩和することができます。

詳しくは、[CNIL Cookie 除外](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)の Web サイトを参照してください。
