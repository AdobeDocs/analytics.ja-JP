---
description: 計算指標ビルダーを使用すると、誰でもパーティシペーション指標を作成できます。
title: パーティシペーション指標
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# パーティシペーション指標

簡単な使用例を示します。コンテンツ所有者が、注文を含む訪問に貢献した（関係した）ページを判断したいとします。その方法を次に示します。

>[!NOTE]以前は管理ツールからこれをおこなう必要がありました。引き続き管理ツールでパーティシペーション指標を有効にできますが、カスタムイベント1 ～ 100の場合のみ有効です。

簡単な使用例を示します。コンテンツ所有者が、電子メールのサインアップを含む訪問に貢献した（関係した）ページを判断したいとします。その方法を次に示します。

1. 計算指標ビルダーで新しい指標を作成します。
1. 成功イベント「注文」を「定義」キャンバスにドラッグします。
1. Change the [attribution model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. 「Lookback」を **[!UICONTROL Visit]** 選択します。 定義は次のようになります。

   ![](assets/participation.png)

1. 指標を保存します。
1. Use the calculated metric in a **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. （オプション）指標を組織内の他のユーザーと共有します。

