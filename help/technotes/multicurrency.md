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

Adobeでは、複数のレベルの通貨換算を提供しているので、組織が多くのレポートで目的の通貨を実現できます。 コンバージョンは、次の 3 つのレベルで発生します。

## ページレベル

[`currencyCode`](/help/implement/vars/config-vars/currencycode.md) 変数を使用して、各ページに目的の通貨を設定できます。 ページ上の通貨が宛先レポートスイートの通貨と一致しない場合、Adobeは本日の為替レートに基づいてレポートスイートの通貨に通貨換算を行います。 換算された通貨が記録されます。

## レポートスイートレベル

すべてのレポートスイートには **基本通貨** があります。 この通貨は、すべての通貨指標のコンテキストを示します（例：[&#x200B; 売上高 &#x200B;](/help/components/metrics/revenue.md)）。 保存されるすべての通貨データは、レポートスイートの基本通貨に基づいています。

