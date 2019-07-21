---
description: 管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。
seo-description: 管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。
seo-title: Data Warehouse ユーザーグループの追加
solution: Analytics
title: Data Warehouse ユーザーグループの追加
topic: Data Warehouse
uuid: d89294db- caa3-4044- b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Data Warehouse ユーザーグループの追加

管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。

1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL ユーザー管理]**&#x200B;の順にクリックします。
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 以下のようなグループ情報を入力します。

   例：`Data Warehouse Access`。
1. **[!UICONTROL [グループの説明]** ]フィールドに説明を入力します。
1. **[!UICONTROL 「レポートスイートへのアクセス]** 」セクションで、グループメンバーにアクセスできるレポートスイートを選択します。
1. [!UICONTROL 「ツール]»の下の??«すべてのツール??****

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. [!UICONTROL ユーザーログインの割り当て]で、ユーザーログインを追加します。
1. Click **[!UICONTROL Save Group]**.

   このグループに追加されたユーザーが次回ログインしたときには、Data Warehouse オプションが [!UICONTROL Reports &amp; Analytics] メニューに追加されています。

   >[!NOTE]
   >
   >権限が競合している場合（ユーザーが2つのグループに割り当てられており、そのうちの1つは機能へのアクセスを拒否し、もう1つは同じアクセスを許可している場合）、システムは権限を制限します。data warehouse に対するアクセスが認められていないグループに所属するユーザーを、そのグループから削除する必要があります。

>[!MORE_LIKE_THIS]
>
>* [グループ ](/help/admin/user-management2/c-user-groups/groups.md)

