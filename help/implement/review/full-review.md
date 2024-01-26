---
title: 完全なレビュー
description: 6 か月ごとに実装状況を確認し、ビジネスニーズと KPI との整合性を維持します。
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 80%

---

# 完全なレビュー（年 2 回実装状況を確認する場合）

6 か月ごとに実装をレビューする必要があるのはなぜですか。お客様のビジネスニーズに合わせて実装を行う必要があるからです。また、データ品質に関する問題が小さく、関係者の信頼を損なう可能性のある主要なデータの問題に発展する前に、その問題に対処する必要があります。 6 か月ごとの完全なレビューに加えて、各 Web サイトのリリース後に、[重点レビュー](/help/implement/review/focused-review.md)を行う必要があります。

## 1. お客様の実装が、当社のビジネスニーズと完全に合致していることを確認します

ビジネスオーナーやアナリストと会い、変化するビジネスニーズを確認します。お客様の実装で現在満たされていないニーズや測定の機会については、KPI や測定計画を更新する方法を見つけ出してください。[BRD と SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=ja#implementation) に変更を記録してください。

## 2. 指標と変数が引き続き正常に機能していることを確認します

ビジネスにとって重要な順序で、すべての指標と変数を簡単に確認し、データが正しく収集されていることを確認します。  [上位 5 件の KPI ](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html?lang=ja#review)に関連付けられた、最も重要な指標や変数から開始します。次に手順を示します。

* ダッシュボードを作成して、指標と変数の月別トレンド表示を確認します ( または、 [インテリジェントアラート](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html) を参照 ) を使用して、期待するデータが取得され、データが正しいことを確認します。 不一致が見つかった場合は、データレイヤー、タグマネージャーのルールおよび処理ルールを調べて、その理由を見つけます。
* [Analytics ヘルスダッシュボード](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)を再実行して、指標と変数の広範なトレンドを監視します。

実装では、不要な指標や変数が多くなりすぎないようにしてください。 ビジネスで不要になった指標や変数は無効にしてください。これらは、後で削除したり再利用したりできます。

## 3. KPI を更新します

ビジネス目標の表示が一新されました。*最も*&#x200B;重要な KPI（主要業績指標）5 件を選択していることを再評価してください。5 つのみ選択してください。これらの KPI には、売上高などの指標や、1 訪問あたりの売上高などの計算指標を使用でき、指標に変数を含めることもできます。詳しくは、[上位 5 件の KPI の定義](/help/implement/review/define-kpis.md)を参照してください。
