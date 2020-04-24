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

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. クリック **[!UICONTROL Edit Groups]**.
1. クリック **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 以下のようなグループ情報を入力します。

   例：`Data Warehouse Access`。
1. フィールドに説明を入力 **[!UICONTROL Group Description]** します。
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. の下で、 [!UICONTROL Tools]を有効にしま **[!UICONTROL All Tools]**&#x200B;す。

   または、をクリックし **[!UICONTROL Customize]**&#x200B;てから有効にしま **[!UICONTROL Custom Data Warehouse Report]**&#x200B;す。

1. で、目 [!UICONTROL Assign User Logins]的のユーザーログインを追加します。
1. クリック **[!UICONTROL Save Group]**.

   このグループに追加されたユーザーが次回ログインしたときには、Data Warehouse オプションが [!UICONTROL Reports & Analytics] メニューに追加されています。

   >[!NOTE]
   >
   >（ユーザーが 2 つのグループに割り当てられており、一方のグループではある機能に対するアクセスが認められていないのに対して、もう一方のグループではアクセスが認められているなど）権限に競合が発生した場合には、システムによって権限に制限が加えられます。data warehouse に対するアクセスが認められていないグループに所属するユーザーを、そのグループから削除する必要があります。

>[!MORELIKETHIS]
>
>* [グループ ](/help/admin/user-management2/c-user-groups/groups.md)

