---
title: アルゴリズムアトリビューション
description: アルゴリズムアトリビューションモデルの詳細を理解します。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 42%

---

# アルゴリズムアトリビューション

Analysis Workspace のアルゴリズム[アトリビューションモデル](models.md)は、統計的な手法を使用して、レポートまたはフリーフォームテーブルのディメンション項目にクレジットを割り当てるという点で、他のモデルとは異なります。Analysis Workspaceの他のすべてのアトリビューションモデルと同様に、アルゴリズムアトリビューションは、任意のディメンションまたは指標で使用できます。 アルゴリズムアトリビューションでは、無制限のセグメント化および分類をサポートし、コンバージョンの 100% をテーブル内の 1 つ以上のディメンション（「分数」アトリビューションとも呼ばれます）に分配します。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ アルゴリズムアトリビューション ](https://video.tv.adobe.com/v/36205?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。Harsanyi dividend は、結果に不平等な貢献を持つゲームのプレイヤー間でクレジットを分配するためのシャプレー価値ソリューション（ノーベル賞受賞者の Lloyd Shapley にちなんで名付けられた）の一般化です。

大まかに言えば、各タッチポイントのコンバージョンクレジットのアトリビューション計算は、ルックバックウィンドウ内の各マーケティングタッチポイントをプレーヤーのグループと見なします。 プレイヤーの連合に、余剰は公平に分配されなければならない。 各分科会の余剰分布は、各分科会が再帰的に以前に作成した余剰分まで決定される。

詳しくは、John Harsanyi と Lloyd Shapley の論文を参照してください。

* Shapley, Lloyd S. (1953).n 人用ゲームの値&#x200B;*Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963).n 人用協力ゲームのシンプル版安価モデル。*International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>アルゴリズムアトリビューションの結果は、特定のルックバックウィンドウ内に複数のタッチポイントが存在する場合のみ、他のモデルと異なります。単一のタッチポイントを持つコンバージョンは、アトリビューションモデルに関係なく、100%のクレジットを受け取ります。
