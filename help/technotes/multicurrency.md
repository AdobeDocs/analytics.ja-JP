---
description: 複数通貨のサポートを有効にするためにターゲット通貨コードを定義する方法について説明します。
title: 複数通貨のサポート
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# 複数通貨のサポート

Adobeでは、複数のレベルの通貨換算が可能なので、多くのレポートで目的の通貨を達成できます。 コンバージョンは次の 3 つのレベルで発生します。

## ページレベル

以下を使用すると、 [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 変数を使用して、各ページに目的の通貨を設定します。 ページ上の通貨が送信先レポートスイートの通貨と一致しない場合、Adobeは現在の日の為替レートに基づいてレポートスイートの通貨に換算します。 換算後の通貨が記録されます。

## レポートスイートレベル

すべてのレポートスイートに **基準通貨**. この通貨は、すべての通貨指標のコンテキストを示します ( 例： [売上高](/help/components/metrics/revenue.md)) をクリックします。 保存される通貨データはすべて、レポートスイートのベース通貨に基づきます。

