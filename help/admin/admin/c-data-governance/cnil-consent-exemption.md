---
description: デバイスやブラウザーでの不必要な Cookie の保存や読み取りに対するユーザーの同意についてのガイドラインと推奨事項について説明します。
title: ユーザーの同意と Cookie に関する CNIL ガイドライン
feature: Data Governance
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: c8e3d9bd40a427387da746c084188b5d13f45bcd
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 75%

---

# CNIL 同意除外

2020 年 10 月 1 日、フランスのデータ保護局 (CNIL) は、cookie のガイドライン（「ガイドライン」）の改訂版と、ユーザーのデバイスやブラウザー (「Recommendations」) での不要な cookie および同様の技術の保存または読み取りに対するユーザーの同意の取得に関する最終推奨事項を公開しました。

ガイドラインでは、同意要件（「同意の免除」）に対する制限付きの免除を提供しています。 同意除外は、Web パブリッシャーの代わりにサイトやアプリのオーディエンスを測定することのみを目的とする Analytics Cookie に適用されます。ガイドラインでは、同意除外を適用するには次の条件を満たす必要があることを規定しています。

* 最大 25 か月間のデータ保持期間。現在のデータ保持設定は、以下で確認できます。 [!UICONTROL Analytics] > [!UICONTROL 管理者] > [!UICONTROL データガバナンス].  [データ保持](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=ja)
* ECID のサードパーティ cookie を無効にします。「[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=ja#id-service-api)」、「[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=ja#id-service-api) [」「disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=ja#id-service-api)」
* 13 か月間の cookie 制限。   `cookieLifetime` 変数を使用して、Analytics の cookie の有効期限を上書きできます。  Analytics や ECID を含む Experience Cloud cookie は、各訪問で cookie の有効期限を延長します。  Cookie の静的な非ローリング期限を設定するには、（1）cookie を削除する日付を設定するカスタムコードを記述する、または、（2）CMP を使用して cookie のリセット日を制御します。   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=ja) および [Experience Cloud の cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=ja#ec-cookies)
* 限定的な範囲。Cookie の範囲を 1 つのサイトまたはアプリケーションに限定する必要があります。[ブラウザーの Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* 匿名化.IP アドレスの最終オクテットを匿名化します。[一般的なアカウント設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* 訪問者 ID をレポートに表示しない。  訪問者 ID は、デフォルトでは、Adobe Workspaces と Adobe Reports and Analytics に表示されません。  訪問者 ID は、データフィードと Data Warehouse で使用できます。  データフィードおよび Data Warehouse へのアクセスは、 [Admin Console で設定されるアクセス権限](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja)で制限できます[データフィード列リファレンス](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja#columns%2C-descriptions%2C-and-data-types)
* 位置情報パラメーター。位置情報の精度は郵便番号レベルにすぎません。[郵便番号](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=ja)オプションおよび [一般的なアカウント設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=ja)
* オプトインオプションの設定。  オプトインサービスを使用すると、訪問者プロトコルを設定して、サイトを訪問したユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを決定できます。 [オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)
* データ共有の防止。  Adobe Audience Manager とのデータ共有を防止するには、[プライバシーレポート](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)の `opt.dmp` コンテキスト変数を使用して、ヒットの共有を妨げます。
* アクセス機能と削除機能。アクセスリクエストと削除リクエストに Privacy Service を利用します。[Analytics および Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=ja)

## データ収集に関するその他の考慮事項

さらに次の考慮事項が適用されます。

* Adobe Analytics では、米国、英国およびシンガポールでデータ処理センターを運用しており、すべてのお客様がそれぞれの地域でデータを柔軟に収集、処理、保存できるようになっています。Adobe Analyticsの初期セットアップを設定する際に、お客様はデータ処理センターの目的の場所を選択できます。 顧客のデータは、最終的には、コア Analytics 製品で選択された地域に保存されます。
* セグメント化や仮想レポートスイート用のオプトアウトデータからオプトインデータを分離したり、別のエンドポイントにルーティングしたりするために、Analytics 変数でオプトインステータスを収集することを検討してください。
* 事前の同意なしにサイト外またはアプリ外での測定（例：オフサイトキャンペーン、電子メールキャンペーン、iFrame など）はおこないません。
* 変数での個人情報の収集は、同意なしには許可されません。[ユーザーの同意に基づいて Experience Cloud アクティビティを制御する](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* データは、匿名の統計情報を生成する目的でのみ使用され、他のデータとの組み合わせはおこないません。
* データは、アクションの相互参照には使用されません。
* GPS 位置情報データは収集されません。
* エンドユーザーの同意が得られた場合は、上記の設定を変更し、制限を緩和することができます。

>[!IMPORTANT]
>
>このドキュメントは、法的または規制に関する助言とは異なり、保証または契約上の取り組みをAdobeの一部として構成するものではありません。 当社は、お客様に対し、この件に関連する問題に関するお客様の法的および規制上の義務に関する、独立した法的助言を求めるようお勧めします。


詳しくは、[CNIL Cookie 除外](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)の Web サイトを参照してください。

