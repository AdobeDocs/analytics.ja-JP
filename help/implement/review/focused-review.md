---
title: 重点レビュー（各Webサイトリリース後）
description: 以下の手順に従って、導入時にエラーが発生しないようにし、KPIに沿っておく必要があります。
translation-type: tm+mt
source-git-commit: 912e5077889a02c3bf0dea9b079d213bb20f9424
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# 重点レビュー（各Webサイトリリース後）

数か月ごとに実装を確認する必要があるのはなぜですか。 したがって、データの質に関する問題は、それでも小さいうちに解決できます。 各Webサイトのリリース後も、この重点レビューを一貫して行うと、毎年2回の[完全なレビュー](/help/implement/review/full-review.md)はるかに簡単になります。 また、小さな問題が大きなデータの問題に発展し、関係者の信頼を損なう可能性があるのを防ぐこともできます。

## 1.トップ5のKPIとの開始

トップ5の主要業績評価指標(KPI)を把握することで、調査する必要がある関連指標と関連ディメンションを判断するのに役立ちます。 過去6か月間にKPIを更新していない場合、またはまだKPIを作成していない場合は、[次の手順](/help/implement/review/define-kpis.md)に従ってください。

## 2. KPI指標と変数が引き続き正常に機能していることを確認する

時間の経過と共にコードを更新すると、意図しない影響が生じる可能性があります。 [トップ5のKPI](/help/implement/review/define-kpis.md)に関連付けられているすべての指標とディメンションが、引き続き正しく機能していることを確認する必要があります。 理想的には、これはWebサイトのリリース直後に行う必要があります。ここ数か月間それを行っていない場合は、今すぐ&#x200B;**&#x200B;してください。 次に手順を示します。

* ダッシュボードを作成して、これらの重要な指標と変数の時間別トレンド表示を確認します（または、各指標に対して[インテリジェントアラート](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace)を設定します）。 その後、1 ～ 2日監視し、期待するデータが正しく取得され、データが正しいことを確認します。 変曲点を探します。 重要な問題を直ちに修正する準備をしてください。 不一致が見つかった場合は、データレイヤー、タグマネージャーのルール、処理ルールを確認して理由を調べます。
* [Analytics正常性ダッシュボード](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)を再実行して、KPI指標と変数の広範なトレンドを監視します。

*指標と変数が正しく機能していることを確認する方法について詳しくは、Adobe AnalyticsチャンピオンのSarah Owen氏から、次の [](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) 情報をお読みください。*

## 3.サイトの更新されたセクションのデータをよく調べます。

最新のリリースのサイトが、サイトのそのセクションのデータ収集に悪影響を与えていないことを確認します。そのセクションに対応するコードと変数をすべて確認し、新しいトラッキングが設計どおりに動作することを確認します。

## 4.ドキュメントを更新する

最近、指標または変数を追加または変更した場合は、ビジネス要件ドキュメント(BRD)およびソリューションデザインリファレンス(SDR)を更新する必要があります。

実装に関するドキュメントがない場合は、変数のリストをエクスポートし、[このテンプレート](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)を使用してBRDまたはSDRを作成します。

## 5.データ品質に関するギャップを即座に解決

状況を評価し、データの修復計画を立てます。 その後、必要な変更を行い、ドキュメントを更新し、変更を関係者に通知します。

*Adobe AnalyticsチャンピオンのSarah Owen氏が提供する、お客様の多忙なスケジュールに導入のレビューを適切に表示できる自然な時期に関するビデオを、2分間ご覧ください。*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
