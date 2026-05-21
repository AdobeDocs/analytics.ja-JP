---
title: 複数のレポートスイート
description: 1つのAnalysis Workspace プロジェクトで複数のレポートスイートを操作する方法について説明します。
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
TQID: https://experienceleague.adobe.com/IrWsvooPWqWmbDAD-70CgI71gEPJCQY-1wFHFyuJsyc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 69%

---

# 複数のレポートスイート

複数のレポートスイートのデータを使用して、Analysis Workspaceでプロジェクトを作成できます。 レポートスイートはパネルレベルで選択されるので、同じWorkspace プロジェクト内の各パネルに対して異なるレポートスイートを選択できます。

この機能は、次の場合に便利です。

* 2 つの異なる地域のデータや、2 つの異なるレポートスイート内のデータを比較する。 テーブルとビジュアライゼーションを作成し、データを並べて比較できます。

* 指標とビジュアライゼーションのダッシュボードを作成して、他の組織に報告する。 同じプロジェクト内の様々なレポートスイートからデータを取得できます。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [複数のレポートスイート &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## レポートスイートをすべてのパネルに適用

任意のパネルのヘッダーを右クリックし、「**[!UICONTROL レポートスイートをすべてのパネルに適用]**」を選択すると、レポートスイートをすべてのパネルに一度に適用できます。

![](assets/apply-rs-all-panels.png)

## アクティブなパネル

アクティブなパネは、明るい青色の境界線で囲まれていることで認識できます。 パネル内を選択するだけで、そのパネルをアクティブなパネルに変えることができます。

>[!TIP]
>
>アクティブなパネルと同じレポートスイート内の任意のパネルにドラッグ＆ドロップできます。 同じレポートスイートの非アクティブなパネル内にドラッグすると、パネルがアクティブになります。
>

## 複数のレポートスイートの操作

![](assets/mrs-ui.png)

1. 2 つ以上のパネルを含む新しいプロジェクトを Workspace で作成します。

1. コンポーネント（指標、ディメンション、セグメント、日付範囲）をパネルにドラッグ＆ドロップします。 レポートスイート固有のデータとビジュアライゼーションがパネルに含まれていることを確認します。


   >[!NOTE]
   >
   >プロジェクトに含まれているコンポーネントの一部がレポートスイートに含まれていないプロジェクトをロードする（またはレポートスイートに切り替える）と、バナーが表示される場合があります。 欠落しているコンポーネントが表示されます。 必要な指標／ディメンションに権限を設定するには、[次の手順](/help/admin/admin-console/permissions/product-profile.md)に従います。
   >

   ![](assets/incompat-rs.png)

   この非互換性に対応するオプションは 3 つあります。
   * 必要なディメンション／指標の有効化。
   * レポートスイートの変更。
   * 一部のコンポーネントが欠落したままで続行する。 これにより、これらのコンポーネントにはデータが生成されず、ビジュアライゼーションが空白になります。

1. パネルを別のレポートスイートに変更し、新しいレポートスイートに基づいてコンポーネントのラベル（現在アクティブなレポートスイート）と一覧表示されるコンポーネントが更新されていることを確認します。

1. 非アクティブなパネルをアクティブなパネルに切り替えるには、（`shift` をドラッグしながら）キーボードショートカットを使用します。

1. （任意）他の Analytics コンポーネントビルダーに移動して、これらのビルダーが、以下を示すレポートスイートラベルが表示されることを確認します。

   * セグメントが作成される場所：[&#x200B; セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md)。
   * 計算指標が作成される場所：[計算指標ビルダー](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)。
   * アラートが作成される場所：[&#x200B; アラートビルダー](/help/components/alerts/alert-builder.md)。
