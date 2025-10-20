---
title: Adobe Analyticsの訪問者 ID サービス移行に関する考慮事項
description: Adobe Analyticsと訪問者 ID サービスのインターフェイスの概要です。
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Adobe Analyticsの訪問者 ID サービス移行に関する考慮事項

組織が、既存の Analytics 実装を使用して訪問者 ID サービスへの移行を計画している場合は、考慮すべき重要なトピックがいくつかあります。 訪問者の識別の整合性を維持し、既存の Analytics 実装が存在する場合に ID サービスがどのように動作するかを理解するには、これらの考慮事項が重要です。

## 訪問者 ID サービスと従来の Analytics 訪問者 Cookie のインターフェイス

AppMeasurementには訪問者を識別する独自の方法があるので、組織が訪問者 ID サービスをデプロイすると、一部の訪問者は従来の Analytics Cookie を使用する場合があります。 様々な状況下で訪問者がどのように識別されるかを次に示します。

* **訪問者 Cookie がありません**:ID サービスがExperience Cloud ID （`mid`）を割り当てます。
* **`s_vi` Cookie が存在する**:ID サービスは、Experience Cloud ID （`aid`）に加えて、既存の従来の Analytics ID （`AMCV`）を `mid` Cookie に書き込みます。 `aid` は [&#x200B; 操作の順序 &#x200B;](overview.md) が上位にあるので、`AMCV` の Cookie の有効期限が切れるかクリアされるまで、従来の Analytics ID が訪問者 ID になります。 猶予期間が有効になっている場合、ID サービスは応答に `mid` と `aid` の両方を含めます。
* **フォールバック cookie が存在する**:ID サービスは、フォールバック cookie （`fid`）を `AMCV` cookie に書き込みません。 代わりに、訪問者は、新規訪問者であるかのようにExperience Cloud ID （`mid`）を受け取ります。

## 訪問者 ID サービスの猶予期間

同じレポートスイートにデータを送信する実装が複数あり、一部の実装でのみ訪問者 ID サービスを実装できる場合、Adobeでは猶予期間を設定することをお勧めします。 例えば、サイトのサポートセクションが別のタグ付けソリューションで管理されている場合、訪問者 ID サービスをサポートセクションの前のサイトの残りの部分にデプロイすることができます。 猶予期間がないと、サポートセクションを表示する新規訪問者に従来の Analytics 訪問者 ID が与えられるので、2 人の異なる訪問者がカウントされます。 猶予期間が設定されている場合、訪問者 ID サービスはExperience Cloud ID （`mid`）と従来の Analytics 訪問者 ID （`aid`）の両方を発行するので、ID サービスのないサイトの領域で訪問者の識別の一貫性が保たれます。

サイトのすべてのエリアにわたって訪問者 ID サービスのデプロイメントを調整する場合は、猶予期間は必要ありません。 猶予期間を設定するには、[Adobe カスタマーケア &#x200B;](https://helpx.adobe.com/jp/marketing-cloud/contact-support.html) にお問い合わせください。

## クロスドメイントラッキング

一部の従来の Analytics 訪問者 ID 実装では、「わかりやすいサードパーティ Cookie」を使用する場合があります。このような場合、2 つのドメインが `data.example.com` のような共通のドメインで同じ訪問者 Cookie を共有します。 フレンドリ Cookie は依然としてサードパーティ Cookie なので、多くの最新のブラウザーはそれらを拒否し、Analytics が訪問者の識別にフォールバック ID （`fid`）に依存する原因となります。 ID サービスに移行すると、すべてのドメインがファーストパーティコンテキストで `AMCV` Cookie を設定できるようになり、訪問者 ID を保持する能力が向上します。

訪問者 ID サービスは、クロスドメイントラッキング用のサードパーティ Cookie （[`demdex` Cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)）を設定しようとしますが、多くの場合、最新のブラウザーによって拒否されます。 [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) メソッドを使用して、所有するドメイン間で訪問者のExperience Cloud ID （`mid`）を渡すことを検討してください。

## サーバーサイドトラッキング

[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) を呼び出してExperience Cloud ID （`mid`）を取得し、[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) を呼び出して従来の Analytics ID （`aid`）を取得できます。 Adobeでは、訪問者特定ロジックを保持するために、両方のを確認することをお勧めします。
