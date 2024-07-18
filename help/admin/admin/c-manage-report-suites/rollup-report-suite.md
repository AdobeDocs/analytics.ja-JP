---
description: グローバルレポートスイートの説明
title: グローバルレポートスイート
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 100%

---

# グローバルレポートスイート

グローバルレポートスイートは、組織が所有するすべてのドメインとアプリケーションからデータを収集します。すべてのイメージリクエストを単一のレポートスイートに送信するための実装が必要です。

アドビでは、ほとんどの場合、グローバルレポートスイートを実装することをお勧めします。グローバルレポートスイートを実装する利点については、[グローバルレポートスイートの考慮事項](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=ja)を参照してください。

マルチスイートタグ付け&#x200B;**&#x200B;と仮想レポートスイートのアプローチ&#x200B;**&#x200B;を使用して、貴社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます。

* **マルチスイートタグ付け**：マルチスイートタグ付けを使用すると、グローバルレポートスイートだけでなく、個々の子レポートスイートにもイメージリクエストを送信できます。グローバルレポートデータは、すべてのレポートスイートで重複排除されます。

  例えば、あるグローバルレポートスイートですべてのデータを収集し、ブランド、地域または別の差別化要因に基づいてセカンダリレポートスイートを設定するとします。 その場合、社内の様々なチームが、関係のあるレポートスイートのデータに焦点を合わせることができます。

  マルチスイートタグ付けを使用するには、子レポートスイートと、子から得られるすべてのデータを含んだグローバルレポートスイートを実装します。web ページやアプリのトラッキングコードには、グローバルレポートスイートのレポートスイート ID（RSID）と、該当する子レポートスイートの RSID が含まれます。<!-- Wording/be more specific? And include any links? -->

  イメージリクエストの各レポートスイートに対して、個別のサーバーコールが実行されます。子レポートスイートへのコールはセカンダリコールです。

* **仮想レポートスイート**：[仮想レポートスイート](/help/components/vrs/vrs-about.md)は、グローバルレポートスイートで収集され、指定のユーザーグループが使用できる、指定のセグメントに関するクエリです。仮想レポートスイートでは、マルチスイートタグ付けを使用せずに、様々なエンドユーザーのレポート要素をキュレートできるので、セカンダリサーバーコールを回避できます。

  仮想レポートスイートを使用するには、グローバルレポートスイートを実装してからデータを解析し、特定のセグメントが適用され、特定のグループ権限を持つ仮想レポートスイートを作成します。仮想レポートスイートは、仮想レポートスイートマネージャー（[!UICONTROL コンポーネント]／[!UICONTROL 仮想レポートスイート]）で作成できます。詳しくは、[仮想レポートスイートのワークフロー](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)を参照してください。

マルチスイートタグ付けの代わりに仮想レポートスイートを使用することは、多くの場合、ベストプラクティスですが、仮想レポートスイートにはいくつかの制限があります。ビジネスニーズに最適なレポートスイートのアプローチを決定するには、[仮想レポートスイートとマルチスイートタグ付けに関する考慮事項](/help/components/vrs/vrs-considerations.md)を参照してください。仮想レポートスイートとマルチスイートタグ付け機能の詳細な比較について詳しくは、[仮想レポートスイートとマルチスイートタグ付けの比較](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)を参照してください。

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
