---
title: カスタムイベント
description: カスタムイベントが存在するヒットの数。
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 91%

---

# カスタムイベント

*このヘルプページでは、カスタムイベントが指標としてどのように機能するかを説明します。 実装変数としてのカスタムイベントの機能について詳しくは、『導入ユーザガイド』の「[イベントの概要](/help/implement/vars/page-vars/events/events-overview.md)」を参照してください。*

カスタムイベント [指標](overview.md)には、特定のカスタムイベントがイメージリクエストで設定されたヒット数が表示されます。 これらの指標は、各組織に固有のイベントに対する洞察を提供するので、多くの実装にとって重要です。

## この指標の計算方法

カスタムイベントの計算方法は、タイプに応じて異なります。 レポートスイート設定の「[成功イベント](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)」で、イベントのタイプを確認できます。

* **カウンターイベント**：デフォルトのイベント設定です。 ほとんどのイベントはカウンターイベントです。 一致するカスタムイベント `event1` — `event1000` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒットの数をカウントします。
* **数値イベント**：`events` 変数内のイベントに割り当てられた数値を合計します。
* **通貨イベント**：その日の為替レートに対して通貨換算を適用し、`events` 変数の各ヒットに割り当てられた数値を合計します。

使用可能なイベントの数は、組織の Analytics 契約によって異なります。 レガシー契約以外の組織のほとんどは、1,000 件のカスタムイベントを利用できます。 利用可能なカスタムイベントの数が不明な場合は、アドビのアカウントチームにお問い合わせください。

組織の[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)で各イベントの使用方法を記録することを強くお勧めします。
