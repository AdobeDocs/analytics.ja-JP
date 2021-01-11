---
title: 完全なレビュー
description: 6か月ごとに導入状況を確認し、ビジネスニーズとKPIとの整合性を維持します。
translation-type: tm+mt
source-git-commit: ad7274dbed3b85ca24cd92bf3a0d36d1f2e3597b
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# 完全なレビュー（年2回導入状況を確認する場合）

6か月ごとに実装を確認する必要があるのはなぜですか。 お客様のビジネスニーズに合わせて導入を行う必要があるからです。 また、データの質が小さいうちに、関係者の信頼を損なう可能性のある主要なデータの問題になる前に、データの質に関する問題に対処する必要があります。 6か月ごとの完全なレビューに加えて、各Webサイトのリリース後に、[集中的なレビュー](/help/implement/review/focused-review.md)を行う必要があります。

## 1.お客様の導入が、当社のビジネスニーズに完全に合致していることを確認します。

ビジネスの所有者やアナリストと会い、変化するビジネス・ニーズを確認。 お客様の導入が現在満たしていないニーズや測定のオポチュニティについては、KPIや測定計画を更新する方法を見極めてください。 [BRDとSDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)に変更を記録してください。

## 2.指標と変数が引き続き正常に機能していることを確認します。

ビジネスにとって重要な順番で、すべての指標と変数を簡単に確認し、データが正しく収集されていることを確認します。 [トップ5のKPI](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html?lang=en#review)に関連付けられた指標と変数に関する開始。 次に手順を示します。

* 指標と変数の月別トレンド表示を確認するダッシュボードを作成し（または各指標に対して[インテリジェントアラート](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace)を設定）、期待するデータが確実に取得され、データが正しいことを確認します。 不一致が見つかった場合は、データレイヤー、タグマネージャーのルールおよび処理ルールを調べて、その理由を調べます。
* [Analytics正常性ダッシュボード](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)を再実行して、指標と変数の広範なトレンドを監視します。

不要な指標や変数に対する実装の負荷を軽減しないでください。 ビジネスで不要になった指標または変数を無効にします。 後で削除したり再利用したりできます。

## 3. KPIを更新します。

ビジネス目標の表示が一新されたので、最も&#x200B;*重要なKPI (Key Performance Indicators) 5個を選択したかどうかを再評価します。* 5つしか持てない！ これらのKPIには売上高などの指標や1訪問あたりの売上高などの計算指標を使用でき、指標にも変数を含めることができます。 詳細については、[トップ5 KPIの定義](/help/implement/review/define-kpis.md)を参照してください。
