---
title: Adobe Analytics でのレポートのカスタマイズ
description: Adobe Analytics でレポートをカスタマイズする方法について説明します。
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '606'
ht-degree: 100%

---

# レポートのカスタマイズ

Google Analytics などのサードパーティプラットフォームでは、複数のカスタマイズオプションを使用できます。これらのオプションにより、ダッシュボード、カスタムレポート、保存されたレポート、カスタムアラートを作成できます。Analysis Workspace では空白のキャンバスからレポートを作成できるので、カスタマイズオプションの多くはツールに直接組み込まれます。

このページでは、ユーザーが [!UICONTROL Analysis Workspace] の使用に関する基本的な知識を持っていることを前提としています。 Adobe Analytics のツールを初めて使用する場合は、[Google Analytics ユーザー向け：Analysis Workspace での基本レポートの作成方法](reports/create-report.md)を参照してください。

## ダッシュボード

[!UICONTROL Analysis Workspace] のアーキテクチャは、ダッシュボードウィジェットの概念と同様に構築されています。 [!UICONTROL Analysis Workspace] のプロジェクトは、Google Analytics のダッシュボードとほぼ同じ役割を果たします。 また、[!UICONTROL Analysis Workspace] のビジュアライゼーションは Google Analytics のウィジェットとほぼ同じ役割を果たします。

### プロジェクトへのコンテンツの追加

1. 左側の[!UICONTROL ビジュアライゼーション]アイコンをクリックし、目的のビジュアライゼーションをワークスペースにドラッグします。
2. 左側の[!UICONTROL コンポーネント]アイコンをクリックし、目的のディメンションと指標をビジュアライゼーションにドラッグして、データを入力します。
3. ビジュアライゼーションの端をドラッグしてサイズを変更し、ビジュアライゼーションのタイトルをドラッグして移動します。

[!UICONTROL Analysis Workspace] では、すべての Google Analytics ウィジェットを使用できます。

* **指標ウィジェット**&#x200B;は、[!UICONTROL 数の概要]ビジュアライゼーションとほぼ同じ役割を果たします。
* **タイムラインウィジェット**&#x200B;は、[!UICONTROL 線]ビジュアライゼーションとほぼ同じ役割を果たします。
* **ジオマップウィジェット**&#x200B;は、[!UICONTROL マップ]ビジュアライゼーションとほぼ同じ役割を果たします。
* **テーブルウィジェット**&#x200B;は、[!UICONTROL フリーフォームテーブル]ビジュアライゼーションとほぼ同じ役割を果たします。
* **円グラフウィジェット**&#x200B;は、[!UICONTROL ドーナツグラフ]ビジュアライゼーションとほぼ同じ役割を果たします。
* **棒グラフウィジェット**&#x200B;は、[!UICONTROL 棒グラフ]ビジュアライゼーションとほぼ同じ役割を果たします。

[!UICONTROL Analysis Workspace] では、レポートニーズに最適な方法でデータを表示するための、さらに多くのビジュアライゼーションオプションを用意しています。詳しくは、分析ユーザーガイドの「[Analysis Workspace のビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)」を参照してください。

### プロジェクトの共有

プロジェクトへのコンテンツの追加が完了すると、プロジェクトを共有できます。

* プロジェクトをチームメンバーと共有するには、**[!UICONTROL 共有／プロジェクトを共有]**&#x200B;に移動します。 受信者は、組織内で Adobe Analytics アカウントを持つその他のユーザーです。
* リンクを使用してプロジェクトを共有するには、**[!UICONTROL 共有／プロジェクトリンクを取得]**&#x200B;に移動します。 この場合も、組織内の Adobe Analytics アカウントにログインする必要があります。

### プロジェクトのエクスポート

[!UICONTROL Analysis Workspace] は、PDF だけでなく CSV 形式で書き出しにも対応しています。

1. *[!UICONTROL 共有]*／*[!UICONTROL ファイルを今すぐ送信]*&#x200B;をクリックし、モーダルウィンドウを開きます。
2. ファイルタイプと受信者を指定します。
3. 「[!UICONTROL 今すぐ送信]」をクリックします。

## カスタムレポート

Google Analytics でカスタムレポートを作成するときに必要なフィールドは、Analysis Workspace でビジュアライゼーションを作成する際のワークフローと似ています。ディメンション、指標およびフィルターの定義も類似しています。Analysis Workspace では、リストからディメンションと指標を選択する代わりに、ディメンションと指標をフリーフォームテーブルにドラッグします。

### カスタムレポートの計算指標

カスタムレポートは、Google Analytics で計算指標を使用できる数少ない項目の 1 つです。Analysis Workspace はキャンバスのような役割を果たすので、計算指標は任意のコンテキストで遡及的に機能します。

計算指標を作成するには：

1. 指標リストの近くにある「**+**」アイコンをクリックし、[!UICONTROL 計算指標ビルダー]を開きます。
2. 計算指標に名前を付け、形式を指定します。
3. 指標コンポーネントを定義領域にドラッグし、各コンポーネント間のドロップダウンを使用して演算子を指定します。
4. 計算指標に適切な数式を追加したら、「保存」をクリックしてワークスペースに戻ります。
5. 新しく定義した計算指標をワークスペースにドラッグします。

   [計算指標](/help/components/c-calcmetrics/cm-overview.md)について詳しくは、コンポーネントユーザーガイドを参照してください。

## カスタムアラート

アラートは、Adobe Analytics と Google Analytics の両方で利用できます。Adobe Analytics では、ヘッダーナビゲーションメニューから&#x200B;*[!UICONTROL コンポーネント]*／*[!UICONTROL アラート]*&#x200B;に移動します。詳しくは、コンポーネントユーザーガイドの「[インテリジェントアラート](/help/components/c-alerts/intellligent-alerts.md)」を参照してください。
