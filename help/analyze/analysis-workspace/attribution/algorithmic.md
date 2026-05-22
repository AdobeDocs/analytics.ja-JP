---
title: アルゴリズムアトリビューション
description: アルゴリズムアトリビューションモデルの詳細を理解します。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: 'https://experienceleague.adobe.com/jPLoQcRU8bpCGjKJ37mioUdZOFDUwNehmyBhdx7lj8c'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 38%

---

# アルゴリズムアトリビューション

Analysis Workspace のアルゴリズム[アトリビューションモデル](models.md)は、統計的な手法を使用して、レポートまたはフリーフォームテーブルのディメンション項目にクレジットを割り当てるという点で、他のモデルとは異なります。 Analysis Workspaceの他のすべてのアトリビューションモデルと同様に、アルゴリズムによるアトリビューションは、あらゆるディメンションや指標で利用できます。 アルゴリズムアトリビューションでは、無制限のセグメンテーションと分類がサポートされ、コンバージョンの100%がテーブル内の1つ以上のディメンション（「分数」アトリビューションとも呼ばれます）に分布されます。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ アルゴリズムアトリビューション ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。 Harsanyiの配当金は、結果に不平等な貢献を持つゲームのプレイヤー間で信用を分配するためのShapleyの価値ソリューションの一般化（Lloyd Shapley、ノーベル賞経済学者にちなんで名付けられた）です。

各タッチポイントに対するコンバージョンクレジットのアトリビューション計算では、ルックバックウィンドウ内の各マーケティングタッチポイントをプレイヤーの連合と見なします。 その連立候補には、利益が公平に分配されなければならない。 各連合の黒字配分は、各連合が以前に再帰的に作成した黒字から決定されます。

詳しくは、John HarsanyiとLloyd Shapleyのオリジナルの論文を参照してください。

* シェイプリー、ロイド S。 (1953). n 人用ゲームの値 *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi、ジョン C。 (1963). n 人用協力ゲームのシンプル版安価モデル。 *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>アルゴリズムアトリビューションの結果は、特定のルックバックウィンドウ内に複数のタッチポイントが存在する場合のみ、他のモデルと異なります。 単一のタッチポイントを持つコンバージョンは、アトリビューションモデルに関係なく、100%のクレジットを受け取ります。
