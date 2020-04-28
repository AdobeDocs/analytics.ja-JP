---
title: AnalyticsでのXDMデータの使用
description: 'Adobe AnalyticsでのExperience PlatformのXDMデータの使用の概要 '
translation-type: tm+mt
source-git-commit: 31efa43043120b68de90e817a7980addbe2ded39

---




# Adobe Experience Platform EdgeデータのAnalyticsでの使用

>[!IMPORTANT]
>
>Adobe Experience Edge Web SDKはリリースされておらず、招待ユーザーのベータテストのみで利用できます。 このドキュメントはベータ版ユーザーのみを対象としており、機能の完全な機能を示すものではありません。この機能のベータ版ユーザーになりたい場合は、アドビ[カスタマーケア](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)にお問い合わせください。


Adobe Experience Platform(AEP)Web SDK [を使用して](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) 、Adobe Analyticsにデータを送信できます。 これは、 [Experience Data Model(XDM)をAnalyticsで使用される形式に変換することで](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) 機能します。

Analyticsは、次の2つの方法でXDMデータを収集します。

* XDMからの自動マッピングスキーマ

* コンテキストデータへの手動マッピング

## 自動マッピング

自動マッピングは、XDMのデフォル [トの](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) スキーマに依存し、通常のAnalyticsデータ収集に含まれるJSONオブジェクトが自動的に入力されます。 XDMから設定した [レポートスイートに自動的にマッピングされるAnalytics変数は](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) 、開発者サポートを組み込む必要はありません。

## 手動マッピング

XDMデータのAnalyticsへの手動マッピングは、 [Analyticsのコンテキストデータ変数に依存しま](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) す。 これらの変数は、該当する変数に対応するJSONオブジェクトにスキーマされます。 通常、開発チームは導入時にコンテキストデータを追加し、管理者は処理ルールを設定し [て指定したレポート](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) スイートにそのデータを適用します。


## セットアップ

XDMデータを受け取るAnalyticsを設定するには：

1. [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) Web SDKをインスト [ールして設定します](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)。

2. 該当するレポートスイートが目的のデータにマップされていることを確認します。 XDMデータは、Adobe Experience Platformから自動的にレポートスイートにフローされます。

