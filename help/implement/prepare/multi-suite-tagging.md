---
description: 複数のスイートタグ付けを実装し、イメージリクエストを複数のレポートスイートに送信する方法を説明します。
title: 複数のスイートタグ付けの実装
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/djrzQEjvc--wnh2wR1HNV-LVEn6RPcyiaLKLha5pfSY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 302
ht-degree: 93%

---

# 複数のスイートタグ付けの実装

[複数のスイートタグ付け](/help/admin/tools/manage-rs/rollup-report-suite.md)を使用すると、イメージリクエストをグローバルレポートスイートだけでなく個々の子レポートスイートに送信して、会社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます。

複数のスイートタグ付けを実装するには、eb ページやアプリのトラッキングコードに、グローバルレポートスイートのレポートスイート ID（RSID）と、該当する子レポートスイートの RSID を含める必要があります。

* Adobe Experience Platform のタグ実装の場合、[[!DNL Analytics] 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=ja)の各レポートスイートを指定します。

* レガシー JavaScript およびモバイル SDK を実装する場合、RSID をコンマで区切り、スペースは使用しません（`rsid1,rsid2,rsid3` など）。

* その他の実装タイプの場合は、必要な構文を使用して複数の RSID をリストします。

>[!TIP]
>
> ベストプラクティスとして、最初にグローバルレポートスイートまたはレポートスイート ID をリストすることをお勧めします。

複数のスイートタグ付けには、各イメージリクエストに対して複数のサーバー呼び出しが必要です：グローバルレポートスイートへのプライマリ呼び出しと、各子レポートスイートのセカンダリ呼び出し。

>[!NOTE]
>
> [仮想レポートスイート](/help/components/vrs/vrs-about.md)（会社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます）には、セカンダリサーバー呼び出しは発生しません。

## 複数のスイートタグ付けまたは仮想レポートスイートを実装する必要がありますか？

多くの場合、複数のスイートタグ付けの代わりに仮想レポートスイートを使用することがベストプラクティスですが、ビジネスニーズに応じて組織に最適なレポートスイートアプローチを決定する必要があります。

仮想レポートスイートが最適なアプローチかどうかを理解するには、 [仮想レポートスイートと複数のスイートタグ付けに関する考慮事項](/help/components/vrs/vrs-considerations.md) を参照してください。 マルチスイートタグ付けと仮想レポートスイート機能の比較については、「[仮想レポートスイート vs.、マルチスイートタグ付け](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)」も参照してください。
