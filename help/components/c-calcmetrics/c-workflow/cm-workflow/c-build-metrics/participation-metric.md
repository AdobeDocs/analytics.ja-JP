---
description: 計算指標ビルダーを使用して、誰でもパーティシペーション指標を作成できます。
title: パーティシエーション指標
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 37%

---

# 「パーティシペーション」指標の作成

次の情報では、注文を含む訪問に貢献（または参加）したページを示す指標の作成方法を説明します。

このタイプの情報は、あらゆるコンテンツ所有者に役立つ可能性があります。

>[!NOTE]
>
>管理ツールではパーティシペーション指標を有効にできますが、有効にできるのは 1 ～ 100 のカスタムイベントのみです。

1. [ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) の説明に従って、計算指標の作成を開始します。

1. 計算指標ビルダーで、指標に「パーティシペーション」という名前を付けます。

1. 成功イベント「注文」を「定義」キャンバスにドラッグします。

1. [設定](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)ギアアイコンの下にある、そのイベントの&#x200B;**[!UICONTROL アトリビューションモデル]**&#x200B;を&#x200B;**[!UICONTROL パーティシペーション]**&#x200B;に変更します。「**[!UICONTROL 訪問]**」のルックバックを選択します。定義は次のようになるはずです。

   ![](assets/participation.png)

1. 「[!UICONTROL **保存**]」を選択して、指標を保存します。

1. **[!UICONTROL ページ]**&#x200B;レポートで計算指標を使用します。

   ![](assets/participation-pages.png)

1. （任意） [ 計算指標の共有 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) の説明に従って、組織の他のユーザーと指標を共有します。
