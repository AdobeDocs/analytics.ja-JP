---
title: クロスデバイス訪問者特定に関する FAQ
description: クロスデバイス訪問者特定に関するよくある質問（FAQ）
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: 'https://experienceleague.adobe.com/RBciiyfaq671zJ51QdJJDXcekFr-lfq0WPY0UAuWoVA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# クロスデバイス訪問者特定に関する FAQ

クロスデバイス訪問者特定に関するよくある質問です。

+++クロスデバイス訪問者特定とクロスデバイス分析の違いは何ですか？
クロスデバイス訪問者特定では、`visitorID` 変数を使用してデバイスを結び付けますが、いくつかの大きな制限があります。 この識別方法の最も大きな制限の 1 つは、デバイスが既に認識されていない限り、未認証のヒットが分離されることです。 これらの未認証ヒットは、ユニーク訪問者数を水増しする可能性があります。

クロスデバイス分析は、アドビの最新のクロスデバイス訪問者特定方法です。 Experience Cloud ID サービスとフィールドベースのステッチングを利用して、さまざまなデバイスからの訪問をさかのぼって結合できます。 CDA は、同じ訪問者が使用するデバイスを判断するために `setCustomerIDs` 関数を使用する必要があります。
+++

+++クロスデバイス訪問者特定は、セグメントをどのように処理しますか？
クロスデバイス訪問者特定では、セグメントを他の機能と同様に扱います。 各ヒットを調べて、セグメント条件に一致するかどうかを確認し、一致する場合はそのヒットをデータに含めます。 訪問および訪問者ベースのコンテナを使用するセグメントは、引き続き訪問者 ID を調べます。 セグメント化のためにユニーク訪問者を一貫して識別するには、可能な限り `visitorID` 変数を使用してください。
+++
