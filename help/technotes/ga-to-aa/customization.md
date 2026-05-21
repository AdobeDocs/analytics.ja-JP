---
title: Adobe Analytics でのレポートのカスタマイズ
description: Adobe Analytics でレポートをカスタマイズする方法について説明します。
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
TQID: https://experienceleague.adobe.com/vvVKR7JKV12zgIic0rso4OihH5kyAoZBV983R3VmOic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 94%

---

# レポートのカスタマイズ

Google Analytics などのサードパーティプラットフォームでは、複数のカスタマイズオプションを使用できます。 これらのオプションにより、ダッシュボード、カスタムレポート、保存されたレポート、カスタムアラートを作成できます。 Analysis Workspace では空白のキャンバスからレポートを作成できるので、カスタマイズオプションの多くはツールに直接組み込まれます。

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

[!UICONTROL Analysis Workspace] では、レポートニーズに最適な方法でデータを表示するための、さらに多くのビジュアライゼーションオプションを用意しています。 詳しくは、分析ユーザーガイドの「[Analysis Workspace のビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)」を参照してください。

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

Google Analytics でカスタムレポートを作成するときに必要なフィールドは、Analysis Workspace でビジュアライゼーションを作成する際のワークフローと似ています。 ディメンション、指標およびフィルターの定義も類似しています。 Analysis Workspace では、リストからディメンションと指標を選択する代わりに、ディメンションと指標をフリーフォームテーブルにドラッグします。

### カスタムレポートの計算指標

カスタムレポートは、Google Analytics で計算指標を使用できる数少ない項目の 1 つです。 Analysis Workspace はキャンバスのような役割を果たすので、計算指標は任意のコンテキストで遡及的に機能します。

計算指標を作成するには：

1. 指標リストの近くにある「**+**」アイコンをクリックし、[!UICONTROL 計算指標ビルダー]を開きます。
2. 計算指標に名前を付け、形式を指定します。
3. 指標コンポーネントをに定義エリアにドラッグし、各コンポーネント間のドロップダウンリストを使用してオペレーターを指定します。
4. 計算指標に適切な数式を追加したら、「保存」をクリックしてワークスペースに戻ります。
5. 新しく定義した計算指標をワークスペースにドラッグします。

   [計算指標](/help/components/calculated-metrics/cm-overview.md)について詳しくは、コンポーネントユーザーガイドを参照してください。

## カスタムアラート

アラートは、Adobe Analytics と Google Analytics の両方で利用できます。 Adobe Analytics では、ヘッダーナビゲーションメニューから&#x200B;*[!UICONTROL コンポーネント]*／*[!UICONTROL アラート]*&#x200B;に移動します。 詳しくは、コンポーネントユーザーガイドの[&#x200B; アラートの概要](/help/components/alerts/alerts-overview.md)を参照してください。
