---
title: アルゴリズムアトリビューション
description: アルゴリズムアトリビューションモデルの詳細。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 79%

---


# アルゴリズムアトリビューション

The Algorithmic [attribution model](models.md) in Analysis Workspace differs from other models in that it uses statistical techniques to allocate credit across the dimension items in your report or freeform table. Analysis Workspace 内の他のすべてのアトリビューションモデルと同様に、任意のディメンションまたは指標で使用でき、無制限のセグメント化と分類をサポートし、コンバージョンの 100% をテーブル内のディメンション（「分数」アトリビューションとも呼ばれます）に分配します。

アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。ハルサニ配当は、結果への貢献度が等しくないゲーム内のプレーヤー間でクレジットを分配するためのシャープレイ値ソリューション（ノーベル賞受賞者のエコノミスト、ロイドシャープレイにちなんで名付けられました）の一般化です。

高いレベルでは、各タッチポイントのコンバージョンクレジットのアトリビューション計算では、ルックバックウィンドウ内の各マーケティングタッチポイントを、剰余を均等に配分する必要のあるプレーヤーの連合とみなします。各連立与党の余剰分布は、各サブカオリティ（または以前に参加したディメンション項目）が再帰的に作成した剰余に従って決定されます。 詳しくは、John Harsanyi と Lloyd Shapley の元の論文を参照してください。

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>アルゴリズムアトリビューションの結果は、特定のルックバックウィンドウ内に複数のタッチポイントが存在する場合のみ、他のモデルと異なります。単一のタッチポイントを持つコンバージョンは、アトリビューションモデルに関係なく、100%のクレジットを受け取ります。
