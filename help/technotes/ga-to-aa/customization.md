---
title: Adobe Analyticsでのレポートのカスタマイズ
description: Adobe Analyticsでレポートをカスタマイズする方法について説明します
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# レポートのカスタマイズ

Googleアナリティクスなどのサードパーティプラットフォームでは、いくつかのカスタマイズオプションを使用できます。これらのカスタマイズにより、ユーザーはダッシュボード、カスタムレポート、保存されたレポートおよびカスタムアラートを作成できます。Analysis Workspaceでは、空白のキャンバスからレポートを作成できるので、ほとんどのカスタマイズはツールに直接組み込まれています。

このページでは、Analysis Workspaceの使用に関する基本的な知識があると想定しています。See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## ダッシュボード

Analysis Workspaceのアーキテクチャは、ダッシュボードウィジェットの概念と同様に構築されています。Analysis Workspaceのプロジェクトは、Google Analyticsのダッシュボードとほぼ同じです。Analysis Workspaceのビジュアライゼーションは、Google Analyticsのウィジェットとほぼ同じです。

### プロジェクトへのコンテンツの追加

1. 左側のビジュアライゼーションアイコンをクリックし、目的のビジュアライゼーションをワークスペースにドラッグします。
2. 左側のコンポーネントアイコンをクリックし、目的のディメンションおよび指標をビジュアライゼーションにドラッグして、データを入力します。
3. ビジュアライゼーションの端をドラッグしてサイズを変更し、ビジュアライゼーションのタイトルをドラッグして移動します。

すべてのGoogle Analyticsウィジェットは、Analysis Workspaceで利用できます。

* **指標ウィジェット** は、概要番号ビジュアライゼーションとほぼ同じです。
* **タイムラインウィジェット** は、線のビジュアライゼーションとほぼ同じです。
* **ジオマップウィジェット** は、マップのビジュアライゼーションとほぼ同じです。
* **テーブルウィジェット** は、ほぼフリーフォームテーブルのビジュアライゼーションとほぼ同じです。
* **円ウィジェット** は、ドーナツグラフのビジュアライゼーションとほぼ同じです。
* **バーウィジェット** はバーのビジュアライゼーションとほぼ同じです。

Analysis Workspaceには、レポートのニーズに最適なデータを表示するための、より多くの視覚化オプションが用意されています。See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### プロジェクトの共有

プロジェクトへのコンテンツの追加が完了したら、コンテンツを共有できます。

* プロジェクトを同僚と共有するには、共有/プロジェクトを共有に移動します。受信者は、Adobe Analyticsアカウントを持つ組織内の他のユーザーです。
* リンクを使用してプロジェクトを共有するには、共有/プロジェクトリンクを取得に移動します。ただし、組織内でAdobe Analyticsにログインする必要があります。

### プロジェクトの書き出し

Analysis Workspaceは、PDFに加えてCSVエクスポートを提供します。

1. *[!UICONTROL 共有]* /ファイルを今 **&#x200B;すぐ送信をクリックして、モーダルウィンドウを開きます。
2. ファイルの種類と受信者を指定します。
3. Click [!UICONTROL Send Now].

## カスタムレポート

Google Analyticsでカスタムレポートを作成する場合、必要なフィールドはワークスペース内のビジュアライゼーションの作成のワークフローと似ています。ディメンション、指標およびフィルターの定義は、プラットフォーム間で似ています。Analysis Workspaceでは、リストからディメンションや指標を選択する代わりに、ディメンションと指標がフリーフォームテーブルにドラッグされます。

### カスタムレポートの計算指標

カスタムレポートは、Google Analyticsの一部の領域の1つで、計算指標を使用できます。Analysis Workspaceはキャンバスのように動作するので、計算指標はさかのぼって、任意のコンテキストで動作します。

計算指標を作成するには：

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. 計算指標に名前を付け、形式を指定します。
3. 指標コンポーネントを定義領域にドラッグし、各コンポーネント間のドロップダウンを使用して演算子を指定します。
4. 計算指標に目的の数式が表示されたら、[保存]をクリックしてワークスペースに戻ります。
5. 新しく定義した計算指標をワークスペースにドラッグします。

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## カスタムアラート

アラートは両方のプラットフォームで使用できます。In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
