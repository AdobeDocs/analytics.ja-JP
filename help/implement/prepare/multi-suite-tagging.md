---
description: 複数のスイートタグ付けを実装し、イメージリクエストを複数のレポートスイートに送信する方法を説明します。
title: 複数のスイートタグ付けの実装
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# 複数のスイートタグ付けの実装

[マルチスイートタギ](/help/admin/c-manage-report-suites/rollup-report-suite.md) ングを使用すると、イメージリクエストをグローバルレポートスイートだけでなく個々の子レポートスイートに送信して、会社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます。

複数のスイートタグ付けを実装するには、Webページやアプリのトラッキングコードに、グローバルレポートスイートのレポートスイートID(RSID)と、該当する子レポートスイートのRSIDを含める必要があります。

* Adobe Experience Platform Launch実装の場合、[[!DNL Analytics] 拡張機能](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)の各レポートスイートを指定します。

* レガシーJavaScriptおよびモバイルSDKを実装する場合、RSIDをコンマで区切り、スペース（`rsid1,rsid2,rsid3`など）は使用しません。

* その他の実装タイプでは、必要な構文を使用して複数のRSIDをリストします。

>[!TIP]
>
> 最初にグローバルレポートスイートまたはレポートスイートIDをリストすることをお勧めします。

マルチスイートタギングには、各イメージリクエストに対して複数のサーバーコールが必要です。グローバルレポートスイートへのプライマリ呼び出しと、各子レポートスイートのセカンダリ呼び出し。

>[!NOTE]
>
> [仮想レポートスイート](/help/components/vrs/vrs-about.md)（会社のグローバルレポートスイートデータのサブセットを様々なエンドユーザーに提供できます）には、セカンダリサーバーコールは発生しません。

## 複数のスイートタグ付けまたは仮想レポートスイートを実装する必要がありますか？

多くの場合、複数のスイートタグ付けの代わりに仮想レポートスイートを使用することがベストプラクティスですが、ビジネスニーズに応じて組織に最適なレポートスイートアプローチを決定する必要があります。

仮想レポートスイートが最適なアプローチかどうかを理解するには、「[仮想レポートスイートと複数のスイートタグ付けに関する考慮事項](/help/components/vrs/vrs-considerations.md)」を参照してください。 複数のスイートタグ付けと仮想レポートスイートの機能の比較については、「[仮想レポートスイートとマルチスイートタグ付け](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)」も参照してください。