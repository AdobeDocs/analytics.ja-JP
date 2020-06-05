---
description: 広告分析ワークフローの概要です。
title: ワークフローの概要
translation-type: tm+mt
source-git-commit: b92beee43756a3c5ec3902eee4ffaab0bcd43ce9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 75%

---


# ワークフローの概要

![](assets/step1_icon.png) Google/Bing検索データの表示を行うAdobe AnalyticsレポートスイートをExperience Cloud組織にマッピングします。

[組織へのレポートスイートのマッピング](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)を参照してください。

![](assets/step2_icon.png) [レポートスイートごとの Advertising Analytics レポートの有効化](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)

Enables [!UICONTROL Advertising Analytics] reporting for Experience-Cloud-enabled report suites.

![](assets/step3_icon.png) [Advertising Analytics アカウントの設定](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)

Analytics 管理ツールで設定します。

![](assets/step4_icon.png) [Analytics での広告データのレポート](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)

注意：検索データは、Adobe Analytics データセンターのタイムゾーンの午前 6 時ごろに検索エンジンから取り込まれます。この時点で AMO データが収集され、レポートスイートに挿入されます。さらに AMO データは Analytics へのデータ挿入の一環としてレポートスイートのタイムゾーンに変換されます。

レポートは以下で利用できます。

* Analysis Workspace: [!UICONTROL Paid Search Performance] template
* Reports &amp; Analytics
* Report Builder
* Analytics レポート API

![](assets/step5_icon.png) [広告アカウントの管理](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)

アカウントの状態をチェックして、アカウントを編集／一時停止できます。
