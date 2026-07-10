---
title: Experience Cloud ID を持つ訪問者
description: ECIDを使用するユニーク訪問者の数。
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: e6c28e30-8689-4bf4-8fa8-561343d308a9id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 25%

---

# Experience Cloud ID を持つ訪問者

&#39;[!UICONTROL Visitors with Experience Cloud ID]&#39; [指標](overview.md)は、ECIDを持つAdobeによって識別された一意の訪問者の数を示します（[Visitor ID Service](https://experienceleague.adobe.com/ja/docs/id-service/using/home)または[Experience Platform ID Service](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home)を使用）。 この指標は、[ ユニーク訪問者](unique-visitors.md)指標と比較して、サイトへの訪問者の大半がECIDを使用していることを確認するのに役立ちます。 訪問者の大部分がこの識別子を使用しない場合、実装内に問題があることを示している可能性があります。

>[!NOTE]
>
>この指標は、Adobe TargetやAdobe Audience Managerなど、複数のCX Enterprise サービスを使用する場合のデバッグに特に重要です。 CX Enterprise製品で共有されるセグメントには、ECIDのない訪問者は含まれません。

## この指標の計算方法

この指標は、[ユニーク訪問者](unique-visitors.md)指標に基づきますが、`mid` クエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie に基づく）を使用して識別された個人のみが含まれます。

## ECID設定のデバッグ

Experience Cloud IDを持つ&#39;[!UICONTROL 訪問者]&#39;指標は、CX Enterprise統合のトラブルシューティングや、訪問者ID サービスまたはExperience Platform ID サービスがデプロイされていないサイトの領域の特定に役立ちます。

「[!UICONTROL Experience Cloud IDを持つ訪問者]」を並べてドラッグし、ユニーク訪問者と比較します。

![ユニーク訪問者の比較](assets/metric-mcvid1.png)

この例では、各ページにExperience Cloud ID]&#39;を持つ&#39;[!UICONTROL 訪問者と同じ数の&#39;[!UICONTROL  ユニーク訪問者]&#39;があることに注意してください。 ただし、&#39;[!UICONTROL  ユニーク訪問者]&#39;の合計数は、Experience Cloud ID]&#39;を持つ&#39;[!UICONTROL 訪問者の合計数を超えています。 [計算指標](../calculated-metrics/cm-overview.md)を作成して、次の定義を使用して、ECIDを使用していないページを調べることができます。

![計算指標の定義](assets/metric-mcvid2.png)

計算された指標をレポートに追加することで、ページレポートを並べ替えて、ECIDを持たない訪問者の数が最も多いページを表示できます。

ECIDのない![ ページ ](assets/metric-mcvid3.png)

「製品クイックビュー」ディメンション項目がECIDで正しく実装されていないことに注意してください。 組織内の適切なチームと協力して、これらのページを可能な限り早く更新できます。 [ブラウザーのタイプ](../dimensions/browser-type.md)、[サイトセクション](../dimensions/site-section.md)、[eVar](../dimensions/evar.md) など、あらゆるタイプのディメンションを使用して、類似したレポートを作成できます。
