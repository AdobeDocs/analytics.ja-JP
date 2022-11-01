---
description: 複数通貨のサポートを有効にするためにターゲット通貨コードを定義する方法について説明します。
title: 複数通貨のサポート
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 複数通貨のサポート

Adobeでは、複数のレベルの通貨換算が可能なので、多くのレポートで目的の通貨を達成できます。 コンバージョンは次の 3 つのレベルで発生します。

## ページレベル

以下を使用して、 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 変数を使用して、各ページに目的の通貨を設定します。 ページ上の通貨が送信先レポートスイートの通貨と一致しない場合、Adobeは現在の日の為替レートに基づいてレポートスイートの通貨に換算します。 換算後の通貨が記録されます。

## レポートスイートレベル

すべてのレポートスイートに **基準通貨**. この通貨は、すべての通貨指標のコンテキストを示します ( 例： [売上高](/help/components/metrics/revenue.md)) をクリックします。 保存される通貨データはすべて、レポートスイートのベース通貨に基づきます。

## ユーザーレベル

Reports &amp; Analytics の場合、ユーザーは、 [レポート設定](/help/analyze/reports-analytics/report-settings.md). この設定は非破壊的で、基になるデータは変更されません。 代わりに、今日の為替レートに基づいて表示されるすべてのレポートに、基本的な通貨換算が適用されます。 同じレポートを異なる日に表示する場合、日別の為替レートが異なるので、数が変わる可能性があります。

Analysis Workspaceでは現在、ユーザーレベルの通貨換算は提供されていません。
