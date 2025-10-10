---
description: 組織全体、グループまたは個々のユーザーと指標を共有する方法を説明します。
title: 計算指標の共有
feature: Calculated Metrics
exl-id: 99817d6f-d0d7-4e1b-88a7-b1465e2f8812
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---

# 計算指標の共有

[&#x200B; 計算指標マネージャー &#x200B;](cm-manager.md) で、計算指標を共有できます。 権限に応じて、計算指標を組織全体、グループまたは個々のユーザーと共有できます。

* **管理者**：管理者は、計算指標を組織全体、組織内のグループおよび個々のユーザーと共有できます。 詳しくは、[Admin Console のドキュメント](https://helpx.adobe.com/jp/enterprise/using/manage-products.html)を参照してください。
* **管理者以外**：管理者以外のユーザーは、自身が作成した計算指標を共有でき、個々のユーザーとのみ共有できます。

1 つ以上の計算指標を共有するには：

1. [&#x200B; 計算指標マネージャー &#x200B;](cm-manager.md) で、共有する計算指標を 1 つ以上選択します。
1. アクションバーの「![&#x200B; 共有 &#x200B;](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共有]**」を選択します。
1. **[!UICONTROL 計算指標を共有]** ダイアログで、次の手順を実行します。

   ![&#x200B; 計算指標を共有ダイアログ &#x200B;](assets/share-calculated-metrics-dialog.png)

   1. （オプション） ![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg) を使用して *個人またはグループを検索*、計算指標を共有するグループまたは個人のリストを制限します。

   1. 「**[!UICONTROL 組織]**」セクションまたは「**[!UICONTROL グループ]**」セクションから 1 つ以上のオプションを選択するか、1 人または複数の個人を検索して選択します。 使用できるオプションは、の役割によって異なります。

   1. 「**[!UICONTROL 保存]**」を選択して、計算指標を共有します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

## ベストプラクティス

以下は、計算指標を共有する必要がある場合と、計算指標を共有する必要がある場合のベストプラクティスです。

* 管理者は、組織内の誰かが計算指標を使用するのに慣れていると確信している場合にのみ、計算指標を「すべて」と共有します。 また、これらの計算指標のお気に入りを検討することもできます。 詳しくは [&#x200B; 計算指標をお気に入りとしてマーク &#x200B;](cm-favorite.md) を参照してください。

* 計算指標が特定のグループのユーザーにビジネス価値を提供する場合、管理者はそのグループと計算指標を共有します。

* 管理者または個々のユーザーは、計算指標を 1 人以上の個人と共有して計算指標を検証します。 セグメントが役に立つことが証明されない場合は、計算指標を削除できます。

<!--
Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin Console. |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the checkbox to the left of any metrics that you want to share. 

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)
   
   The Share Calculated metric dialog box displays.

   ![](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calculated-metrics/workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.
-->
