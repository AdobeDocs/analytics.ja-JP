---
description: 必要システム構成と、Analysis Workspace、Report Builder、Data Warehouse、Data Workbench の比較
title: Analytics 製品の比較と必要システム構成
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: af53ada8-1b7d-4929-ac91-ac971dd20ec7id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: dcae653e-62c6-4cc8-84e6-ee110b848296id: e9cb007b-c8b7-4975-bc81-11a788c535faid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

---

# Analytics 製品の比較と必要システム構成

このページでは、Adobe Analytics の各種製品（Analysis Workspace、Report Builder、Data Warehouse、データフィード、および Analytics API 2.0）の比較を示します。

使用すべき Adobe Analytics 製品について詳しくは、[使用する Adobe Analytics ツールの検討](/help/analyze/get-started/which-analytics-tool.md)を参照してください。

| 製品名とヘルプリンク | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [データフィード](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **アクセス方法** | [ブラウザー](/help/analyze/get-started/sys-reqs.md) | [Windows 用 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | ブラウザーを使用してセットアップします。 [詳細情報](/help/analyze/get-started/sys-reqs.md) | ブラウザーを使用してセットアップします。 [詳細情報](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API ツール。 Adobe Developer の資格情報でログインします。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **データの精度** | 集計 | 集計 | 集計 | ヒット | 集計 |
| **Experience Cloud ID（ECID）が使用可能** | いいえ | いいえ | はい | はい | いいえ |
| **タイムスタンプが使用可能** | いいえ | いいえ | いいえ | はい | いいえ |
| **処理レベル** | 完全処理 | 完全処理済みで、個別の[リアルタイムレポートを使用](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) | 完全処理 | 完全処理 | 完全処理 |
| **管理ボットフィルタデータを含む** <br> [詳細情報](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | × | ○（個別のボットレポート） | いいえ | いいえ | いいえ |
| **トラフィックが少ない（ユニークが超過しました）** <br> [詳細情報](/help/technotes/low-traffic.md) | はい | はい | いいえ | いいえ | はい |
| **表示される行数制限（ページ分割前）** | 400 | 50000 | 制限なし | 制限なし | 50000 |
| **複数のレポートスイート** | [○](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | はい | いいえ | はい | いいえ |
| **分類の数** | 制限なし | ～ 2 | 制限なし | 制限なし | 制限なし（複数のクエリに対して実行） |
| **セグメント化** <br> [詳細情報](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | はい | はい | ○（[制限あり](/help/components/segmentation/seg-reference/seg-compatibility.md)） | いいえ | はい |
| **計算指標** <br> [詳細情報](/help/components/calculated-metrics/cm-overview.md) | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） | ○（Attribution あり） | はい | いいえ | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） |
| **マーケティングチャネル** <br> [詳細情報](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | はい | はい | はい | ○ — [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | ○ |
| **コホート分析** | [○](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | はい | いいえ | いいえ | いいえ |
| **アトリビューション** | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） | 制限あり | いいえ | いいえ | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） |
| **キュレーション** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/curate.md) | ○ - プロジェクトおよび仮想レポートスイート | いいえ | いいえ | いいえ | ○ - 仮想レポートスイートのみ |
| **プロジェクトの共有** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md) | はい（プロジェクトロールあり） | はい | いいえ | いいえ | いいえ |
| **配信予定** | はい | はい | はい | はい | いいえ |
| **配信先** | 電子メール | 電子メール、FTP、SFTP、[Microsoft PowerBI への公開](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC、メール | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform | - |
| **仮想レポートスイートのレポート時間処理** <br> [詳細情報](/help/components/vrs/vrs-report-time-processing.md) | はい | いいえ | いいえ | いいえ | はい |
| **地域および技術レポート** | はい <p>post フィールドではなくmid値を使用します。 訪問の最初のヒット ロジックは、`visit_page_num=1`ではなく`post_cust_hit_time_gmt`に基づいています。 訪問中にIPが変更されたり、ヒットが予定外に到着したり、月の枠を超えて訪問したりすると、結果が他のツールとは異なる場合があります。</p> | はい <p>post フィールドではなくmid値を使用します。 訪問の最初のヒット ロジックは、`visit_page_num=1`ではなく`post_cust_hit_time_gmt`に基づいています。 訪問中にIPが変更されたり、ヒットが予定外に到着したり、月の枠を超えて訪問したりすると、結果が他のツールとは異なる場合があります。</p> | はい <p>post値と`visit_page_num=1`を使用して、訪問の最初のヒットを判断します。 これらのディメンションに対して、最初のヒットからの値を、訪問中のすべてのヒットに適用します。</p> | はい <p>post値と`visit_page_num=1`を使用して、訪問の最初のヒットを判断します。 これらのディメンションに対して、最初のヒットからの値を、訪問中のすべてのヒットに適用します。</p> | はい <p>post フィールドではなくmid値を使用します。 訪問の最初のヒット ロジックは、`visit_page_num=1`ではなく`post_cust_hit_time_gmt`に基づいています。 訪問中にIPが変更されたり、ヒットが予定外に到着したり、月の枠を超えて訪問したりすると、結果が他のツールとは異なる場合があります。</p> |
