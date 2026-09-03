---
title: Experience Cloud ID を持つ個人
description: クロスデバイス分析で、Experience Cloud ID を持つ人の数です。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 58%

---

# Experience Cloud ID を持つ個人

「Experience Cloud IDを持つユーザー」は、[訪問者ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home)または[Experience Platform ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)を使用してAdobeによって識別された[&#x200B; ユーザー](people.md)の数を示す[&#x200B; クロスデバイス分析](../cda/overview.md)指標です。

## この指標の計算方法

各[&#x200B; ユーザー](people.md) （識別または未識別）を考慮すると、ヒットに`mid`個のクエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieに基づく）が含まれている場合、この[指標](overview.md)は増加します。

計算指標 `[People with ECID] ÷ [People]` を作成し、ID サービスを使用してサイトへの訪問者の割合を取得できます。

Experience Cloud ID の重要性と設定のデバッグについて詳しくは、CDA 以外の同等の指標「[Experience Cloud ID を持つ訪問者](visitors-with-ecid.md)」を参照してください。
