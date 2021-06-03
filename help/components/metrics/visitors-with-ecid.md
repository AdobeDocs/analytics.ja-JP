---
title: Experience Cloud ID を持つ訪問者
description: Adobe Experience Cloud ID サービスを使用しているユニーク訪問者の数です。
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 96%

---

# Experience Cloud ID を持つ訪問者

「Experience Cloud ID を持つ訪問者」指標は、アドビが [Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)を使用して識別したユニーク訪問者の数を示します。このディメンションは、[ユニーク訪問者](unique-visitors.md)指標と比較して、サイトへの大部分の訪問者が ID サービスを使用していることを確認するのに役立ちます。訪問者の大部分が ID サービス cookie を使用していない場合は、実装内の問題を示している可能性があります。

>[!NOTE]
>
>この指標は、Adobe Target や Adobe Audience Manager など複数の Experience Cloud サービスを使用する場合のデバッグに特に重要です。Experience Cloud 製品間で共有されるセグメントには、Experience Cloud ID のない訪問者は含まれません。

## この指標の計算方法

この指標は、[ユニーク訪問者](unique-visitors.md)指標に基づきますが、`mid` クエリ文字列（[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie に基づく）を使用して識別された個人のみが含まれます。

## Experience Cloud ID 設定のデバッグ

「Experience Cloud ID を持つ訪問者」指標は、Experience Cloud 統合のトラブルシューティングや、ID サービスがデプロイされていないサイトの領域の特定に役立ちます。

「Experience Cloud ID を持つ訪問者」をユニーク訪問者と並べてドラッグして比較します。

![ユニーク訪問者の比較](assets/metric-mcvid1.png)

この例では、各ページのユニーク訪問者が Experience Cloud ID での訪問者と同じ数になっていることに注意してください。ただし、ユニーク訪問者の合計数は Experience Cloud ID での訪問者の合計数より大きくなっています。ID サービスが設定されていないページを調べる[計算指標](../c-calcmetrics/cm-overview.md)を作成できます。次の定義を使用できます。

![計算指標の定義](assets/metric-mcvid2.png)

この計算指標をレポートに追加することで、MCID を持たない訪問者の数が最も多いページがひとめでわかるように、ページレポートをソートすることができます。

![ID サービスを使用しないページ](assets/metric-mcvid3.png)

「製品クイックビュー」ディメンション項目は、ID サービスでは正しく実装されないことに注意してください。組織内の適切なチームと協力して、これらのページを可能な限り早く更新できます。[ブラウザーのタイプ](../dimensions/browser-type.md)、[サイトセクション](../dimensions/site-section.md)、[eVar](../dimensions/evar.md) など、あらゆるタイプのディメンションを使用して、類似したレポートを作成できます。
