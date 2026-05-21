---
title: 重点レビュー（各 Web サイトリリース後）
description: 以下の手順に従って、実装時にエラーが発生しないようにし、KPI に沿って進める必要があります。
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
TQID: https://experienceleague.adobe.com/C57qRRa4-WDgJDgvtLebgy-0DAPvMUreSrGfuA67N4o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 62%

---

# 重点レビュー（各 Web サイトリリース後）

数か月ごとに実装をレビューする必要があるのはなぜですか。 データ品質に関する問題がまだ小さいうちに解決できます。 各web サイトのリリース後に、この焦点を絞ったレビューを継続的に行う場合は、年2回の[&#x200B; フルレビュー](/help/implement/review/full-review.md)がはるかに簡単になります。 また、軽微な問題が、関係者の信頼を損なう可能性のあるビッグデータの問題に発展するのを防ぐことができます。

## &#x200B;1. 上位5つのKPIから始める

上位 5 件の主要業績評価指標（KPI）を把握することで、調査が必要な関連指標と関連ディメンションを判断するのに役立ちます。 過去6か月間にKPIを更新していない場合、またはビジネスでまだKPIを作成していない場合は、[次の手順](/help/implement/review/define-kpis.md)に従ってください。

## &#x200B;2. KPI指標と変数が引き続き適切に機能することを確認します

時間をかけてコードを更新すると、意図しない影響が生じる可能性があります。 [上位 5 件の KPI](/help/implement/review/define-kpis.md) に関連付けられているすべての指標とディメンションが、引き続き正しく機能していることを確認する必要があります。 これは、web サイトのリリース直後に行うのが理想的です。過去数か月に行っていない場合は、*今すぐ*&#x200B;実行してください。 次に手順を示します。

* ダッシュボードを作成して、これらの重要な指標と変数の時間別トレンドビューを表示します（または、各指標に[&#x200B; アラート &#x200B;](/help/components/alerts/alerts-overview.md)を設定します）。 そして、1日か2日監視して、期待するデータが得られていることを確認し、データが正しいことを確認します。 変曲点を探します。 重要な問題を直ちに修正できるよう備えてください。 不一致が見つかった場合は、データレイヤー、タグマネージャーのルール、処理ルールを調べて理由を見つけます。
* [Analytics ヘルスダッシュボード](https://express.adobe.com/page/tnNQGNlfzta3b/)を再実行して、KPI 指標および変数の幅広いトレンドを監視します。

*指標と変数が正しく機能していることを確認する方法について詳しくは、Adobe Analytics チャンピオンの Sarah Owen による[これらのヒント](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608?profile.language=ja)を参照してください。*

## &#x200B;3. サイトの更新されたセクションからのデータを徹底的に調べます

最新のリリースサイトが、サイトのそのセクションのデータ収集に悪影響を与えていないことを確認します。そのセクションに対応するコードと変数をすべて確認し、新しいトラッキングが設計どおりに動作することを確認します。

## &#x200B;4. ドキュメントを更新する

指標または変数を最近追加または変更した場合は、ビジネス要件ドキュメント（BRD）およびソリューションデザインリファレンス（SDR）を更新する必要があります。

実装に関するドキュメントがない場合は、変数のリストを書き出し、[このテンプレート &#x200B;](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=ja#implementation)を使用してBRDまたはSDRを作成します。

## &#x200B;5. データ品質のギャップにすばやく対処できます

状況を評価し、データの修復計画を立てます。 その後、必要な変更を行い、ドキュメントを更新し、変更を関係者に通知します。

*Adobe Analytics チャンピオンである Sarah Owen による、実装レビューを多忙なスケジュールに無理なく合わせられるタイミングに関する 2 分間のビデオをご覧ください。*


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [実装のレビュー](https://video.tv.adobe.com/v/3440170?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


