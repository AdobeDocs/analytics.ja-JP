---
description: 'AAM オーディエンスディメンションは Analytics の任意の場所で使用できます。統合されるセグメントはオーディエンス ID およびオーディエンス名と呼ばれる新しい Analytics ディメンションであり、Analytics によって収集される他のディメンションと同様に使用できます。データフィードでは、オーディエンスIDは「mc_audiences」列に保存されます。 現在、これらのディメンションは Data Workbench または Livestream では使用できません。オーディエンスディメンションの活用方法の例を以下に示します。 '
seo-description: 'AAM オーディエンスディメンションは Analytics の任意の場所で使用できます。統合されるセグメントはオーディエンス ID およびオーディエンス名と呼ばれる新しい Analytics ディメンションであり、Analytics によって収集される他のディメンションと同様に使用できます。データフィードでは、オーディエンスIDは「mc_audiences」列に保存されます。 現在、これらのディメンションは Data Workbench または Livestream では使用できません。オーディエンスディメンションの活用方法の例を以下に示します。 '
seo-title: Analytics でのオーディエンスデータの使用
solution: Experience Cloud
title: Analytics でのオーディエンスデータの使用
uuid: 203925fb-f070-441c-813a-43099cb9b2b9
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Analytics でのオーディエンスデータの使用

AAM オーディエンスディメンションは Analytics の任意の場所で使用できます。統合されるセグメントはオーディエンス ID およびオーディエンス名と呼ばれる新しい Analytics ディメンションであり、Analytics によって収集される他のディメンションと同様に使用できます。データフィードでは、オーディエンスIDは「mc_audiences」列に保存されます。 現在、これらのディメンションは Data Workbench または Livestream では使用できません。オーディエンスディメンションの活用方法の例としては、次のものがあります。

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

Analysis Workspace では、AAM セグメントは 2 つのディメンションとして表示されます。

1. Go to **[!UICONTROL Workspace]**.
1. From the list of **[!UICONTROL Dimensions]**, select the dimensions **[!UICONTROL Audience ID]** or **[!UICONTROL Audience Name]**. 名前は ID をわかりやすく分類するものです。

   ![](assets/aw-mcaudiences.png)

## セグメント比較 {#section_E72B80B6470C42D4B9B19BE90E6070A2}

[セグメント比較](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/segment-comparison.html)は、2 つのセグメントの統計的に最も重要な違いを検出します。オーディエンスデータは、次の2つの方法でセグメント比較に使用できます。1)を、比較対象の2つのセグメント、2)を「上位のディメンション項目」テーブルの項目として使用します。

1. **[!UICONTROL ワークスペース]**&#x200B;に移動して、左レールから&#x200B;**グメント比較[!UICONTROL パネルを選択します。]**

1. コンポーネント&#x200B;**メニューで[!UICONTROL オーディエンス名]を検索します。**

1. [!UICONTROL オーディエンス名]を開いて、関連するディメンション項目を表示します。
1. 比較するオーディエンスをセグメント比較ビルダーにドラッグします。
1. （オプション）：ほかのディメンション項目またはセグメントを選択することも可能です。最大 2 つを比較できます。
1. Click **[!UICONTROL Build]**.

   オーディエンスIDディメンションと名前ディメンションは、比較対象の2つのセグメントに対する追加のプロファイルデータなので、「上位のディメンション項目」テーブルに自動的に表示されます。

   ![](assets/aud-segcompare.png)

## Analysis Workspace でのカスタマージャーニー（フロー） {#section_FC30E5795C9D4539838E30FE11FAEA6E}

AAM セグメントのデータはヒットごとに Analytics に渡され、その時点での訪問者のオーディエンスのメンバーシップを表します。つまり、訪問者が1つのセグメント(例えば、「認識」)を使用し、後でより適切なセグメント(例："検討")。 Analysis Workspace で[フロー](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html)を使用すると、訪問者がオーディエンス間でたどるカスタマージャーニーを可視化できます。

1. **[!UICONTROL ワークスペース]**&#x200B;に移動して、左レールから「**フロー[!UICONTROL 」ビジュアライゼーションを選択します。]**

1. [!UICONTROL オーディエンス名]ディメンションをフロービルダーにドラッグします。
1. Click **[!UICONTROL Build]**.
1. （オプション）：ほかのディメンションをフロービジュアライゼーションにドラッグして、[ディメンション間フロー](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/multi-dimensional-flow.html)を作成します。

![](assets/flow-aamaudiences.png)

オーディエンスは[フォールアウトのビジュアライゼーション](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html)で使用することもできます。

## Analysis Workspace でのベン図のビジュアライゼーション {#section_E78AB764FB5047148B51DC1526B0DF89}

[ベン図のビジュアライゼーション](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/venn.html)には、最大 3 つのセグメントの重複が表示されます。

1. **[!UICONTROL ワークスペース]**&#x200B;に移動して、左レールから「**ベン[!UICONTROL 」ビジュアライゼーションを選択します。]**

1. コンポーネントメニューで[!UICONTROL オーディエンス名]を検索します。
1. [!UICONTROL オーディエンス名]を開いて、関連するディメンション項目を表示します。
1. 比較するオーディエンスをベン図ビルダーにドラッグします。
1. （オプション）：他のディメンション項目またはセグメントを選択することも可能です。最大 3 つを比較できます。
1. Click **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## セグメントビルダー {#section_2AA81852A1404AB894472CA8959461B6}

Analytics が収集した行動情報に加えて、オーディエンスディメンションを Analytics の[セグメントビルダー](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html)に取り込むことができます。

1. Go to  **[!UICONTROL Components]** &gt; **[!UICONTROL Segments]** .
1. 「**[!UICONTROL 追加]」をクリックして新しいセグメントを作成します。**
1. セグメントに名前を付けたら「[!UICONTROL オーディエンス名]」ディメンションを定義パネルにドラッグします。
1. （オプション）：他の条件をセグメントに追加します。
1. セグメントを保存します。

   ![](assets/aud-segbuilder.png)

## Reports &amp; Analytics と Report Builder {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. To view the Analytics report, go to  **[!UICONTROL Reports]** &gt; **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Audience ID Reports]** .
1. このフォルダーから、オーディエンス ID ディメンションとオーディエンス名ディメンションの両方にアクセスできます。

   ![](assets/mc-audiences.png)

