---
description: デバイスやブラウザーでの不必要な Cookie の保存や読み取りに対するユーザーの同意についてのガイドラインとレコメンデーションについて説明します。
title: ユーザーの同意と Cookie に関する CNIL ガイドライン
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
TQID: 'https://experienceleague.adobe.com/DNqDZWOm1buhq-vLG3io11v-s-7SAXfb6W3A9VAOtXw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 769
ht-degree: 91%

---

# CNIL 同意除外

2020年10月1日（PT）、フランスのデータ保護局（以下「CNIL」）は、ユーザーのデバイスやブラウザーで不必要な Cookie や類似のテクノロジーを保存または読み取ることに対するユーザーの同意の取得に関する Cookie ガイドラインの改訂版（以下「ガイドライン」）とレコメンデーションの最終版（以下「レコメンデーション」）を公開しました。

ガイドラインでは、同意要件に対する制限付きの適用の例外（以下「同意の免除」）を規定しています。 同意除外は、Web パブリッシャーの代わりにサイトやアプリのオーディエンスを測定することのみを目的とする Analytics Cookie に適用されます。 ガイドラインでは、同意除外を適用するには次の条件を満たす必要があることを規定しています。

* 最大 25 か月間のデータ保持期間。  現在のデータ保持設定は、[!UICONTROL Analytics]／[!UICONTROL 管理者]／[!UICONTROL データガバナンス]で確認できます。  [データ保持](/help/technotes/data-retention.md)
* ECID のサードパーティ cookie を無効にします。 「[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=ja#id-service-api)」、「[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=ja#id-service-api) [」「disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=ja#id-service-api)」
* 13 か月間の cookie 制限。  `cookieLifetime` 変数を使用して、Analytics の cookie の有効期限を上書きできます。 AnalyticsやECIDを含むCX Enterprise Cookieは、訪問ごとにCookieの有効期限を延長します。  静的でローリングしないCookieの有効期限を設定するには、（1） Cookieを削除する日付を設定するカスタムコードを記述するか、（2） CMPを使用してCookieのリセット日を制御します。  [cookieLifetime](/help/implement/vars/config-vars/cookielifetime.md)および[CX エンタープライズ Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=ja#ec-cookies)
* 限定的な範囲。 Cookie の範囲を 1 つのサイトまたはアプリケーションに限定する必要があります。 [ブラウザーの Cookie](/help/technotes/cookies/cookies.md#third-party-cookie-limitations)
* 匿名化. IP アドレスの最終オクテットを匿名化します。 [一般的なアカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* 訪問者 ID をレポートに表示しない。  訪問者 ID は、デフォルトでは、Adobe Workspaces と Adobe Reports and Analytics に表示されません。  訪問者 ID は、データフィードと Data Warehouse で使用できます。  データフィードおよびデータウェアハウスへのアクセスは、[Admin Console でのアクセス権限](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja)と[データフィード列リファレンス](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)で制限できます
* 位置情報パラメーター。 位置情報の精度は郵便番号レベルにすぎません。 [郵便番号](/help/implement/vars/page-vars/zip.md)オプションおよび [一般的なアカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
* オプトインオプションの設定。  オプトインサービスを使用すると、ユーザーがサイトを訪問した際にユーザーのデバイスまたはブラウザーに Cookie を設定できるかどうかを決定する訪問者プロトコルを設定できます。 [オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ja)
* データ共有の防止。  Adobe Audience Manager とのデータ共有を防止するには、[プライバシーレポート](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)の `opt.dmp` コンテキスト変数を使用して、ヒットの共有を妨げます。
* アクセス機能と削除機能。 アクセスリクエストと削除リクエストに Privacy Service を利用します。 [Analytics および Privacy Service](gdpr.md)

## データ収集に関するその他の考慮事項

さらに次の考慮事項が適用されます。

* Adobe Analytics では、米国、英国およびシンガポールでデータ処理センターを運用しており、すべてのお客様がそれぞれの地域でデータを柔軟に収集、処理、保存できるようになっています。 Adobe Analytics の初期セットアップを設定する際に、お客様は希望するデータ処理センターの場所を選択できます。 お客様のデータは、最終的には、コア Analytics 製品で選択した地域内に保存されます。
* セグメント化や仮想レポートスイート用のオプトアウトデータからオプトインデータを分離したり、別のエンドポイントにルーティングしたりするために、Analytics 変数でオプトインステータスを収集することを検討してください。
* 事前の同意なしにサイト外またはアプリ外での測定（例：オフサイトキャンペーン、メールキャンペーン、iFrame など）はおこないません。
* 変数での個人情報の収集は、同意なしには許可されません。 [&#x200B; ユーザーの同意に基づいてCX エンタープライズ アクティビティを制御](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=ja#implementing-opt-in-on-the-page)
* データは、匿名の統計情報を生成する目的でのみ使用され、他のデータとの組み合わせはおこないません。
* データは、アクションの相互参照には使用されません。
* GPS 位置情報データは収集されません。
* エンドユーザーの同意が得られた場合は、上記の設定を変更し、制限を緩和することができます。

>[!IMPORTANT]
>
>このドキュメントは、法的または規制に関する助言を意図したものではありません。また、アドビの一部として保証または契約上の取り組みを構成するものでもありません。 当社は、お客様に対し、この件に関連する問題に関するお客様の法的および規制上の義務について、独立した法的助言を求めるようお勧めします。

詳しくは、[CNIL Cookie の例外](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)の Web サイトを参照してください。
