---
description: Advertising Analytics ワークフローの概要
title: ワークフローの概要
feature: Advertising Analytics
exl-id: 00993c19-1e74-4a97-b16a-967feab13b32
TQID: 'https://experienceleague.adobe.com/Xrm-gn59uSRzBKtwY1Z6O40b7d0MS-LH-Y96hLjbJKQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 42%

---

# ワークフローの概要

Advertising Analyticsの設定ワークフローは、次の手順で構成されます。

<!--
>[!VIDEO](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/integrations/ad-cloud/configuring-advertising-analytics)
-->

1. [レポートスイートごとの Advertising Analytics レポートの有効化](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md). Experience Cloud 対応レポートスイートの [!UICONTROL Advertising Analytics] レポートを有効にします。
2. [Advertising Analytics アカウントの設定](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md). Analytics 管理ツールで設定します。
3. [Analytics での広告データのレポート](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md). 検索データは、Adobe Analytics データセンターのタイムゾーンの午前6時頃（06:00）に検索エンジンから取得されます。 Adobe Advertising データが収集され、レポートスイートに挿入されます。 データをAnalyticsに挿入する一環としてレポートスイートのタイムゾーンに変換されます。 レポートは、Analysis Workspace（有料検索パフォーマンステンプレート）、Report Builder、およびAnalytics レポート APIで使用できます。
4. [広告アカウントの管理](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md). アカウントの状態をチェックして、アカウントを編集／一時停止できます。
