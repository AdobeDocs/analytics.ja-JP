---
description: アラートを使用して、通知をきめ細かく制御したり、異常値検出と統合したりする方法について説明します。
title: アラートの概要
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 54%

---

# アラートの概要

Adobe Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。

また、Adobe Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。これらのアラート（*インテリジェントアラート* とも呼ばれます）では、[ 異常値検出 ](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) と統合され、最も必要なときにトリガーされる詳細なコントロールが提供されます。

アラートを使用すると、次のことができます。

* アラートのトリガー頻度をプレビューする。
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信。
* 1 つのアラートに複数の指標を取り込む *スタック型* アラートを作成します。
* 以下に基づいてアラートを作成：
   * 存在する指標の異常値が、想定されるしきい値を超える、または下回っている。

     [ 異常値検出 ](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) では、履歴データを使用して、期待値に上限と下限を加えて構築します。 実際の指標の値が、上限またはしきい値として定義された下限を超えた場合、そのイベントはしきい値信頼性レベルでの異常値と見なされ、アラートのトリガーを設定します。 しきい値が高い場合（例：99% または 99.9%）は、帯域幅が広いことを意味し、より極端な異常値によって引き起こされるアラートが少なくなります。 しきい値が低い（例：90%）場合は帯域が狭いことを意味し、極端な異常値が少ないことが原因で発生するアラートが多くなります。
   * 特定の割合による指標の変化。
   * 特定の値より上、下、または等しい指標。 （Select、Prime、Ultimateのいずれかのパッケージを利用するAdobe Analyticsのお客様のみが利用できます）

この [ ビデオチュートリアル ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) では、アラートの基本的な概要を説明します。


## アラートの異常値ルックバック

>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Adobe Analytics Prime または Ultimate パッケージを使用している組織でのみ使用できます。

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに選択した精度に応じて異なります。

* 月単位の精度：15 ヶ月 + 前年の同じ時間範囲
* 週単位の精度：15 週 + 前年の同じ時間範囲
* 日単位の精度：35 日 + 前年の同じ時間範囲
* 時間単位の精度：336 時間

詳しくは、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)を参照してください。

## アラートの作成

Adobe Analytics でアラートを作成する方法について詳しくは、[アラートの作成](/help/components/alerts/alert-builder.md)を参照してください。

>[!IMPORTANT]
>
>タイムスタンプ付きデータを使用してアラートを作成すると、アラートが誤って起動される可能性があります。アラートには、タイムスタンプのないデータの使用をお勧めします。

## アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。タグ付け、名前変更、削除など、アラートに対して様々な管理タスクを実行できます。

Adobe Analytics で既存のアラートを管理する方法について詳しくは、[アラートの管理](/help/components/alerts/alert-manager.md)を参照してください。
