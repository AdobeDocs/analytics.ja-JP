---
description: 注文の促進を支援するマーケティングチャネルを示す指標の作成方法について説明します。これは、任意のディメンションや興味の成功イベントに適応させることができます。
title: 注文支援指標
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 25%

---

# より複雑な計算指標の作成

この記事では、計算指標のより複雑な例について説明します。 この計算指標は、どのマーケティングチャネルが注文の促進に役立つかを示します。 このタイプの計算指標は、任意のディメンションまたは成功イベントに適応させることができます。

1. [ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) の説明に従って、計算指標の作成を開始します。

1. 計算指標ビルダーで、指標に `Assisted Orders` などの名前を付けます。

1. **[!UICONTROL 指標]** コンポーネントから **[!UICONTROL オンライン注文]** 指標を選択し、指標を **[!UICONTROL 定義]** 領域にドラッグします。

   1. 指標の ![ 設定 ](/help/assets/icons/Setting.svg) を選択します。
   1. **[!UICONTROL デフォルト以外のアトリビューションモデルを使用]** を選択します。
   1. **[!UICONTROL 列アトリビューションモデル]** のアトリビューションモデルを調整します。
      1. **[!UICONTROL モデル]** に **[!UICONTROL カスタム]** を選択します。 **[!UICONTROL スターター]** を `0` に、**[!UICONTROL プレーヤー]** を `100` に、**[!UICONTROL クローザー]** を `0` に設定します。
      1. **[!UICONTROL コンテナ]** の **[!UICONTROL 訪問者]** を選択します。
      1. **[!UICONTROL ルックバックウィンドウ]** に **[!UICONTROL 30 日]** を選択します。

      1. 「**[!UICONTROL 適用]**」を選択します。

      ![ 列アトリビューションモデル ](assets/complex-calculated-metric.png)

1. 「**[!UICONTROL 保存]**」を選択して、計算指標を保存します。

計算指標を使用するには：

1. Analysis Workspaceで、**[!UICONTROL マーケティングチャネル]** ディメンション、**[!UICONTROL オンライン注文]** および新しい **[!UICONTROL 支援オンライン注文]** 指標を使用してフリーフォームテーブルを作成します。

   ![ マーケティングチャネル支援オンライン注文 ](assets/marketing-channel-assists.png)

1. （任意） [ 計算指標の共有 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) の説明に従って、組織の他のユーザーと指標を共有します。

これで、どのマーケティングチャネルが注文の促進を支援したかを簡単に示すことができます。または、フリーフォームテーブルで指標を右クリックして、テーブルから直接アトリビューションモデルを調整できます。
