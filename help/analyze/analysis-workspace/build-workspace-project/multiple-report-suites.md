---
title: 複数のレポートスイート
description: 1 つのAnalysis Workspace プロジェクトで複数のレポートスイートを操作する方法を説明します。
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 71%

---

# 複数のレポートスイート

複数のレポートスイートのデータを使用して、Analysis Workspaceでプロジェクトを作成できます。 レポートスイートはパネルレベルで選択されるので、同じWorkspace プロジェクト内のパネルごとに異なるレポートスイートを選択できます。

この機能は次の場合に役立ちます。

* 2 つの異なる地域のデータや、2 つの異なるレポートスイート内のデータを比較する。テーブルとビジュアライゼーションを作成し、データを並べて比較できます。

* 指標とビジュアライゼーションのダッシュボードを作成して、他の組織に報告する。様々なレポートスイートから同じプロジェクトのにデータを取り込むことができます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 複数のレポートスイート ](https://video.tv.adobe.com/v/37010?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## レポートスイートをすべてのパネルに適用

任意のパネルのヘッダーを右クリックし、「**[!UICONTROL レポートスイートをすべてのパネルに適用]**」を選択すると、レポートスイートをすべてのパネルに一度に適用できます。

![](assets/apply-rs-all-panels.png)

## アクティブなパネル

アクティブなパネは、明るい青色の境界線で囲まれていることで認識できます。パネル内を選択するだけで、そのパネルがアクティブなパネルになります。

>[!TIP]
>
>アクティブなパネルと同じレポートスイート内の任意のパネルにドラッグ＆ドロップできます。同じレポートスイートの非アクティブなパネル内にドラッグすると、パネルがアクティブになります。
>

## 複数のレポートスイートの操作

![](assets/mrs-ui.png)

1. 2 つ以上のパネルを含む新しいプロジェクトを Workspace で作成します。

1. コンポーネント（指標、ディメンション、セグメント、日付範囲）をパネルにドラッグ＆ドロップします。レポートスイート固有のデータとビジュアライゼーションがパネルに含まれていることを確認します。


   >[!NOTE]
   >
   >プロジェクトに含まれているコンポーネントの一部がレポートスイートに含まれていないプロジェクトをロードする（またはレポートスイートに切り替える）と、バナーが表示される場合があります。欠落しているコンポーネントが表示されます。必要な指標／ディメンションに権限を設定するには、[次の手順](/help/admin/admin-console/permissions/product-profile.md)に従います。
   >

   ![](assets/incompat-rs.png)

   この非互換性に対応するオプションは 3 つあります。
   * 必要なディメンション／指標の有効化。
   * レポートスイートの変更。
   * 一部のコンポーネントが欠落したままで続行する。これにより、これらのコンポーネントにはデータが生成されず、ビジュアライゼーションが空白になります。

1. パネルを別のレポートスイートに変更し、新しいレポートスイートに基づいてコンポーネントのラベル（現在アクティブなレポートスイート）と一覧表示されるコンポーネントが更新されていることを確認します。

1. 非アクティブなパネルをアクティブなパネルに切り替えるには、（`shift` をドラッグしながら）キーボードショートカットを使用します。

1. （任意）他の Analytics コンポーネントビルダーに移動して、これらのビルダーが、以下を示すレポートスイートラベルが表示されることを確認します。

   * セグメントの作成場所：[ セグメントビルダー ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=ja)。
   * 計算指標が作成される場所：[ 計算指標ビルダー ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ja)。
   * アラートの作成場所：[ アラートビルダー ](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html?lang=ja)。
