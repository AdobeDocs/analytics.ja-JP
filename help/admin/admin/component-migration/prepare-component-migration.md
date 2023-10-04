---
description: コンポーネントとプロジェクトをAdobe AnalyticsからCustomer Journey Analyticsに移行するために必要な準備について説明します。
title: コンポーネントとプロジェクトをAdobe AnalyticsからCustomer Journey Analyticsに移行する準備
feature: Admin Tools
source-git-commit: cbd991821dc1eefa458ec5d92b75f9b4dfcc9fa0
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 15%

---

# コンポーネントとプロジェクトをAdobe AnalyticsからCustomer Journey Analyticsに移行する準備

組織の誰かがプロジェクトの移行を開始する前に、 [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行](/help/admin/admin/component-migration/component-migration.md)で、以下の節を完了します。

## 前提条件

プロジェクトと関連コンポーネントを移行する準備が整う前に、まず次の手順を実行する必要があります。

* 次のいずれかの方法を使用して、Adobe Experience Platformにデータを取り込み、Adobe AnalyticsレポートスイートデータをCustomer Journey Analyticsで表示します。

  >[!NOTE]
  >
  >  WebSDK を使用してデータを取り込む場合、すべてのスキーマフィールドを手動でマッピングする必要があります。 ( マッピングプロセスについて詳しくは、 [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行](/help/admin/admin/component-migration/component-migration.md))


   * Adobe Analyticsソースコネクタを使用するには、次の操作が必要です。

      * [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むためのレポートスイートの設定](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      * [データの取り込みと使用](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ja)

   * WebSDK を使用するには、次の操作が必要です。

      * [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むためのレポートスイートの設定](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      * [Adobe Experience Platform Web SDK を使用したデータの取り込み](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

* の作成 [接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=ja) および [データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja) 取り込まれたデータを使用します。

* データがマッピングされるデータビューにCustomer Journey Analytics内のユーザーがプロビジョニングされていることを確認します。

  詳しくは、 [Customer Journey AnalyticsのAdmin Console権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analyticsアクセス制御](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  「権限」タブは、Admin Console の各製品プロファイルの一部です。特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。

* コンポーネントのマッピング方法を組織として決定します。

  詳しくは、以下の節を参照してください。 [組織として、コンポーネントのマッピング方法を決定します。](#decide-as-an-organization-how-you-will-map-components).

## 移行に含まれる機能の理解

移行に含まれるプロジェクト要素とコンポーネントの概要を次の表に示します。

### 移行されるコンポーネント要素

Dimensionと指標は、 [Adobe AnalyticsプロジェクトのCustomer Journey Analyticsへの移行](#migrate-adobe-analytics-projects-to-customer-journey-analytics)に基づいて、セグメントと日付範囲は、

|  | 移行済み |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimensionと指標：いいえ<p>セグメントと日付範囲： ![チェックマーク](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共有](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensionと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |
| **[説明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensionと指標：いいえ<p>セグメントと日付範囲： ![チェックマーク](assets/Smock_Checkmark_18_N.svg)</p> |
| **[タグ](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensionと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |
| **[アトリビューション（ディメンションに対する）](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensionと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |

{style="table-layout:auto"}

### 移行されるプロジェクト要素

|  | 移行済み |
|---------|----------|
| **[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[セグメント](/help/components/segmentation/seg-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[ディメンション](/help/components/dimensions/overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[指標](/help/components/metrics/overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[パネル](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 移行を実行するユーザーによって定義 |
| **[キュレーション](/help/analyze/analysis-workspace/curate-share/curate.md)** | × |
| **[共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | × |
| **[注釈](/help/analyze/analysis-workspace/components/annotations/overview.md)** | × |
| **[フォルダー構造](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | × |
| **[説明](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[タグ](/help/analyze/landing.md)** | × |
| **[お気に入り](/help/analyze/landing.md)** | × |
| **[スケジュール](/help/components/scheduled-projects-manager.md)** | × |
| **[異常値検出](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## エラーの原因となる、サポートされていない要素を理解する

次のビジュアライゼーション、パネルおよび機能は、Customer Journey Analyticsではサポートされていません。 これらの要素が移行前にプロジェクトに含まれている場合、移行が失敗するか、プロジェクトの移行後にエラーが発生する可能性があります。

プロジェクトをCustomer Journey Analyticsに移行する前に、これらの要素をAdobe Analyticsプロジェクトから削除します。 移行が失敗した場合は、移行を再試行する前にこれらの要素を削除します。

### サポートされないビジュアライゼーション

* [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### サポートされていないパネル

* [Analytics for Target（A4T）](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [メディア分平均オーディエンス](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [次または前の項目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [ページの概要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

### サポートされない機能

* [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [アラート](/help/components/c-alerts/intellligent-alerts.md)

## 組織として、コンポーネントのマッピング方法を決定します。

>[!IMPORTANT]
>
>Customer Journey Analyticsプロセスでは、Adobe Analyticsプロジェクト内のコンポーネントが識別されます。このコンポーネントは移行時に自動的にコンポーネントにマッピングされず、手動でマッピングできます。
>
>**1 つのプロジェクトに対して行われたマッピングは、移行を実行しているユーザーに関係なく、組織全体の今後のすべてのプロジェクトに適用されます。 これらのマッピングは、カスタマーケアに問い合わせる以外は、変更または取り消しできません。**
>
>このため、プロジェクトを移行する前に、組織がディメンションと指標のマッピング方法を決定することが重要です。 これにより、1 つのプロジェクトのみを考慮する場合に、個々の管理者がサイロで意思決定を行うのを防ぐことができます。
>
>次に、プロジェクトに存在する場合に手動でマッピングする必要があるディメンションと指標のリストを示します。 移行する前に、このリストを確認することをお勧めします。 プロジェクト内にこれらのコンポーネントが存在する場合は、どのCustomer Journey Analyticsコンポーネントにマッピングするかを今すぐ決定します。


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
* 跳ね返る
* pageevents
* pageviewspervisit
* orderspervisit
* averagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* 新規エンゲージメント
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* デバイス
* 推定担当者
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression