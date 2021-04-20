---
description: 一般的な項目（課金、ログなど）、会社の管理、ツール、Web サービスへのアクセス、Report Builder および Data Connectors の統合に関するユーザー権限を有効にします。
keywords: グループ;権限
subtopic: Users and groups
title: Analytics ツールの権限のカスタマイズ
feature: Admin Tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
exl-id: fe3a9f65-f121-438f-91d0-45cfaea94416
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 100%

---

# Analytics ツールの権限のカスタマイズ

>[!IMPORTANT]
>
>ユーザーと製品の管理は [Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移動しました。ユーザーを移行する時期は、アドビから通知されます。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

一般的な項目（課金、ログなど）、会社の管理、ツール、Web サービスへのアクセス、Report Builder および Data Connectors の統合に関するユーザー権限を有効にします。

**[!UICONTROL ユーザー管理]**／**[!UICONTROL グループ]**／**[!UICONTROL すべてのレポートアクセス]**／**[!UICONTROL Analytics ツール]**／**[!UICONTROL カスタマイズ]**

>[!NOTE]
>
>2016 年秋のリリース（10 月 21 日）で、グループ管理に変更が加えられました。変更の概要については、[管理上の変更 - 2016 年秋](/help/admin/user-management2/c-user-management/permissions-changes.md)を参照してください。

## レポートアクセス - Analytics ツール

![](assets/report-access-analytics-tools.png)

「**[!UICONTROL カスタマイズ]**」をクリックして、このグループがアクセスする項目を選択します。

## フィールドの説明

このページの設定は、[!UICONTROL ユーザーグループの定義]ページで選択されたレポートスイートに関係します。

| 要素 | 説明 |
|--- |--- |
| **一般** |  |
| [コードマネージャー](/help/admin/admin/code-manager-admin.md) | Web およびモバイルプラットフォーム用のデータ収集コードをダウンロードする権限を有効にします。 |
| コードマネージャー - Web サービス | Web サービスを使用したコードマネージャーへのアクセスを管理者以外のユーザーに許可します。 |
| [ログ](/help/admin/admin/logs.md) | ユーザーがログインした時間、ユーザーの使用量、アクセス、レポートスイート、管理者による変更を確認するのに役立つログファイルに対する権限を有効にします。 |
| ログ - Web サービス | Web サービスを使用した管理ツールのログへのアクセスを管理者以外のユーザーに許可します。 |
| [トラフィック管理](/help/admin/c-traffic-management/traffic-management.md) | トラフィック管理ページでは、予想されるトラフィック量の変化を指定できます。 |
| 権限管理 | 管理ツールのユーザー管理ページへのアクセス権を管理者以外のユーザーに付与します。読み取り権限がありますが、書き込み権限はありません。 |
| 権限（書き込み） - Web サービス | 管理者以外のユーザーが Web サービスのユーザー管理で権限設定の読み取り／書き込みをおこなうことができるようにします。<br>この設定は、特に、管理 API の該当する権限アクションを指します。 |
| 権限（読み取り） - Web サービス | 管理者以外のユーザーが Web サービスのユーザー管理に権限設定を表示できるようにします。<br>この設定は、特に、管理 API の該当する権限アクションを指します。 |
| **会社管理** |  |
| [セキュリティ](/help/admin/company/security-manager.md) | レポートデータへのアクセスを制御するセキュリティマネージャーページに対する権限を付与します。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。 |
| サポート情報 | カンパニー設定のサポート情報に対する権限を付与します。 |
| [Web サービス](/help/admin/company/web-services-admin.md) | 管理ツールインターフェイスの Web サービスページにアクセスできるようにします（[!UICONTROL カンパニー設定]／[!UICONTROL Web サービス]）。<br>Web Services API を使用すると、ユーザーインターフェイスを通じて使用可能な機能を複製および補強する Adobe Analytics サービスにプログラムレベルでアクセスできます。 |
| シングルサインオン（レガシー） | 管理ツールのシングルサインオンページへのアクセス権を付与します。<br>**注意**：Adobe Experience Cloud のシングルサインオンは、Experience Cloud とソリューションの間の[アカウントのリンク](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)を使用して実装されます。 |
| [保留中のアクション](/help/admin/company/pending-actions-admin.md) | [!UICONTROL カンパニー設定]の保留中のアクションを管理する権限を付与します。 |
| [ブランド提携](/help/admin/company/co-branding-admin.md) | Analytics のコブランド化の権限を付与します。 |
| [環境設定](/help/admin/admin/preferences-manager.md) | [!UICONTROL Preference Manager] に対する権限を付与します。 |
| [レポートスイートを非表示](/help/admin/company/c-hide-report-suites.md) | Adobe Analytics ユーザーインターフェイスでレポートスイートを非表示にする権限を付与します。 |
| **ツール** | これらの設定は、Analytics ツール（インターフェイスおよびアプリケーション）およびセグメンテーションや計算指標などの高度な機能へのアクセス権を付与します。 |
| [現在のデータ](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/current-data.html) | レポートの「現在のデータ」機能を使用する権限を付与します。 |
| Web サービスへのアクセス | 管理者以外のユーザーの Web サービスへのアクセスを有効にします。Web サービス資格情報を生成します。 |
| [Report Builder](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | このグループのメンバーに [!UICONTROL Report Builder] ライセンスへのアクセス権を付与します。 |
| [Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) アクセス | [!DNL Adobe Analytics] の推奨レポートインターフェイスである、Analysis Workspace へのアクセス権をユーザーに付与します。 |
| [Reports &amp; Analytics](https://docs.adobe.com/content/help/ja-JP/analytics/landing/an-key-concepts.html) | Reports &amp; Analytics へのアクセス権をユーザーに付与します。 |
| [計算指標の作成](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/cm-overview.html) | 計算指標を作成する権限をユーザーに付与します。 |
| [セグメントの作成](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html) | セグメントを作成する権限をユーザーに付与します。 |
| **Data Connectors** |  |
| 統合（作成、更新または削除） | Data Connector 統合を作成、更新および削除する権限を付与します。 |
