---
title: 完全なレビュー
description: 6 か月ごとに実装状況を確認し、ビジネスニーズと KPI との整合性を維持します。
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 85%

---

# 完全なレビュー（年 2 回実装状況を確認する場合）

6 か月ごとに実装をレビューする必要があるのはなぜですか。 実装を、ビジネスニーズに合わせて確実におこなう必要があるからです。 また、まだ問題が小さく、関係者の信頼を損なう可能性のある重大なデータの問題に発展する前に、データ品質の問題に対処する必要があります。 6 か月ごとの完全なレビューに加えて、各 Web サイトのリリース後に、[重点レビュー](/help/implement/review/focused-review.md)をおこなう必要があります。

## 1.実装が、アドビのビジネスニーズと完全に合致していることを確認します。

ビジネスオーナーやアナリストと会い、変化するビジネスニーズを確認します。 お客様の実装で現在満たされていないニーズや測定の機会については、KPI や測定計画を更新する方法を見つけ出してください。 [BRD と SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation) に変更を記録してください。

## 2.指標と変数が引き続き正常に機能していることを確認します。

ビジネスにとって重要な順序で、すべての指標と変数を簡単に確認し、データが正しく収集されていることを確認します。  [上位 5 件の KPI ](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html#review)に関連付けられた、最も重要な指標や変数から開始します。次に手順を示します。

* ダッシュボードを作成して、指標と変数の月別トレンド表示を確認（または各指標に対して[インテリジェントアラート](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html?lang=ja#analysis-workspace)を設定）し、期待するデータが取得されており、データが正しいことを確認します。不一致が見つかった場合は、データレイヤー、タグマネージャーのルールおよび処理ルールを調べて、その理由を見つけます。
* [Analytics ヘルスダッシュボード](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)を再実行して、指標と変数の広範なトレンドを監視します。

実装では、不要な指標や変数が多くなりすぎないようにしてください。ビジネスで不要になった指標や変数は無効にしてください。これらは、後で削除または再利用することができます。

## 3. KPI を更新する

ビジネス目標の表示が一新されました。*最も*&#x200B;重要な KPI（主要業績指標）5 件を選択していることを再評価してください。5 つのみ選択してください。これらの KPI には、売上高などの指標や、1 訪問あたりの売上高などの計算指標を使用でき、指標に変数を含めることもできます。 詳細については、[上位 5 件の KPI の定義](/help/implement/review/define-kpis.md)を参照してください。
