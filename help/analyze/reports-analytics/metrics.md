---
description: 指標はレポートの基礎で、データの相互関連を見て把握するのに役立ち、Web サイトに関する異なるデータセットを並べて比較することができます。指標は、ビュー数、クリックスルー数、リロード数、平均滞在時間、数量、注文件数、売上高など、訪問者の行動に関する量的な情報です。
title: 指標
topic: Reports and analytics
uuid: ae2021eb-8b26-4a98-b7a0-ce36bca46753
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 指標

指標はレポートの基礎で、データの相互関連を見て把握するのに役立ち、Web サイトに関する異なるデータセットを並べて比較することができます。指標は、ビュー数、クリックスルー数、リロード数、平均滞在時間、数量、注文件数、売上高など、訪問者の行動に関する量的な情報です。

## 指標

指標はレポートの基礎で、データの相互関連を見て把握するのに役立ち、Web サイトに関する異なるデータセットを並べて比較することができます。指標は、ビュー数、クリックスルー数、リロード数、平均滞在時間、数量、注文件数、売上高など、訪問者の行動に関する量的な情報です。

指標と関連日付はレポートの列に表示されます。トラフィック指標は、訪問者数に関するデータを表示します。コンバージョン指標は、購入、ダウンロード、またはユーザーが Web サイト上でとることが望まれるその他の行動などの成功イベントに関するデータを表示します。

[計算指標](/help/components/c-calcmetrics/cm-overview.md)は指標を組み合わせて作成します。

定義については、[指標の概要](/help/components/c-variables/c-metrics/metricslist.md)を参照してください

## デフォルトのレポート指標の選択

レポートレベルでデフォルトの指標を設定する手順を説明します。

<!-- 

t_metrics_set_default.xml

 -->

1. レポートを実行します。
1.  デフォルトの指標として保存する指標を追加します。
1. ドロップダウ **[!UICONTROL Add Metrics]** ンリストをクリックし、を選択しま **[!UICONTROL Set as Default]**&#x200B;す。

   選択された指標がこのレポートのデフォルトとして保存されます。次の情報はデフォルトの指標に適用されます。

* デフォルトの指標は、同一レポート内または同一レポートスイート内では、すべてのユーザーアカウントに対して適用されます。例えば、同じレポートスイート内の特定のレポートを閲覧しているすべてのユーザーには、前の手順を使用して設定された指標が表示されます。
* レポート間を移動する場合、最近閲覧したレポート内で表示されていた指標が移動後に引き続き表示されます。To display default metrics in that new report, click the [!UICONTROL Add Metrics] drop-down list, then click [!UICONTROL Show Defaults].

* Clicking [!UICONTROL Clear Defaults] removes the default metrics for that report and reverts them to the original default metrics for that report ( [!UICONTROL Page Views] for props, and whatever you have set in Admin Tools for eVars).

