---
title: Adobe Analytics データのサードパーティ製品との比較
description: Adobe Analytics のデータを他の Analytics ソリューションで収集されたデータと直接比較する場合のオプションを理解します。
feature: Third-party Integration
exl-id: b4f85088-7ffd-45dc-bdd1-c0fc8dc3b332
TQID: 'https://experienceleague.adobe.com/I-zMxnrvOOk3NUjeQFbcrIq0nAPO6AAaO0eznskChgQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: a60fda7a-bb0b-4eb6-b9fe-77558cbee1fa
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 88%

---

# Adobe Analytics データのサードパーティ製品との比較

オンラインでは多くの分析ソリューションを利用できます。 これらの各ソリューションは、独自のメソッドを使用してコードを実装し、データを収集します。 各製品で使用されるページ表示、訪問、ユニーク訪問者、その他の指標は、それぞれ独自に定義されます。

これらの定義、データ構造、実装は大幅に異なるため、 **Adobe カスタマーケアは、サードパーティの分析ツールとの不一致のトラブルシューティングをおこないません。**

Adobe Analytics とサードパーティの分析ツールの間に大きな相違がある場合は、以下のリソースを利用できます。

* **デバッガを使用した自己監査**：サイト上のページは、[Adobe のデバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)または他のパケット監視で確認できます。 デバッガーを使用すると、実装を検証し、イメージリクエストが適切な変数で正しく実行されていることを確認できます。
* **データフィードを使用した自己監査**：Adobe は、1 日のすべての生データを含む[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)を受信するオプションを組織に提供します。 その後、組織でこのデータを使用して、サードパーティの分析ツールと比較し、不一致があるかどうかを判断できます。
* **Adobe Consultingを使用した監査とデータ検証の支援**:Adobeの公式担当者にサイトの完全な実装監査を実施してもらいたい場合は、Adobe アカウントチームにお問い合わせください。 アカウントマネージャーは実装コンサルタントとのミーティングを設定し、実装コンサルタントが会社の契約に基づいてサイトを監査できます。
