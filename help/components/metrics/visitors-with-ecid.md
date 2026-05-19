---
title: Experience Cloud ID を持つ訪問者
description: Adobe Experience Cloud ID サービスを使用しているユニーク訪問者の数です。
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 76%

---

# Experience Cloud ID を持つ訪問者

「Experience Cloud IDを持つ訪問者」の[指標](overview.md)は、[Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してAdobeによって識別された一意の訪問者の数を示します。 この指標は、[ユニーク訪問者](unique-visitors.md)指標と比較して、サイトへの訪問者の大半が ID サービスを使用していることを確認するのに役立ちます。 訪問者の大部分が ID サービス cookie を使用していない場合は、実装内の問題を示している可能性があります。

>[!NOTE]
>
>この指標は、Adobe TargetやAdobe Audience Managerなど、複数のCX Enterprise サービスを使用する場合のデバッグに特に重要です。 CX Enterprise製品間で共有されるセグメントには、Experience Cloud IDのない訪問者は含まれません。

## この指標の計算方法

この指標は、[ユニーク訪問者](unique-visitors.md)指標に基づきますが、`mid` クエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) cookie に基づく）を使用して識別された個人のみが含まれます。

## Experience Cloud ID 設定のデバッグ

「Experience Cloud IDを持つ訪問者」指標は、CX Enterprise統合のトラブルシューティングや、ID サービスがデプロイされていないサイトの領域の特定に役立ちます。

「Experience Cloud ID を持つ訪問者」をユニーク訪問者と並べてドラッグして比較します。

![ユニーク訪問者の比較](assets/metric-mcvid1.png)

この例では、各ページのユニーク訪問者が Experience Cloud ID での訪問者と同じ数になっていることに注意してください。 ただし、ユニーク訪問者の合計数は Experience Cloud ID での訪問者の合計数より大きくなっています。 ID サービスが設定されていないページを調べる[計算指標](../calculated-metrics/cm-overview.md)を作成できます。 次の定義を使用できます。

![計算指標の定義](assets/metric-mcvid2.png)

この計算指標をレポートに追加することで、MCID を持たない訪問者の数が最も多いページがひとめでわかるように、ページレポートをソートすることができます。

![ID サービスを使用しないページ](assets/metric-mcvid3.png)

「製品クイックビュー」ディメンション項目は、ID サービスでは正しく実装されないことに注意してください。 組織内の適切なチームと協力して、これらのページを可能な限り早く更新できます。 [ブラウザーのタイプ](../dimensions/browser-type.md)、[サイトセクション](../dimensions/site-section.md)、[eVar](../dimensions/evar.md) など、あらゆるタイプのディメンションを使用して、類似したレポートを作成できます。
