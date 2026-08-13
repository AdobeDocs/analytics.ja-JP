---
title: Adobe Analyticsの訪問者ID サービスの移行に関する考慮事項
description: Adobe AnalyticsとVisitor ID サービスのインターフェイスの概要。
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 2%

---

# Adobe Analyticsの訪問者ID サービスの移行に関する考慮事項

既存のAnalytics実装を使用して訪問者ID サービスに移行する場合は、考慮すべき重要なトピックがいくつかあります。 これらの考慮事項により、訪問者IDの整合性を維持し、既存のAnalytics実装の存在下で訪問者ID サービスがどのように動作するかを理解できます。

>[!TIP]
>
>このページは、既存のAppMeasurementまたはAnalytics拡張機能の実装にのみ適用され、訪問者ID サービスを追加するか、Web SDKの実装にアップグレードしています。 言い換えれば、実装は従来のAnalytics ID （`aid`）を使用し、ECID （`mid`）の使用に向かって進んでいます。 すべてのWeb SDKの実装では、デフォルトでECID （`mid`）を使用する[Experience Platform Identity Service](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)が使用されます。

## 訪問者ID サービスと従来のAnalytics訪問者Cookieのインターフェイス

AppMeasurementには、訪問者を識別する独自のレガシーメソッドがあるため、組織が訪問者ID サービスをデプロイする際に、既存のAnalytics Cookieを持つ訪問者が存在する場合があります。 次のリストは、様々な状況で訪問者がどのように識別されるかを示しています。

* **訪問者Cookieがありません**：訪問者ID サービスはECID （`mid`）を割り当てます。
* **`s_vi` Cookieが存在します**：訪問者ID サービスは、ECID （`mid`）に加えて、既存の従来のAnalytics ID （`aid`）を`AMCV` Cookieに書き込みます。 `aid`は[操作の順序](overview.md)で上位に表示されるため、従来のAnalytics IDは、`AMCV` Cookieが期限切れになるか消去されるまで、訪問者IDになります。 猶予期間が有効になっている場合、訪問者ID サービスは、応答に`mid`と`aid`の両方を含めます。
* **フォールバッククッキーが存在します**：訪問者ID サービスは、フォールバッククッキー（`fid`）を`AMCV` Cookieに書き込みません。 代わりに、訪問者は新しい訪問者であるかのようにECID （`mid`）を受け取ります。

## 訪問者ID サービス猶予期間

同じレポートスイートにデータを送信する複数の実装があり、一部の実装にのみVisitor ID サービスを実装できる場合は、Adobeでは猶予期間を設定することをお勧めします。 例えば、サイトのサポートセクションが別のタグ付けソリューションによって管理されている場合、サポートセクションの前に訪問者ID サービスがサイトの他の部分にデプロイされている可能性があります。 猶予期間がない場合、サポートセクションを表示する新規訪問者には従来のAnalytics訪問者IDが付与され、2人の個別の訪問者がカウントされます。 猶予期間を設けると、訪問者ID サービスはECID （`mid`）と従来のAnalytics訪問者ID （`aid`）の両方を発行し、訪問者ID サービスのないサイトの領域が訪問者を識別する一貫性を維持できるようにします。

サイトのすべての領域をまたいで訪問者ID サービスのデプロイメントを調整する場合は、猶予期間は必要ありません。 猶予期間を設定するには、[Adobe カスタマーケア ](https://helpx.adobe.com/jp/marketing-cloud/contact-support.html)にお問い合わせください。 猶予期間は最大180日間まで設定でき、更新できます。 Adobeでは、プロパティ全体で訪問者ID サービスを使用するように設定した後、猶予期間を終了することをお勧めします。

## クロスドメインにわたる追跡

一部のレガシーAnalytics訪問者ID実装では、「フレンドリーなサードパーティ Cookie」を使用する場合があります。この場合、2つのドメインが`data.example.com`のような共通ドメインで同じ訪問者Cookieを共有します。 フレンドリーなサードパーティ Cookieは引き続きサードパーティ Cookieであるため、多くの最新のブラウザーでは拒否され、Analyticsは訪問者の識別にフォールバック ID （`fid`）に依存します。 訪問者ID サービスに移行すると、すべてのドメインがファーストパーティのコンテキストで`AMCV` Cookieを設定できるようになり、訪問者IDを保持する実行可能性が高まります。

訪問者ID サービスは、クロスドメインのトラッキング用にサードパーティ Cookie （[`demdex` Cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)）を設定しようとしますが、多くの場合、最新のブラウザーによって拒否されます。 所有しているドメイン間で訪問者のECID （`mid`）を渡すために、[`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) メソッドの使用を検討してください。

## サーバーサイドトラッキング

[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)を呼び出してECID （`mid`）を取得し、[`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid)を呼び出して従来のAnalytics ID （`aid`）を取得できます。 Adobeでは、訪問者識別ロジックを保持するために、両方を確認することをお勧めします。
