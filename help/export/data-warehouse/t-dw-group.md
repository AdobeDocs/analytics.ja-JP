---
description: 管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。
title: Data Warehouse ユーザーグループの追加
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Data Warehouse ユーザーグループの追加

管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー管理]**&#x200B;の順にクリックします。
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 以下のようなグループ情報を入力します。

   例：`Data Warehouse Access`。
1. Type a description in the **[!UICONTROL Group Description]** field.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Under [!UICONTROL Tools], enable **[!UICONTROL All Tools]**.

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. [!UICONTROL ユーザーログインの割り当て]で、ユーザーログインを追加します。
1. 「**[!UICONTROL グループの保存]**」をクリックします。

   このグループに追加されたユーザーが次回ログインしたときには、Data Warehouse オプションが [!UICONTROL Reports &amp; Analytics] メニューに追加されています。

   >[!NOTE]
   >
   >権限が競合する場合（2つのグループに割り当てられたユーザーのうち1つは機能へのアクセスを拒否し、もう1つは同じアクセスを許可するなど）、システムは権限を制限します。 data warehouse に対するアクセスが認められていないグループに所属するユーザーを、そのグループから削除する必要があります。

>[!MORELIKETHIS]
>
>* [グループ ](/help/admin/user-management2/c-user-groups/groups.md)

