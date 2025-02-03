---
title: 重点レビュー（各 Web サイトリリース後）
description: 以下の手順に従って、実装時にエラーが発生しないようにし、KPI に沿って進める必要があります。
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 68%

---

# 重点レビュー（各 Web サイトリリース後）

数か月ごとに実装をレビューする必要があるのはなぜですか。データ品質に関する問題がまだ小さいうちに解決できます。各 Web サイトのリリース後も、この重点レビューを一貫して行うと、年 2 回の [ 完全なレビュー ](/help/implement/review/full-review.md) がはるかに簡単になります。 また、小さな問題がビッグデータの問題に発展し、関係者の信頼を損なう可能性もなくなります。

## 1. 上位 5 件の KPI から開始します。

上位 5 件の主要業績評価指標（KPI）を把握することで、調査が必要な関連指標と関連ディメンションを判断するのに役立ちます。過去 6 か月間に KPI を更新していない場合や、ビジネスがまだ KPI を作成していない場合は、[ 次の手順 ](/help/implement/review/define-kpis.md) に従ってください。

## 2. KPI 指標と変数が引き続き正常に機能していることを確認します

時間をかけてコードを更新すると、意図しない影響が生じる可能性があります。[上位 5 件の KPI](/help/implement/review/define-kpis.md) に関連付けられているすべての指標とディメンションが、引き続き正しく機能していることを確認する必要があります。これは web サイトのリリース直後に行うことが理想です。過去数か月間行っていない場合は、（今すぐ *実施し* ください。 次に手順を示します。

* ダッシュボードを作成して、これらの重要な指標と変数の時間別トレンドビューを確認します（または、各指標に対して [ アラート ](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=ja) を設定します）。 その後、1 ～ 2 日監視し、期待するデータが取得され、データが正しいことを確認します。 変曲点を探します。重要な問題を直ちに修正できるよう備えてください。不一致が見つかった場合は、データレイヤー、タグマネージャーのルール、処理ルールを調べて理由を見つけます。
*  [Analytics ヘルスダッシュボード](https://express.adobe.com/page/tnNQGNlfzta3b/)を再実行して、KPI 指標および変数の幅広いトレンドを監視します。

*指標と変数が正しく機能していることを確認する方法について詳しくは、Adobe Analytics チャンピオンの Sarah Owen による[これらのヒント](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608?profile.language=ja)を参照してください。*

## 3. サイトの更新されたセクションのデータをよく調べます。

最新のリリースサイトが、サイトのそのセクションのデータ収集に悪影響を与えていないことを確認します。そのセクションに対応するコードと変数をすべて確認し、新しいトラッキングが設計どおりに動作することを確認します。

## 4. ドキュメントを更新します。

指標または変数を最近追加または変更した場合は、ビジネス要件ドキュメント（BRD）およびソリューションデザインリファレンス（SDR）を更新する必要があります。

実装のドキュメントがない場合は、変数のリストをエクスポートし、[ このテンプレート ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=ja#implementation) を使用して BRD または SDR を作成します。

## 5. データ品質に関するギャップを即座に解決します。

状況を評価し、データの修復計画を立てます。その後、必要な変更を行い、ドキュメントを更新し、変更を関係者に通知します。

*Adobe Analytics チャンピオンである Sarah Owen による、実装レビューを多忙なスケジュールに無理なく合わせられるタイミングに関する 2 分間のビデオをご覧ください。*


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ 実装の確認 ](https://video.tv.adobe.com/v/328340?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


