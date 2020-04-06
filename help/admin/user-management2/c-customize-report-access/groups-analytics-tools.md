---
description: 一般的な項目（課金、ログなど）、会社の管理、ツール、Web サービスへのアクセス、Report Builder および Data Connectors の統合に関するユーザー権限を有効にします。
keywords: groups;permissions
subtopic: Users and groups
title: Analytics ツールの権限のカスタマイズ
topic: Admin tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics ツールの権限のカスタマイズ

>[!IMPORTANT]
>
>ユーザーと製品の管理は [Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移動しました。ユーザーを移行する時期は、アドビから通知されます。After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** will be retired.

一般的な項目（課金、ログなど）、会社の管理、ツール、Web サービスへのアクセス、Report Builder および Data Connectors の統合に関するユーザー権限を有効にします。

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL All Report Access]** > **[!UICONTROL Analytics Tools]** > **[!UICONTROL Customize]**

>[!NOTE]2016 年秋のリリース（10 月 21 日）で、グループ管理に変更が加えられました。変更の概要については、[管理上の変更 - 2016 年秋](/help/admin/user-management2/c-user-management/permissions-changes.md)を参照してください。

## レポートアクセス - Analytics ツール

![](assets/report-access-analytics-tools.png)

Click **[!UICONTROL Customize]** to select items to which this group will have access.

## フィールドの説明

このページの設定は、そのページで選択したレポートスイートに関連 [!UICONTROL Define User Groups] します。

| 要素 | 説明 |
|--- |--- |
| **一般** |  |
| [コードマネージャー](/help/admin/admin/code-manager-admin.md) | Webおよびモバイルプラットフォーム用のデータ収集コードをダウンロードする権限を有効にします。 |
| コードマネージャー - Web サービス | 管理者以外のユーザーがWebサービスを通じてコードマネージャーにアクセスできるようにします。 |
| [ログ](/help/admin/admin/logs.md) | ログファイルに対する権限を有効にします。ログファイルは、ユーザーがログインしたとき、ユーザーの使用状況、アクセス、レポートスイート、管理者による変更を確認するのに役立ちます。 |
| ログ - Web サービス | 管理者以外のユーザーがWebサービスを通じて管理ツールのログにアクセスできるようにします。 |
| [トラフィック管理](/help/admin/c-traffic-management/traffic-management.md) | トラフィック管理ページでは、予想されるトラフィック量の変化を指定できます。 |
| 権限管理 | 管理ツールのユーザー管理ページへのアクセス権を管理者以外のユーザーに付与します。 これらのユーザーは読み取り権限を持っていますが、書き込み権限は持っていません。 |
| 権限（書き込み） - Web サービス | 管理者以外のユーザーに、WebサービスのUser Managementの読み取りおよび書き込み権限の設定を許可します。<br>この設定は、特に、管理 API の該当する権限アクションを指します。 |
| 権限（読み取り） - Web サービス | 管理者以外のユーザーに対して、WebサービスのUser Managementの表示権限の設定を許可します。<br>この設定は、特に、管理 API の該当する権限アクションを指します。 |
| **会社管理** |  |
| [セキュリティ](/help/admin/company/security-manager.md) | レポートデータへのアクセスを制御するセキュリティマネージャーページに対する権限を付与します。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。 |
| サポート情報 | カンパニー設定のサポート情報に対する権限を付与します。 |
| [Web サービス](/help/admin/company/web-services-admin.md) | 管理ツールインターフェイス(/[!UICONTROL Company Settings] )のWebサービスページへのアクセスを許可 [!UICONTROL Web Services]します。<br>Web Services API を使用すると、ユーザーインターフェイスを通じて使用可能な機能を複製および補強する Adobe Analytics サービスにプログラムレベルでアクセスできます。 |
| シングルサインオン（レガシー） | 管理ツールのシングルサインオンページへのアクセスを許可します。<br>**注意：**Adobe Experience Cloud のシングルサインオンは、Experience Cloud とソリューションの間の[アカウントのリンク](https://marketing.adobe.com/resources/help/ja_JP/mcloud/organizations.html)を使用して実装されます。 |
| [保留中のアクション](/help/admin/company/pending-actions-admin.md) | Grants permission to manage pending actions in [!UICONTROL Company Settings]. |
| [ブランド提携](/help/admin/company/co-branding-admin.md) | Analytics のコブランド化の権限を付与します。 |
| [環境設定](/help/admin/admin/preferences-manager.md) | Grants permission to the [!UICONTROL Preference Manager]. |
| [レポートスイートを非表示](/help/admin/company/c-hide-report-suites.md) | Adobe Analytics ユーザーインターフェイスでレポートスイートを非表示にする権限を付与します。 |
| **ツール** | これらの設定により、Analyticsツール（インターフェイスおよびアプリケーション）や、セグメント化や計算指標などの高度な機能に対するアクセス権が付与されます。 |
| [現在のデータ](https://marketing.adobe.com/resources/help/ja_JP/reference/data_latency.html) | 現在のデータ機能を使用する権限をレポートします。 |
| [Ad Hoc Analysis ライセンスユーザー](https://marketing.adobe.com/resources/help/ja_JP/dsc/) | アクセス権を付与しま [!UICONTROL Ad Hoc Analysis]す。 |
| Web サービスへのアクセス | 管理者以外のユーザーのWebサービスへのアクセスを有効にします。 Webサービス資格情報を生成します。 |
| [Report Builder](https://marketing.adobe.com/resources/help/ja_JP/arb/setup.html) | このグループのメンバーにライセンスへのアクセスを許 [!UICONTROL Report Builder] 可します。 |
| [Analysis Workspace アクセス](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/) | [!DNL Adobe Analytics] の推奨レポートインターフェイスである、Analysis Workspace へのアクセス権をユーザーに付与します。 |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/ja_JP/sc/user/) | Reports &amp; Analytics へのアクセス権をユーザーに付与します。 |
| [計算指標の作成](https://marketing.adobe.com/resources/help/ja_JP/analytics/calcmetrics/) | 計算指標を作成する権限をユーザーに付与します。 |
| [セグメントの作成](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/) | セグメントを作成する権限をユーザーに付与します。 |
| **Data Connectors** |  |
| 統合（作成、更新または削除） | Data Connector 統合を作成、更新および削除する権限を付与します。 |
