---
description: Adobe AnalyticsとAudience Managerはどちらもセグメントを利用しています。 ただし、Analytics セグメントは、Audience Manager セグメントとまったく同じではありません。 これらの違いは、AnalyticsとAudience Manager レポートに表示される不一致に一因します。 そのため、両方のソリューションでセグメントを扱う際には、これらの違いを理解し、実践することが重要です。
title: Analytics と Audience Manager のセグメントについて
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
TQID: 'https://experienceleague.adobe.com/RjKoKg5fyxSwXNSQRCGHhJQcfjkwLIrVsKDBCFpJ5Ac'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: a97e0d8c-238a-47ee-8d81-16bd45309bed
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 747
ht-degree: 12%

---

# Analytics と Audience Manager のセグメントについて

Adobe AnalyticsとAudience Managerはどちらもセグメントを利用しています。 ただし、Analytics セグメントは、Audience Manager セグメントとまったく同じではありません。 これらの違いは、AnalyticsとAudience Manager レポートに表示される不一致に一因します。 そのため、両方のソリューションでセグメントを扱う際には、これらの違いを理解し、実践することが重要です。

## Audience Manager セグメント {#aam-segments}

Audience Manager セグメントは、論理ルールによって結合された定義済み特性のセットに適格な訪問者のグループ（ユーザーID）です。 Audience Managerのセグメントに訪問者（ユーザーID）が含まれているかどうかを判断する基準は4つあります。

* セグメント自体と各セグメントを構成する特性に設定されたルール。 これらのルールは、ユーザーIDがセグメントの選定に必要な条件または条件を定義します。
* アルゴリズムモデリング。 特定のセグメントに適格である利用者は、アルゴリズムによるモデリングと分析にもとづいて、他のセグメントにも適格となる場合があります。
* TTL （Time-to-Live）インターバル： セグメントメンバーシップは、設定された間隔で失効するか、無期限に継続できます。
* 最新性と頻度： 利用者がいつ、どれくらいの頻度でやり取りしているのかを定義することで、サイト、セクション、特定のクリエイティブに対する関心の高さにもとづいて、セグメントを作成することができます。

Audience Managerのセグメントメンバーシップは流動的です。 利用者は、現在の時点でセグメント基準に適格であるかどうかに応じて、セグメントにエントリするかセグメントから離脱します。 つまり、Audience Managerセグメントの母集団は、時間の経過とともに増加または減少する可能性があります。

Analyticsでは、Audience Manager セグメントはオーディエンスとして表されます。

詳細については、[&#x200B; セグメントビルダーの特性データとセグメント母集団データ &#x200B;](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja)および[信号、特性、セグメント &#x200B;](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=ja)を参照してください。

## Analytics セグメント {#analytics-segments}

Analytics セグメントは、レポート内のデータをフィルタリングするメカニズムです。 フィルタリングは、Audience Manager のように訪問者レベルのみではなく、訪問者、訪問またはヒットのレベルでおこなうことができます。 Analytics セグメントとAudience Manager セグメントを比較する際に考慮すべき重要な要素がいくつかあります。

* Adobe Analyticsのセグメントは、Audience Managerのセグメントとは異なるデータセットを使用します。 データの収集時に、Analyticsは、Audience Managerで使用できないデータに対して様々な後処理ステップを適用します。 後処理には、eVarの永続性、処理ルール、ルックアップ（位置情報、モバイルデバイス）、VISTAなど、様々な要素が含まれます。 Audience Managerは、サーバーサイド転送（またはDIL）を通じて前処理されたデータを受け取ります。

  Analyticsで期限切れにならないディメンションに基づいてセグメントをAudience Managerで同じディメンションと比較する場合、データの不一致が発生します。 例えば、listVarsやマーチャンダイジングのeVarの有効期限はありません。

  例えば、eVar = blue で、期限切れになることがないと Analytics で設定されている場合、条件「eVar = blue」を持つ Analytics のセグメントには常にこの訪問者が含まれます。 一方、Audience Managerでは、一定期間が経過すると、その訪問者が同様に定義されたセグメントからフォールアウトする可能性があります。

* Adobe Analyticsのセグメントは、Adobe Adobe Audience Managerのセグメントよりも多くの機能を備えています。 Audience Managerセグメントは常に訪問者レベルで評価されます。 分析セグメントは、訪問者、訪問、またはヒットレベル（またはこれらのレベルの組み合わせ）で定義できます。 さらに、Adobe Analyticsは、シーケンシャルセグメンテーションなど、Audience Managerにはない高度なセグメンテーション機能にも対応しています。

* 前述したように、Audience Managerの訪問者は、現在の時点でセグメント基準に適格であるかどうかに応じて、セグメントにエントリするか、セグメントから脱落するかを選択できます。

  一方、Analyticsでは、レポートの日付範囲に基づいて、訪問者がセグメントに含まれるか、セグメントから除外されます。 例えば、ある訪問者が先月購入したとします。 Adobe Audience Managerでは、日付範囲に関係なく、その訪問者は「購入者」セグメントに含まれます。 Analyticsでは、今月に基づくレポートには、訪問者はセグメントに含まれません。 ただし、今月と先月に基づくレポートでは、訪問者がセグメントに含まれます。

詳しくは、[Analytics セグメント化ガイド &#x200B;](/help/components/segmentation/seg-home.md)を参照してください。
