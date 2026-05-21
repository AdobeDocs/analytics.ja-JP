---
title: データレイヤーの作成
description: Analytics の実装におけるデータレイヤーと、それらを Adobe Analytics で変数のマッピングに使用する方法について説明します。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 476
ht-degree: 100%

---

# データレイヤーの作成

データレイヤーは、Analytics 実装で使用される変数値を格納したサイト上の JavaScript オブジェクトで構成されるフレームワークです。 Analytics 変数に値を割り当てる際の、制御が強化され、メンテナンスが容易になります。

## 前提条件

[ソリューションデザインドキュメントの作成](solution-design.md) - 組織がトラッキング要件に合わせて調整をおこなうことが重要です。 組織の開発チームに連絡する前に、ソリューションデザインドキュメントの準備が整っていることを確認します。

## ワークフロー

データレイヤーを使用して Adobe Analytics を実装する場合は、通常次の手順に従います。

1. **サイト開発チームと協力して、データレイヤーを実装します**：サイト開発チームは、主にデータレイヤーオブジェクトに正しい値が入力されることを確認する必要があります。 このページをサイト開発チームと共に確認し、チーム間で期待値が一致することを確認します。

   >[!NOTE]
   >
   >アドビ推奨のデータレイヤー仕様に従うことはオプションです。 データレイヤーが既に存在する場合、またはアドビの仕様に従わない場合は、どの仕様に従うかを組織で決定してください。

1. **ブラウザーコンソールを使用して、データレイヤーを検証します**：データレイヤーが作成されたら、任意のブラウザーの開発者コンソールを使用して、データレイヤーが機能していることを検証できます。 デベロッパーコンソールは、`F12` キーを使用してほとんどのブラウザーで開くことができます。 変数値の例は `adobeDataLayer.page.title` です。
1. **Adobe Experience Platform データ収集を使用して、データレイヤーオブジェクトをデータ要素にマッピングする**：この手順は、組織の実装方法によって次のように異なります。
   * **Web SDK を使用する場合**：目的のデータレイヤーオブジェクトを Adobe Experience Platform Edge の目的の XDM フィールドにマッピングします。 目的のデータレイヤーマッピングを決定するには、[Analytics XDM 変数のマッピング](../aep-edge/xdm-var-mapping.md)を参照してください。
   * **Analytics 拡張機能を使用する場合**：Adobe Experience Platform データ収集のタグにデータ要素を作成して、目的のデータレイヤーオブジェクトに割り当てます。 次に、Analytics 拡張機能内で、各データ要素を適切な Analytics 変数に割り当てます。

## 仕様

アドビでは、新規実装または再構築された実装に [Adobe クライアントデータレイヤー](https://github.com/adobe/adobe-client-data-layer/wiki)を使用することをお勧めします。

組織では、[カスタマーエクスペリエンスデジタルデータレイヤー](https://www.w3.org/2013/12/ceddl-201312.pdf)などの他のデータレイヤー仕様や、まったく別のカスタム仕様を自由に使用できます。 組織のニーズを満たす一貫したデータレイヤーに合わせることが最も重要です。

データレイヤーは拡張可能です。組織に固有の要件がある場合は、そのニーズに合わせてオブジェクトをデータレイヤーに含めることができます。

## データレイヤー値の設定

通常、データレイヤーはサーバーサイドを生成し、サイトコンテンツの構築に使用したのと同じオブジェクトを参照します。 組織の[ソリューションデザインドキュメント](solution-design.md)で設定されたトラッキング要件に基づいて、サイトのデータレイヤーを設定します。

## 次の手順

[データ要素へのデータレイヤーオブジェクトのマッピング](../launch/layer-to-elements.md)：Adobe Experience Platform で、サイトのデータレイヤーを使用します。
