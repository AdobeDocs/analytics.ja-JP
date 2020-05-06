---
title: よくある質問
description: サードパーティプラットフォームからアドビ製品への移行について、よく寄せられる質問にお答えします。
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 75%

---


# よくある質問

**サードパーティプラットフォームからAdobe Analyticsに履歴データを移行する方法を教えてください。**

データの収集、処理および保存の方法は、分析プラットフォームごとに異なります。アドビでは、履歴データを移行するのではなく、Adobe Analytics 内でデータの収集と使用を開始する際に明確な切り替え日を設定することを推奨しています。多くの場合、会計年度の初日、暦年の初日、暦月の初日が切り替え日に設定されます。履歴データを表示するには、サードパーティプラットフォームにログインして、適切な履歴レポートを取得します。

アドビ製品への履歴データの移行をご検討の方は、担当のアカウントマネージャーにお問い合わせください。導入コンサルタントは貴社のご協力のもと、Google Analytics からデータを書き出し、アドビのデータ収集サーバーが取り込むことのできるデータソースに変換します。

アドビでは、履歴データの移行は複雑でコストのかかるプロセスなので推奨していません。訪問者の識別については、訪問者情報はプラットフォームによって異なる cookie や形式で保存されるので、アドビ製品にシームレスにポーティングできません。

**多くのレポートでセグメント化ドロップダウンを使用しています。How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. ワークスペースプロジェクト内の場合：

1. Ctrl キー（Windows）または Command キー（Mac）を押しながら、ドロップダウンに含めるコンポーネントをクリックします。ドロップダウンフィルターには、セグメントだけでなくコンポーネントも含めることができます。
2. コンポーネントのグループを、「ここにセグメントをドロップ」というラベルの付いたワークスペース領域にドラッグします。移動させる前に、Shift キーを押し続けます。

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**ディメンション値をクリックしてドリルダウンを表示しています。Analysis Workspace でこのワークフローを再現する方法を教えてください。**

また、 [!UICONTROL 分析ワークスペースのディメンション値は] 、分類の作業が容易になります。 左クリックではなく右クリックでアクセスします。 Right-click on a dimension value, click **[!UICONTROL Breakdown], then select the desired component. Ctrl キー（Windows）または Command キー（Mac）を押しながら各値をクリックすると、同じ分類を複数のディメンション値に適用できます。
