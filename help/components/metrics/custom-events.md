---
title: カスタムイベント
description: カスタムイベントが存在するヒットの数。
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 83%

---

# カスタムイベント

*このヘルプページでは、カスタムイベントが指標としてどのように機能するかを説明します。実装変数としてのカスタムイベントの機能について詳しくは、『導入ユーザガイド』の「[イベントの概要](/help/implement/vars/page-vars/events/events-overview.md)」を参照してください。*

カスタムイベント [ 指標 ](overview.md) は、イメージリクエストで特定のカスタムイベントが設定されたヒット数を表示します。 これらの指標は、各組織に固有のイベントに対する洞察を提供するので、多くの実装にとって重要です。

## この指標の計算方法

カスタムイベントの計算方法は、タイプに応じて異なります。レポートスイート設定の「[成功イベント](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)」で、イベントのタイプを確認できます。

* **カウンターイベント**：デフォルトのイベント設定です。ほとんどのイベントはカウンターイベントです。一致するカスタムイベント `event1` — `event1000` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒットの数をカウントします。
* **数値イベント**：`events` 変数内のイベントに割り当てられた数値を合計します。
* **通貨イベント**：その日の為替レートに対して通貨換算を適用し、`events` 変数の各ヒットに割り当てられた数値を合計します。

使用可能なイベントの数は、組織の Analytics 契約によって異なります。レガシー契約以外の組織のほとんどは、1,000 件のカスタムイベントを利用できます。使用できるカスタムイベントの数が不明な場合は、Adobeアカウントチームにお問い合わせください。

組織の[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)で各イベントの使用方法を記録することを強くお勧めします。
