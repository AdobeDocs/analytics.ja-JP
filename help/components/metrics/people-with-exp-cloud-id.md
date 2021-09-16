---
title: Experience Cloud ID を持つ個人
description: クロスデバイス分析で、デバイスIDを持つ人の数です。
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# Experience Cloud ID を持つ個人

「Experience CloudIDを持つユーザー」は[クロスデバイス分析](../cda/overview.md)指標で、[Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してAdobeによって識別された[ユーザー](people.md)の数を示します。

## この指標の計算方法

[People](people.md)（識別済みまたは未識別）のそれぞれを考慮すると、この指標は、ヒットに`mid`クエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) cookieに基づく）が含まれている場合に増加します。

IDサービスを使用して、計算指標`[People with ECID] ÷ [People]`を作成し、サイトへの訪問者の割合を取得できます。

Experience CloudIDの重要性と設定のデバッグについて詳しくは、CDA以外の同等の指標[Experience CloudID](visitors-with-ecid.md)の訪問者を参照してください。
