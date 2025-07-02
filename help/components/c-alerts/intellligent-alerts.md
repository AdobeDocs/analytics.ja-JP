---
description: アラートを使用して、通知の詳細な制御や異常値検出との統合を可能にする方法を説明します。
title: アラートの概要
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 94%

---

# アラートの概要

Adobe Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。

また、Adobe Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。これらのアラート（「インテリジェントアラート」とも呼ばれる）は、[異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)と統合された詳細なコントロールを提供し、最も必要なときにトリガーされます。

アラートを使用すると、次のことができます。

* アラートがトリガーされる頻度のプレビュー
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信
* 1 つのアラートで複数の指標を示す「積み重ね」アラートの作成
* 異常値（90％、95％、99％、99.75％、99.9％のしきい値、変化率、超過／未満）に基づいてアラートを作成します（Select、Prime、Ultimate のいずれかのパッケージを使用する Adobe Analytics のお客様のみが使用できます）。

ビデオチュートリアル（[アラート](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=ja)（5:34））では、アラートの基本的な概要について説明します

## アラートの異常値ルックバック

>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Adobe Analytics Prime または Ultimate パッケージを利用中の組織のみが使用できます。

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに選択した精度に応じて異なります。

* 月単位の精度：15 ヶ月 + 前年の同じ時間範囲
* 週単位の精度：15 週 + 前年の同じ時間範囲
* 日単位の精度：35 日 + 前年の同じ時間範囲
* 時間単位の精度：336 時間

詳しくは、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)を参照してください。

## アラートの作成

Adobe Analytics でアラートを作成する方法について詳しくは、[アラートの作成](/help/components/c-alerts/alert-builder.md)を参照してください。

>[!IMPORTANT]
>
>タイムスタンプ付きデータを使用してアラートを作成すると、アラートが誤って起動される可能性があります。アラートには、タイムスタンプのないデータの使用をお勧めします。

## アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。タグ付け、名前変更、削除など、アラートに対して様々な管理タスクを実行できます。

Adobe Analytics で既存のアラートを管理する方法について詳しくは、[アラートの管理](/help/components/c-alerts/alert-manager.md)を参照してください。
