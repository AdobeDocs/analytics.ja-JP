---
title: マーケティングチャネルの分析
description: Workspace でのマーケティングチャネルディメンションの使用方法について説明します。
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
TQID: https://experienceleague.adobe.com/XWjRuwOusH-TsOb5rzG8rAIkye3faYxfZzyQOMrav3Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 77%

---

# マーケティングチャネルの分析

>[!NOTE]
>
>アトリビューションとAdobe Analyticsのマーケティングチャネルの効果を最大化するために、いくつかの[改訂されたベストプラクティス &#x200B;](/help/components/c-marketing-channels/mchannel-best-practices.md)を公開しました。
>
>Analytics 管理者は、[マーケティングチャネルの管理](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)の説明に従って、組織のマーケティングチャネルを管理できます。

マーケティング施策のターゲットをより的確に絞り、マーケティング投資の費用対効果を高めるために、どのマーケティングチャネルが誰に対して最も効果的かを知りたい場合があるでしょう。 Adobe Adobe Analyticsでは、Workspaceのマーケティングチャネルのディメンションと指標は、注文や売上などにさまざまなチャネルが与える影響を追跡し、チャネルに関する有用なインサイトを獲得するのに役立つツールのひとつです。 マーケティングチャネルに関連して使用できるディメンションと指標は次のとおりです。

![](assets/mc-dims.png)

| ディメンション／指標 | 定義 |
| --- | --- |
| マーケティングチャネル | これは、使用が推奨されるマーケティングチャネルディメンションです。 アトリビューションモデルは、実行時に適用することができます。 このディメンションはラストタッチチャネルディメンションと同じように動作しますが、異なるアトリビューションモデルを適用して使用する際に混乱を招かないよう、異なるラベルが付けられています。 |
| ラストタッチチャネル | ラストタッチアトリビューションモデルが事前に適用され、変更できないレガシーディメンションです。 |
| ファーストタッチチャネル | ファーストタッチアトリビューションモデルが事前に適用され、変更できないレガシーディメンションです。 |
| マーケティングチャネルインスタンス | この指標は、ページビューやカスタムリンク名の呼び出しなど、マーケティングチャネルがイメージリクエストで定義された回数を測定します。 永続化された値は含まれません。 |
| 新規エンゲージメント | この指標はインスタンスと似ていますが、イメージリクエストでファーストタッチマーケティングチャネルが定義された場合にのみ増加します。 |

## 基本分析

このフリーフォームテーブルは、各マーケティングチャネルのオンライン注文件数、オンライン売上高、およびコンバージョン率を示します。

![](assets/mc-viz1.png)

各マーケティングチャネルのオンライン注文件数とオンライン売上高をドーナツグラフで示します。

![](assets/mc-viz2.png)

この折れ線グラフは、様々なチャネルのオンライン注文件数の経時的なトレンドを示します。

![](assets/mc-viz3.png)

## アドバンス分析

マーケティングチャネルの詳細：各チャネルをより詳細に把握し、特定のキャンペーンや施策の配置などを表示できます。各マーケティングチャネルの内容は、次のとおりです。

![](assets/mc-viz4.png)

## アトリビューションモデルの適用

[&#x200B; アトリビューション &#x200B;](/help/analyze/analysis-workspace/attribution/overview.md)を使用して、様々なアトリビューションモデルを瞬時に適用できます。

![](assets/mc-viz5.png)

異なるアトリビューションモデルを適用すると、同じ指標（オンライン注文件数）から異なる結果が生成されます。

## クロスタブマーケティング分析

従来のファーストタッチチャネルとラストタッチチャネルを使用すると、チャネル間のインタラクションを便利なビューで確認できます。

![](assets/mc-viz6.png)

クロスタブマーケティングの分析について詳しくは、次のビデオを参照してください。[クロスタブ分析を使用した Analysis Workspace の基本的なマーケティング属性の調査](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html?lang=ja)
