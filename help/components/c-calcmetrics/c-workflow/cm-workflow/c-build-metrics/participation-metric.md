---
description: 計算指標ビルダーを使用して、誰でもパーティシペーション指標を作成できます。
title: パーティシペーション指標
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
exl-id: bef185d6-72c0-4068-80f8-57261369573f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# パーティシペーション指標

簡単な使用例を示します。コンテンツ所有者が、注文を含む訪問に貢献した（関係した）ページを判断したいとします。その方法を次に示します。

>[!NOTE]
>
>以前は管理ツールからこれをおこなう必要がありました。引き続き管理ツールでパーティシペーション指標を有効にできますが、カスタムイベント 1 ～ 100 に対してのみ可能です。

簡単な使用例を示します。コンテンツ所有者が、電子メールのサインアップを含む訪問に貢献した（関係した）ページを判断したいとします。その方法を次に示します。

1. 計算指標ビルダーで新しい指標を作成します。
1. 成功イベント「注文」を「定義」キャンバスにドラッグします。
1. [設定](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)ギアアイコンの下にある、そのイベントの&#x200B;**[!UICONTROL アトリビューションモデル]**&#x200B;を&#x200B;**[!UICONTROL パーティシペーション]**&#x200B;に変更します。「**[!UICONTROL 訪問]**」のルックバックを選択します。定義は次のようになるはずです。

   ![](assets/participation.png)

1. 指標を保存します。
1. **[!UICONTROL ページ]**&#x200B;レポートで計算指標を使用します。

   ![](assets/participation-pages.png)

1. （オプション）指標を組織内の他のユーザーと共有します。
