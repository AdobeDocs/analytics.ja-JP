---
title: Adobe Analytics でのレポートのカスタマイズ
description: Adobe Analytics でレポートをカスタマイズする方法について説明します。
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 75%

---


# レポートのカスタマイズ

Google Analytics などのサードパーティプラットフォームでは、複数のカスタマイズオプションを使用できます。これらのオプションにより、ダッシュボード、カスタムレポート、保存されたレポート、カスタムアラートを作成できます。Analysis Workspace では空白のキャンバスからレポートを作成できるので、カスタマイズオプションの多くはツールに直接組み込まれます。

This page assumes the user has a basic knowledge of using [!UICONTROL Analysis Workspace]. Adobe Analytics のツールを初めて使用する場合は、[Google Analytics ユーザー向け：Analysis Workspace での基本レポートの作成方法](reports/create-report.md)を参照してください。

## ダッシュボード

[!UICONTROL 分析ワークスペース] ・アーキテクチャは、ダッシュボード・ウィジェットの概念と似た構造を持っています。 [!UICONTROL 分析ワークスペース内のプロジェクト] は、Google Analyticsのダッシュボードとほぼ同じです。 [!UICONTROL 分析ワークスペースのビジュアライゼーション] は、Google Analyticsのウィジェットとほぼ同じです。

### プロジェクトへのコンテンツの追加

1. Click the [!UICONTROL Visualizations] icon on the left and drag the desired visualization onto the workspace.
2. Click the [!UICONTROL Components] icon on the left and drag the desired dimensions and metrics onto the visualization to populate it with data.
3. ビジュアライゼーションの端をドラッグしてサイズを変更し、ビジュアライゼーションのタイトルをドラッグして移動します。

All Google Analytics widgets are available in [!UICONTROL Analysis Workspace]:

* **指標ウィジェット**&#x200B;は、数の概要ビジュアライゼーションとほぼ同じ役割を果たします。
* **タイムラインウィジェット**&#x200B;は、線ビジュアライゼーションとほぼ同じ役割を果たします。
* **ジオマップウィジェット**&#x200B;は、マップビジュアライゼーションとほぼ同じ役割を果たします。
* **テーブルウィジェット**&#x200B;は、フリーフォームテーブルビジュアライゼーションとほぼ同じ役割を果たします。
* **円グラフウィジェット**&#x200B;は、ドーナツグラフビジュアライゼーションとほぼ同じ役割を果たします。
* **棒グラフウィジェット**&#x200B;は、棒グラフビジュアライゼーションとほぼ同じ役割を果たします。

[!UICONTROL Analysis Workspace では、レポートニーズに最適な方法でデータを表示するための、さらに多くのビジュアライゼーションオプションを用意しています。]詳しくは、分析ユーザーガイドの「[Analysis Workspace のビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)」を参照してください。

### プロジェクトの共有

プロジェクトへのコンテンツの追加が完了すると、プロジェクトを共有できます。

* To share the project with your colleagues, go to **[!UICONTROL Share > Share Project]**. 受信者は、組織内で Adobe Analytics アカウントを持つその他のユーザーです。
* To share your project via a link, go to **[!UICONTROL Share > Get Project Link]**. この場合も、組織内の Adobe Analytics アカウントにログインする必要があります。

### プロジェクトのエクスポート

In addition to PDF, [!UICONTROL Analysis Workspace] offers a CSV export.

1. *[!UICONTROL 共有]*／*[!UICONTROL ファイルを今すぐ送信]*&#x200B;をクリックし、モーダルウィンドウを開きます。
2. ファイルタイプと受信者を指定します。
3. 「[!UICONTROL 今すぐ送信]」をクリックします。

## カスタムレポート

Google Analytics でカスタムレポートを作成するときに必要なフィールドは、Analysis Workspace でビジュアライゼーションを作成する際のワークフローと似ています。ディメンション、指標およびフィルターの定義も類似しています。Analysis Workspace では、リストからディメンションと指標を選択する代わりに、ディメンションと指標をフリーフォームテーブルにドラッグします。

### カスタムレポートの計算指標

カスタムレポートは、Google Analytics で計算指標を使用できる数少ない項目の 1 つです。Analysis Workspace はキャンバスのような役割を果たすので、計算指標は任意のコンテキストで遡及的に機能します。

計算指標を作成するには：

1. Click the **+** icon near the metric list to open the [!UICONTROL Calculated Metric Builder].
2. 計算指標に名前を付け、形式を指定します。
3. 指標コンポーネントを定義領域にドラッグし、各コンポーネント間のドロップダウンを使用して演算子を指定します。
4. 計算指標に適切な数式を追加したら、「保存」をクリックしてワークスペースに戻ります。
5. 新しく定義した計算指標をワークスペースにドラッグします。

   [計算指標](/help/components/c-calcmetrics/cm-overview.md)について詳しくは、コンポーネントユーザーガイドを参照してください。

## カスタムアラート

アラートは、Adobe Analytics と Google Analytics の両方で利用できます。Adobe Analytics では、ヘッダーナビゲーションメニューから&#x200B;*[!UICONTROL コンポーネント]*／*[!UICONTROL アラート]*&#x200B;に移動します。詳しくは、コンポーネントユーザーガイドの「[インテリジェントアラート](/help/components/c-alerts/intellligent-alerts.md)」を参照してください。
