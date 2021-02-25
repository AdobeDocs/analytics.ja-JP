---
description: デバイスやブラウザーに不要なCookieを保存または読み取るユーザーの同意に関するガイドラインと推奨事項について説明します。
title: ユーザーの同意とcookieに関するCNILガイドライン
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# CNILの同意除外

2020年10月1日、フランスのデータ保護局(「CNIL」)は、ユーザーのデバイスやブラウザー(「Recommendations」)に不要なcookieや類似のテクノロジーを保存または読み取るユーザーの同意を得るための、改訂版のcookieガイドライン（「ガイドライン」）と最後の推奨事項を公開しました。

ガイドラインでは、同意要件に対する制限付きの除外（「同意除外」）を提供しています。 同意の除外は、Web発行者の代わりにのみサイトまたはアプリのオーディエンスの測定を目的とするAnalytics cookieに適用されます。 ガイドラインでは、同意除外の適用に関して次の条件を満たす必要があることを規定しています。

* 最大25ヶ月のデータ保持期間  現在のデータ保持設定は、Analytics/管理者/データ管理で確認できます。  [データ保持](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* 13か月のcookie制限。  `cookieLifetime`変数を使用して、AnalyticsのCookieの有効期限を上書きできます。  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* 範囲に制限あり。 Cookieの範囲は、1つのサイトまたは1つのアプリケーションに限定する必要があります。 [ブラウザーのCookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;third-party-cookie-implementations)
* 匿名化. IPアドレスの最終オクテットを匿名化します。 [一般的なアカウント設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* 訪問者IDをレポートに表示しない。  訪問者IDは、デフォルトでは、AdobeワークスペースとAdobeReports and Analyticsに表示されません。  訪問者IDは、データフィードおよびData Warehouseで使用できます。  データフィードおよびData Warehouseへのアクセスは、Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;タスク_040673FE3E3E429B9531FBCB8B6A4391)の[アクセス権限によって制限できます
* 位置情報パラメーター 位置情報は、郵便番号レベルと同じ精度ではありません。 [郵便番号](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip in adobe-experience-platform-launch) オプションおよび [一般的なアカウント設定](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* オプトインオプションを設定します。  オプトインサービスでは、訪問者プロトコルを設定して、サイト訪問時にユーザーのデバイスまたはブラウザーにCookieを設定できるかどうかを判断できます。 [オプトインサービス](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* データ共有を禁止します。  Adobe Audience Managerとのデータ共有を禁止するには、[プライバシーレポート](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;変数)の`opt.dmp`コンテキスト変数を使用して、ヒットの共有をブロックします。
* アクセス機能と削除機能。 アクセスおよび削除の要求にPrivacy Serviceを利用します。 [解析とPrivacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## データ収集に関するその他の考慮事項

次の追加の考慮事項が適用されます。

* サイト外の測定(オフサイトキャンペーン、電子メールキャンペーン、iFrameなどの事前の同意なし)は不要です。
* 変数内の個人情報の収集は、同意なしでは許可されません。
* データは、匿名の統計情報を生成する目的でのみ使用され、他のデータとの組み合わせは使用されません。
* データは、アクション間の相互参照には使用されません。
* GPS位置情報データは収集されません。

詳しくは、[CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)のWebサイトを参照してください。
