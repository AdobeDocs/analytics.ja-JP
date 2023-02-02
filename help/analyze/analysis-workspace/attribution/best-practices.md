---
title: アトリビューションのベストプラクティス
description: アトリビューションモデルの決定に関するベストプラクティスは何ですか。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 58%

---

# アトリビューションのベストプラクティス

組織に適したアトリビューションモデルの選択は、多くの考慮事項に基づいて行います。 この記事では、方法といくつかの一般的なベストプラクティスについて説明します。

## 手順 1：探索的分析

>[!NOTE]
>この分析は、アトリビューションモデルを選択する前に行う必要があります。

このフェーズでは、最初に顧客の行動を把握し、コンバージョン指標を定義します。 コンバージョン指標に基づいて、 [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=ja) （生データ用）や Analysis Workspace などのツールを使用すると、

* コンバージョンに至る前に様々なマーケティングチャネルに接触した顧客の数
* これらの行動の比率/分布

例えば、50% の顧客がコンバージョンの前に 3 つのチャネルにタッチした場合、これら 3 つのチャネル間で何らかのインタラクションはありますか。
その後、ファネルの上下の分析を行って、理解を深めることができます。

### 上位ファネル分析

上位ファネル分析チャネルは、ブランドや製品認知度の作成に使用されます。 例えば、ほとんどのテレビ広告の目標はブランド認知度の向上です。時間の経過と共にテレビ広告は忘れられてしまうので、 [「タイムディケイ」アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md) を使用することもできます。

### 下部ファネル分析

低ファネル分析では、ユーザーが既にブランドを把握し、コンバージョンを希望していると仮定します。 電子メール、プッシュ通知またはFacebook広告を使用します。

## 手順 2：ルールベースのアトリビューション

この手順の目的は、仮説を検証することです。

**例 1**

仮定：「ファーストタッチチャネルは、ラストタッチチャネルよりもコンバージョンに対する影響が大きくなります。」

この場合、 [「逆 J 字形」アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md) をクリックしてこの仮説をテストします。 このモデルでは、ファーストタッチポイントに対するクレジットの 60% が与えられます。

**例 2**

仮定：「当社の業界（旅行業界など）では、顧客が商品を購入する前に多くの調査を行うので、属性期間は 60 日か 90 日で、30 日ではありません。」

この場合、 [ルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=ja#lookback-windows) を 90 日に変更しました。

## 手順 3：アルゴリズムアトリビューションの使用

すべての質問に対して満足のいく回答を提供するアトリビューションモデルがまだない場合、 [アルゴリズムアトリビューション](/help/analyze/analysis-workspace/attribution/algorithmic.md). 考えられる多数の仮説と組み合わせを検証するのは非常に困難なので、アルゴリズムアトリビューションは、組み込みアルゴリズムを使用してディメンション項目にクレジットを割り当てます。

## その他の考慮事項

* Analysis Workspace だけに依存するのではなく、データサイエンティストのサービスを使用する必要性が生じる場合があります。
* Adobe データフィードのように、生データを使用できます。
* [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) の使用を検討します。例えば、インプレッションデータを検討する場合などに有効です。
