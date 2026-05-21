---
description: 複数通貨のサポートを有効にするためにターゲット通貨コードを定義する方法について説明します。
title: 複数通貨のサポート
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# 複数通貨のサポート

Adobeでは、様々なレベルの通貨コンバージョン機能を提供しています。これにより、多くのレポートで目的の通貨を取得できます。 コンバージョンは、次の3つのレベルで発生します。

## ページレベル

[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)変数を使用して、各ページに目的の通貨を設定できます。 ページ上の通貨が宛先レポートスイートの通貨と一致しない場合、Adobeは、現在の日付の為替レートに基づいて、レポートスイートの通貨に通貨換算を行います。 変換された通貨が記録されます。

## レポートスイートレベル

すべてのレポートスイートには&#x200B;**基本通貨**&#x200B;があります。 この通貨は、すべての通貨指標（[収益](/help/components/metrics/revenue.md)など）のコンテキストを示します。 保存されるすべての通貨データは、レポートスイートの基本通貨に格納されます。

