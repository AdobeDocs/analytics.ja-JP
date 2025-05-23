---
description: 複数のスイートタグ付けを実装し、イメージリクエストを複数のレポートスイートに送信する方法を説明します。
title: 複数のスイートタグ付けの実装
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 93%

---

# 複数のスイートタグ付けの実装

[複数のスイートタグ付け](/help/admin/admin/c-manage-report-suites/rollup-report-suite.md)を使用すると、イメージリクエストをグローバルレポートスイートだけでなく個々の子レポートスイートに送信して、会社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます。

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

仮想レポートスイートが最適なアプローチかどうかを理解するには、 [仮想レポートスイートと複数のスイートタグ付けに関する考慮事項](/help/components/vrs/vrs-considerations.md) を参照してください。複数のスイートタグ付けと仮想レポートスイートの機能の比較については [&#128279;](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78) 仮想レポートスイートと，複数のスイートタグ付けの比較」も参照してください。
