---
title: Experience Cloud ID を持つ個人
description: クロスデバイス分析で、Experience Cloud ID を持つ人の数です。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 83%

---

# Experience Cloud ID を持つ個人

「Experience Cloud ID を持つユーザー」は[クロスデバイス分析](../cda/overview.md)指標で、[Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してアドビが識別した[ユーザー](people.md)の数を示します。

## この指標の計算方法

各 [ ユーザー ](people.md) （識別済みまたは未識別）を考慮すると、この [ 指標 ](overview.md) は、ヒットに `mid` のクエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) cookie に基づく）が含まれている場合に増加します。

計算指標 `[People with ECID] ÷ [People]` を作成し、ID サービスを使用してサイトへの訪問者の割合を取得できます。

Experience Cloud ID の重要性と設定のデバッグについて詳しくは、CDA 以外の同等の指標「[Experience Cloud ID を持つ訪問者](visitors-with-ecid.md)」を参照してください。
