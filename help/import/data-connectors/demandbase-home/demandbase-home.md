---
description: 'null'
title: Adobe Analytics 用 Demandbase Data Connector
uuid: 28fddb8f-06f6-4447-8257-4a59131bedbe
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 96%

---


# Adobe Analytics 用 Demandbase Data Connector {#demandbase-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>2021年8月1日に、Adobeデータコネクタ技術の提供終了を予定しています。 [詳細情報...](/help/import/data-connectors/data-connectors-eol.md)

この Adobe® Data Connectors の統合は、Demandbase のリアルタイム ID サービスと Adobe Analytics の行動情報を組み合わせて、B2B 組織のために強力な分析、最適化とコンテンツパーソナライゼーションの機会を作り出します。

事前に決定された特性に基づいて、見込み客に合わせてコンテンツを提供すことで、より適格なリードを促してコンバージョン率を向上させます。特定の業界、会社規模、または特定の会社自体に関連するコンテンツを提供すれば、サイトでの結果に依存せずに、適切なメッセージを直接訪問者に届けることができます。これにより、バウンスが減少し、より健全で適格なコンバージョンファネルが増加します。

## 主なメリットと機能 {#key-benefits-and-features}

メリットと機能の上位 5 つを示します。

* 会社名、業種、売上高範囲など、8 つの標準 Demandbase 組織ディメンションに関するトラフィックおよびコンバージョンのレポートを提供します。
* お好きな 8 つのオプション Demandbase ディメンションを追加できます。これには、アカウント監視ディメンションを含めることができます。
* Demandbase ディメンションを使用して Adobe Experience Cloud 全体でセグメントを作成および適用する機能が含まれます。
* レポートスイート変数の最適化を提供します。16 の可能な Demandbase ディメンションはすべて、2 つのカスタムコンバージョン変数（eVar）のみを使用して取得できます。
* 特定のオーディエンスに対するターゲット設定に使用するために、統合 Demandbase ディメンションを Adobe Target に送信できます。

## 統合の前提条件 {#integration-prerequisites}

アドビおよび Demandbase のお客様向けの主な前提条件です。

### アドビのお客様の前提条件 {#section-ce8963ca1c1741009d842222c6a49063}

* Adobe Analytics を現在ご利用中のお客様である。
* Data Connectors を有効にする権限を持つ Adobe Experience Cloud 管理者ユーザーである。
* レポートスイート内で 1 つ以上の eVar 変数が使用可能かつ有効になっている。2番目の eVar はオプションです。

### Demandbase のお客様の前提条件 {#section-08e14afe216a4b0db9e7e2965894de6f}

* Demandbase を現在ご利用中のお客様である。
* Analytics のライセンスを持つ有効な Demandbase API キーを持っている。
* **オプション：**&#x200B;コンテンツのパーソナライゼーションのライセンスを持つ有効な Demandbase API キーが必要です。このキーは、Adobe Target 内で統合 Demandbase ディメンションをアクティブ化する場合にのみ必要です。
