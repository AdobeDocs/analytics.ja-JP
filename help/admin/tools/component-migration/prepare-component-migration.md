---
description: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行に備えて必要な準備について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行の準備
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
TQID: https://experienceleague.adobe.com/MneXzLSy9umkfoSWXFBrUn3zc-exo2OUTbiQZ1N3ZbA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1005
ht-degree: 8%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行の準備

組織内の誰もが、[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行](/help/admin/tools/component-migration/component-migration.md)の説明に従ってプロジェクトの移行を開始する前に、次の節を完了してください。

## 前提条件

プロジェクトとその関連コンポーネントを移行する準備が整う前に、最初にAdobe Customer Journey Analytics ガイドの「[Adobe Analyticsからの進化](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=ja)」の手順に従う必要があります。 次の手順に従います。

1. Customer Journey AnalyticsでAdobe Analytics レポートスイートデータを表示するには、次のいずれかの方法を使用してAdobe Experience Platformにデータを取り込みます。

   >[!NOTE]
   >
   >  WebSDKを使用してデータを取り込む場合、すべてのスキーマフィールドを手動でマッピングする必要があります。 （マッピングプロセスについて詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行](/help/admin/tools/component-migration/component-migration.md)を参照してください）


   * Adobe Analytics ソースコネクタを使用するには、次の操作が必要です。

      1. [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むレポートスイートを設定する](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=ja#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [データの収集と活用](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ja)

   * WebSDKを使用するには、次のことが必要です。

      1. [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むレポートスイートを設定する](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=ja#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Adobe Experience Platform Web SDKを介したデータの取り込み](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html?lang=ja)

1. 取り込んだデータを使用して、[接続](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=ja)と[&#x200B; データビュー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja)を作成します。

1. Customer Journey Analyticsのユーザーが、データをマッピングするデータビューにプロビジョニングされていることを確認します。

   詳しくは、[Customer Journey Analytics アクセス制御](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=ja)のAdmin Console[&#128279;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=ja#customer-journey-analytics-permissions-in-admin-console)のCustomer Journey Analytics権限を参照してください。

   「権限」タブは、Admin Consoleの各製品プロファイルの一部です。 特定の製品プロファイルにユーザーを追加できます。 次に、特定のデータビューに権限を割り当て、製品プロファイル内のユーザーがどの権限を持っているかを指定します。

1. 組織として、コンポーネントのマッピング方法を決める。

   詳細については、以下の「[組織として決定する](#decide-as-an-organization-how-you-will-map-components)」の節を参照してください。

## 移行に含まれるものを理解する

次の表は、移行に含まれるプロジェクトとコンポーネントの要素の概要を示しています。

### 移行されるコンポーネント要素

ディメンションと指標は、[Adobe Analytics プロジェクトをCustomer Journey Analyticsに移行](#migrate-adobe-analytics-projects-to-customer-journey-analytics)で説明されているマッピングプロセスの一部として移行されます。

Customer Journey Analyticsにまだ存在しないセグメント、日付範囲、計算指標は、マッピングされたディメンションと指標に基づいて、そこで再作成されます。

|  | 移行済み |
|---------|---------|
| **[所有者](/help/components/calculated-metrics/workflow/cm-manager.md)** | ディメンションと指標：いいえ<p>セグメントと日付範囲：![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共有](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | ディメンションと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |
| **[説明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | ディメンションと指標：いいえ<p>セグメントと日付範囲：![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg)</p> |
| **[タグ](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | ディメンションと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |
| **[属性（ディメンション上）](/help/analyze/analysis-workspace/attribution/overview.md)** | ディメンションと指標：いいえ<p>セグメントと日付範囲：いいえ</p> |

{style="table-layout:auto"}

### 移行されるプロジェクト要素

|  | 移行済み |
|---------|----------|
| **[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[セグメント](/help/components/segmentation/seg-overview.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[ディメンション](/help/components/dimensions/overview.md)** | 自動または手動でマッピングされた![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[指標](/help/components/metrics/overview.md)** | 自動または手動でマッピングされた![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[パネル](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg)移行を行うユーザーによって定義されました |
| **[キュレーション](/help/analyze/analysis-workspace/curate-share/curate.md)** | いいえ |
| **[共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | いいえ |
| **[注釈](/help/analyze/analysis-workspace/components/annotations/overview.md)** | いいえ |
| **[フォルダー構造](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | いいえ |
| **[説明](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |
| **[タグ](/help/analyze/landing.md)** | いいえ |
| **[お気に入り](/help/analyze/landing.md)** | いいえ |
| **[スケジュール](/help/components/scheduled-projects-manager.md)** | いいえ |
| **[異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![&#x200B; チェックマーク &#x200B;](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## エラーの原因となるサポートされていない要素を理解する

次のビジュアライゼーションとパネルは、Customer Journey Analyticsではサポートされていません。 これらの要素が移行前にプロジェクトに含まれている場合、移行が失敗するか、プロジェクトの移行後にエラーが発生する可能性があります。

Customer Journey Analyticsにプロジェクトを移行する前に、Adobe Analytics プロジェクトからこれらの要素を削除します。 移行に失敗した場合は、移行を再試行する前に、これらの要素を削除してください。

### サポートされていないパネル

* [Analytics for Target（A4T）](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [メディア分平均オーディエンス](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [次または前の項目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [ページの概要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [貢献度分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## 組織として、どのようにコンポーネントをマッピングするか決める

>[!NOTE]
>
>移行プロセスでは、Customer Journey Analyticsのコンポーネントに自動的にマッピングできないAdobe Analytics プロジェクト内のコンポーネントを特定し、手動でマッピングできます。
>
>**1つのプロジェクトで行われたマッピングは、どのユーザーが移行を実行しているかに関係なく、IMS組織全体のすべての今後のプロジェクトに適用されます。 これらのマッピングは、今後のプロジェクトを移行する際に更新できます。**
>
>プロジェクトを移行する前に、ディメンションと指標をどのようにマッピングするかを決定することが重要です。 これにより、個々の管理者が、単一のプロジェクトのみを検討する際に、それぞれの判断が分断されるのを防ぐことができます。
>
>次に、プロジェクトにディメンションと指標が存在する場合に、手動でマッピングする必要があるディメンションと指標のリストを示します。 移行前にこのリストを確認することをお勧めします。 これらのコンポーネントのいずれかがプロジェクトに存在する場合は、それらをマッピングするCustomer Journey Analytics コンポーネントを決定します。


### 手動でマッピングする必要があるディメンション

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* 期間
* カテゴリ
* connectiontype
* 顧客の忠誠度
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
* persistentCookie
* 返品頻度
* searchenginenatural
* searchenginenaturalkeyword
* 携帯電話会社
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### 手動でマッピングする必要がある指標

* timespentvisit
* timespentvisitor
* リロード
* バウンス
* バウンス
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisits
* 訪問者ホームページ
* visitorsmcvisid
* pagesnotfound
* newengagements
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* デバイス
* 推定人物
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression
