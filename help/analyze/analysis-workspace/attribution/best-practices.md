---
title: アトリビューションのベストプラクティス
description: アトリビューションモデルの決定に関するベストプラクティスは何ですか。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# アトリビューションのベストプラクティス

組織に適したアトリビューションモデルの選択は、多くの考慮事項に基づいて行います。この記事では、方法といくつかの一般的なベストプラクティスについて説明します。

## 手順 1：探索的分析

>[!NOTE]
>この分析は、アトリビューションモデルを選択する前に行う必要があります。

このフェーズでは、最初に顧客の行動を把握し、コンバージョン指標を定義します。コンバージョン指標に基づいて、 [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=ja) （生データ用）や Analysis Workspace などのツールを使用すると、

* コンバージョンに至る前に様々なマーケティングチャネルに接触した顧客の数
* これらの動作の割合／分布

例えば、50% の顧客がコンバージョンの前に 3 つのチャネルにタッチした場合、これら 3 つのチャネル間で何らかのインタラクションはありますか。
その後、ファネルの上下の分析を行って、理解を深めることができます。

### 上位ファネル分析

上位ファネル分析は、ブランドや製品の認知度の作成に使用されるチャネルを分析します。例えば、ほとんどのテレビ広告の目標はブランド認知度の向上です。時間の経過と共にテレビ広告は忘れられてしまうので、 [「タイムディケイ」アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md) を使用することもできます。

### 下部ファネル分析

下部ファネル分析では、人物が既にブランドを知っていて、コンバージョンすることを求めていると仮定します。メール、プッシュ通知または Facebook 広告を使用します。

## 手順 2：ルールベースのアトリビューション

この手順の目的は、仮説を検証することです。

**例 1**

「ファーストタッチチャネルは、ラストタッチチャネルよりもコンバージョンに大きな影響を与える」という仮説を仮定します。

この場合、[「逆 J 字型」アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md)を使用して、この仮説をテストします。このモデルでは、ファーストタッチポイントに対するクレジットの 60% が与えられます。

**例 2**

「当社の業界（旅行業など）では、顧客が商品の購入前に大量に調査するので、アトリビューションウィンドウは 30 日ではなく 60 日か 90 日です」という仮説を仮定します。

この場合、[ルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=ja#lookback-windows)を 90 日に変更します。

## 手順 3：アルゴリズムアトリビューションの使用

すべての質問に対して満足のいく回答を提供するアトリビューションモデルがまだない場合は、[アルゴリズムアトリビューション](/help/analyze/analysis-workspace/attribution/algorithmic.md)を使用できます。考えられる多数の仮説と組み合わせを検証することは非常に難しいので、アルゴリズムアトリビューションでは、組み込みアルゴリズムを使用して、ディメンション項目全体にクレジットを割り当てます。

## その他の考慮事項

* Analysis Workspace だけに依存するのではなく、データサイエンティストのサービスを使用する必要性が生じる場合があります。
* Adobe データフィードのように、生データを使用できます。
* [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) の使用を検討します。例えば、インプレッションデータを検討する場合などに有効です。
