---
title: アトリビューションのベストプラクティス
description: アトリビューションモデルの決定に関するベストプラクティスは何ですか。
source-git-commit: 3f586a6a183baf5ff388a55105886eb31fd4366a
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---


# アトリビューションのベストプラクティス

組織に適したアトリビューションモデルの選択は、多くの考慮事項に基づいておこないます。 この記事では、方法といくつかの一般的なベストプラクティスについて説明します。

## 手順1:探索分析

>[!NOTE]
>この分析は、アトリビューションモデルを選択する前におこなう必要があります。

このフェーズでは、最初に顧客の行動を把握し、コンバージョン指標を定義します。 コンバージョン指標に基づいて、[データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en)（生データ用）やAnalysis Workspaceなどのツールを使用すると、

* コンバージョンをおこなう前に、様々なマーケティングチャネルに接触している顧客の数
* これらの動作の割合/分布。

例えば、50%の顧客がコンバージョンの前に3つのチャネルにタッチした場合、これら3つのチャネル間で何らかのインタラクションはありますか。
その後、ファネルの上下の分析を行って、理解を深めることができます。

### 上位ファネル分析

アッパーファネル分析は、ブランドや製品の認知度の作成に使用されるチャネルを分析します。 例えば、ほとんどのテレビ広告の目標はブランド認知です。 [「タイムディケイ」アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md)は、時間の経過と共にテレビ広告を忘れてしまうので、使用することもできます。

### 低ファネル分析

この分析では、ユーザーが既にブランドを知っていて、コンバージョンを求めていると仮定します。 電子メールまたはプッシュ通知またはFacebook広告を使用します。

## 手順2:ルールベースアトリビューション

この手順の目的は、仮説を検証することです。

**例 1**

仮説が「ファーストタッチチャネルは、ラストタッチチャネルよりもコンバージョンに大きな影響を与えます。 次に、[&quot;逆J字形&quot;アトリビューションモデル](/help/analyze/analysis-workspace/attribution/models.md)を使用して、この仮説をテストします。 このモデルでは、ファーストタッチポイントに対するクレジットの60%が与えられます。

**例 2**

仮説は次のようになります。「当社の業界（旅行業など）では、顧客が商品を購入する前に多くの調査をおこなうので、アトリビューション期間は30日ではなく60日か90日です。 次に、[ルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=en#lookback-windows)を90日に変更します。

## 手順3:アルゴリズムアトリビューションの使用

考えられる仮説と組み合わせの数を多く検証するのは非常に困難なので、[アルゴリズムアトリビューション](/help/analyze/analysis-workspace/attribution/algorithmic.md)を使用して、この作業を組み込みのアルゴリズムに任せることができます。 すべての質問に答え、最適なアトリビューションモデルが既に見つかっている場合は、この手順を実行する必要はありません。

## その他の考慮事項

* Analysis Workspaceだけに依存するのではなく、データサイエンティストのサービスを使用する必要が生じる場合があります。
* Adobeデータフィードのように、生データを使用できます。
* [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja)の使用を検討します。例えば、インプレッションデータを検討する場合などです。
