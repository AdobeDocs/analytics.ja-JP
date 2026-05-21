---
title: アトリビューションのベストプラクティス
description: 使用するアトリビューションモデルを決定する際のベストプラクティスを理解します。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: https://experienceleague.adobe.com/3h12v3wRMC0SY63jsXBbG6kkTM8ArVOz6ctJVikdKb4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 64%

---

# アトリビューションのベストプラクティス

組織に適したアトリビューションモデルの選択は、多くの考慮事項に基づいて行います。 この記事では、メソドロジーと一般的なベストプラクティスについて解説します。

* [探索的分析](#exploratory-analysis)
* [ルールベースのアトリビューション](#rule-base-attribution)
* [アルゴリズムによるアトリビューション](#use-algorithmic-attribution)

## 探索的分析

>[!NOTE]
>この分析は、アトリビューションモデルを選択する前に行う必要があります。

このフェーズでは、最初に顧客の行動を把握し、コンバージョン指標を定義します。 コンバージョン指標に基づいて、 [データフィード](/help/export/analytics-data-feed/data-feed-overview.md) （生データ用）や Analysis Workspace などのツールを使用すると、

* コンバージョンに至る前に様々なマーケティングチャネルに接触した顧客の数
* これらの動作の割合／分布

例えば、50% の顧客がコンバージョンの前に 3 つのチャネルにタッチした場合、これら 3 つのチャネル間で何らかのインタラクションはありますか。
その後、ファネルの上下の分析を行って、理解を深めることができます。

### 上位ファネル分析

上位ファネル分析は、ブランドや製品の認知度の作成に使用されるチャネルを分析します。 例えば、ほとんどのテレビ広告の目標はブランド認知度の向上です。 テレビ広告は時間の経過とともに忘れられるので、[時間減衰アトリビューションモデル ](/help/analyze/analysis-workspace/attribution/models.md)を使用することができます。

### 下部ファネル分析

下部ファネル分析では、人物が既にブランドを知っていて、コンバージョンすることを求めていると仮定します。 メール、プッシュ通知または Facebook 広告を使用します。

## ルールベースアトリビューション

この手順の目的は、仮説を検証することです。

**例 1**

仮説が「*私のファーストタッチチャネルは、私のラストタッチチャネルよりもコンバージョンに大きな影響を与えます。*」

この場合、[逆J字型アトリビューションモデル ](/help/analyze/analysis-workspace/attribution/models.md)を使用して、この仮説をテストします。 このモデルでは、ファーストタッチポイントに対するクレジットの 60% が与えられます。

**例 2**

仮説が次のようであるとします。*「特定の業界（旅行業界など）では、顧客は製品を購入する前に多くの調査を行うため、アトリビューション期間は30日ではなく60日または90日です。*」

この場合、[ルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md)を 90 日に変更します。

## アルゴリズムによるアトリビューション

すべての質問に対して満足のいく回答を提供するアトリビューションモデルがまだない場合は、[アルゴリズムアトリビューション](/help/analyze/analysis-workspace/attribution/algorithmic.md)を使用できます。 考えられる多数の仮説と組み合わせを検証することは非常に難しいので、アルゴリズムアトリビューションでは、ビルトインのアルゴリズムを使用して、ディメンション項目全体にクレジットを割り当てます。

## その他の考慮事項

* Analysis Workspace だけに依存するのではなく、データサイエンティストのサービスを使用する必要性が生じる場合があります。
* Adobe データフィードのように、生データを使用できます。
* インプレッションデータを考慮する場合は、例えば[Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview)の使用を検討してください。
