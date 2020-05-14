---
title: AnalyticsでのXDMデータの使用
description: 'Adobe AnalyticsでのExperience PlatformからのXDMデータの使用の概要 '
translation-type: tm+mt
source-git-commit: 3526d9f98b545e5f720a0cb127857e7fd5d5388e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---


# Adobe Experience Platform EdgeデータのAnalyticsでの使用

Adobe Experience Platform(AEP) [Web SDK](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) (Adobe Analytics)を使用して、データを送信できます。 これは、 [Experience Data Model(XDM)をAnalyticsで使用される形式に変換することで機能し](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) ます。

Analyticsは、次の2つの方法でXDMデータを収集します。

* XDMスキーマからの自動マッピング

* コンテキストデータへの手動マッピング

## 自動マッピング

[自動マッピングは](https://git.corp.adobe.com/AdobeDocs/analytics.en/blob/master/help/implement/aep-edge/xdm-manual.md) 、XDMのデフォルトの [](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) スキーマに依存しており、通常のAnalyticsデータ収集に含まれるJSONオブジェクトが自動的に入力されます。 XDMから設定したレポートスイートに自動的にマップされる [](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) Analytics変数は、組み込むための開発者サポートは必要ありません。

## 手動マッピング

XDMデータをAnalyticsに手動でマッピングする場合は、 [Analyticsのコンテキストデータ](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) 変数が必要です。 これらの変数は、該当するスキーマに対応するJSONオブジェクトに配置されます。 通常、導入時に、開発チームがコンテキストデータを追加し、管理者が [処理ルールを設定して、そのデータを指定したレポートスイートに適用します](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) 。


## セットアップ

XDMデータを受け取るAnalyticsを設定するには：

1. [Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html)[](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)。

2. 該当するレポートスイートが目的のデータにマップされていることを確認します。 XDMデータは、Adobe Experience Platformから自動的にレポートスイートにフローされます。

