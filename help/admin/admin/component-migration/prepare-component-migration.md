---
description: Adobe AnalyticsからCustomer Journey Analyticsにコンポーネントやプロジェクトを移行するための準備に必要な準備について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 9%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備

[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行 ](/help/admin/admin/component-migration/component-migration.md) に記載されている手順に従って、組織内の任意のユーザーがプロジェクトの移行を開始する前に、次の節を完了してください。

## 前提条件

プロジェクトと関連コンポーネントを移行する準備を整える前に、まずAdobe Customer Journey Analytics ガイドの [Adobe Analyticsからの進化 ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=ja) の手順に従う必要があります。 手順は次のとおりです。

1. Adobe Analytics レポートスイートデータをCustomer Journey Analyticsで表示するには、次のいずれかの方法を使用して、データをAdobe Experience Platformに取り込みます。

   >[!NOTE]
   >
   >  WebSDK を使用してデータを取り込む場合は、すべてのスキーマフィールドを手動でマッピングする必要があります。 （マッピングプロセスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行 ](/help/admin/admin/component-migration/component-migration.md) を参照してください。


   * Adobe Analytics ソースコネクタを使用するには、次の操作が必要です。

      1. [Adobe Experience PlatformおよびCustomer Journey Analyticsに取り込むレポートスイートの設定 ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [ データの取り込みと使用 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ja)

   * WebSDK を使用するには、次の操作が必要です。

      1. [Adobe Experience PlatformおよびCustomer Journey Analyticsに取り込むレポートスイートの設定 ](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Adobe Experience Platform Web SDK を使用したデータの取得 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. 取り込んだデータを使用して [ 接続 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) および [ データビュー ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja) を作成します。

1. Customer Journey Analyticsのユーザーが、データがマッピングされているデータビューにプロビジョニングされていることを確認します。

   詳しくは、[&#128279;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html)Customer Journey Analyticsアクセス制御の [Admin ConsoleのCustomer Journey Analytics権限 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) を参照してくだ  い。

   「権限」タブは、Admin Consoleの各製品プロファイルの一部です。 特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。

1. コンポーネントのマッピング方法を組織として決定します。

   詳しくは、以下の節 [ コンポーネントのマッピング方法を組織として決定 ](#decide-as-an-organization-how-you-will-map-components) を参照してください。

## 移行に含まれる内容を理解する

次の表は、移行に含めるプロジェクトとコンポーネントの要素の概要を示しています。

### 移行されるコンポーネント要素

Dimensionと指標は、[Adobe Analytics プロジェクトのCustomer Journey Analyticsへの移行 ](#migrate-adobe-analytics-projects-to-customer-journey-analytics) に示されているマッピングプロセスの一環として移行されます。

Customer Journey Analyticsにまだ存在しないセグメント、日付範囲、計算指標は、マッピングされたディメンションと指標に基づいてそこに再作成されます。

|  | 移行済み |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimensionと指標：なし<p>セグメントと日付範囲：![ チェックマーク ](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共有](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensionと指標：なし<p>セグメントと日付範囲：なし</p> |
| **[説明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensionと指標：なし<p>セグメントと日付範囲：![ チェックマーク ](assets/Smock_Checkmark_18_N.svg)</p> |
| **[タグ](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensionと指標：なし<p>セグメントと日付範囲：なし</p> |
| **[アトリビューション（ディメンション上）](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensionと指標：なし<p>セグメントと日付範囲：なし</p> |

{style="table-layout:auto"}

### 移行されるプロジェクト要素

|  | 移行済み |
|---------|----------|
| **[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[セグメント](/help/components/segmentation/seg-overview.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[ディメンション](/help/components/dimensions/overview.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[指標](/help/components/metrics/overview.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[パネル](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) 移行を行うユーザーによって定義されます |
| **[キュレーション](/help/analyze/analysis-workspace/curate-share/curate.md)** | × |
| **[共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | × |
| **[注釈](/help/analyze/analysis-workspace/components/annotations/overview.md)** | × |
| **[フォルダー構造](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | × |
| **[説明](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |
| **[タグ](/help/analyze/landing.md)** | × |
| **[お気に入り](/help/analyze/landing.md)** | × |
| **[スケジュール](/help/components/scheduled-projects-manager.md)** | × |
| **[異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![ チェックマーク ](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## エラーを引き起こすサポートされていない要素について

次のビジュアライゼーションとパネルは、Customer Journey Analyticsではサポートされていません。 移行前のプロジェクトにこれらの要素が含まれていると、移行が失敗したり、プロジェクトの移行後にエラーが発生する可能性があります。

プロジェクトをCustomer Journey Analyticsに移行する前に、これらの要素をAdobe Analytics プロジェクトから削除します。 移行が失敗した場合は、移行を再試行する前にこれらの要素を削除します。

### サポートされていないビジュアライゼーション

* [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### サポートされていないパネル

* [Analytics for Target（A4T）](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [メディア分平均オーディエンス](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [次または前の項目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [ページの概要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [貢献度分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## コンポーネントのマッピング方法を組織として決定する

>[!IMPORTANT]
>
>この移行プロセスでは、Customer Journey Analytics内のコンポーネントに自動的にマッピングできないAdobe Analytics プロジェクトのコンポーネントを特定し、手動でマッピングできるようにします。
>
>**1 つのプロジェクトで行われたマッピングは、移行を実行するユーザーに関係なく、IMS 組織全体の今後のすべてのプロジェクトに適用されます。 これらのマッピングは、カスタマーケアに連絡しない限り、変更したり取り消したりすることはできません。**
>
>このため、プロジェクトを移行する前に、組織でディメンションと指標のマッピング方法を決定することが重要です。 これにより、個々の管理者が 1 つのプロジェクトのみを検討する際に、サイロ内で決定を下すことを回避できます。
>
>以下は、プロジェクトに存在する場合に手動でマッピングする必要があるディメンションと指標のリストです。 移行前に、このリストを確認することをお勧めします。 これらのコンポーネントがプロジェクトに存在する場合は、マッピング先のCustomer Journey Analyticsコンポーネントを決定します。


### 手動でマッピングする必要があるDimension

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* category
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### 手動でマッピングする必要がある指標

* timespentvisit
* timespentvisitor
* リロード
* bounces
* バウンス
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* 暗い訪問者
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* newengagements
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* デバイス
* estimatedpeople
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression
