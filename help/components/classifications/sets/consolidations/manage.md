---
title: 分類セットの統合マネージャー
description: 1 つ以上の分類セットを 1 つの分類セットに統合します。
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# 分類セットの統合マネージャー

類似のデータを含む分類セットが複数ある場合は、それらを 1 つの分類セットに統合できます。 2 つ以上の分類セットを統合すると、Adobeでは、個々の分類セットからのすべての分類データを含む新しい分類セットが生成されます。 統合は、同じ分類データを含む多数のレポートスイートまたはディメンションにデータをアップロードし、それらを 1 つのワークフローに結合する場合に役立ちます。 分類セット統合マネージャーを表示するには、Adobe Analyticsの製品管理者アクセス権が必要です。

**[!UICONTROL コンポーネント]**/**[!UICONTROL 分類セット]**/**[!UICONTROL 連結]**

統合が実行されると、元の分類セットが削除され、統合された分類セットが置き換えられます。 **[!UICONTROL 追加]** をクリックして [ 連結を作成 ](process.md) します。

## 分類セットをフィルタリング

分類セット統合マネージャーの左側には、目的の統合を見つけるためのフィルター設定があります。 フィルターアイコンをクリックすると、フィルター設定の表示が切り替わります。連結は、**[!UICONTROL ステータス]**、**[!UICONTROL 完了時間]** または **[!UICONTROL 作成時間]** でフィルタリングできます。

![ 分類セット統合フィルター ](../../assets/classification-set-consolidation-filters.png)

分類セットの連結マネージャの列の上に、次の追加のフィルタ・オプションが表示されます。

* **[!UICONTROL タイトルで検索]**：名前で統合を検索します。
* **列の表示/非表示**: [!UICONTROL &#x200B; 名前 &#x200B;] 以外の任意の列の表示を切り替えます。

## 分類セット統合マネージャーの列

分類セット連結マネージャでは、次の列を使用できます。

* **[!UICONTROL 名前]**：統合の名前。
* **[!UICONTROL 現在のジョブ]**：現在のジョブ。<!-- todo: better description -->
* **[!UICONTROL ステータス]**：連結のステータス。<!-- todo: get list of possible statuses -->
* **[!UICONTROL 作成日]**：連結が作成された日時。
* **[!UICONTROL 完了日]**：連結が完了（または失敗）した日時。
