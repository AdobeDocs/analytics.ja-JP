---
description: 管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。
title: Data Warehouse ユーザーグループの追加
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 96%

---

# Data Warehouse ユーザーグループの追加

管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。

1. **[!UICONTROL Analytics]**/**[!UICONTROL 管理者]**/**[!UICONTROL すべての管理者]**/**[!UICONTROL ユーザー管理]**&#x200B;をクリックします。
1. 「**[!UICONTROL グループの編集]**」をクリックします。
1. 「**[!UICONTROL 新しいユーザーグループの追加]**」をクリックします。
1. **[!UICONTROL ユーザーグループの定義]**&#x200B;セクションで、「グループ名」フィールドに名前を入力します。以下のようなグループ情報を入力します。

   例：`Data Warehouse Access`。
1. 「**[!UICONTROL グループの説明]**」フィールドに説明を入力します。
1. **[!UICONTROL レポートスイートへのアクセス]**&#x200B;セクションでは、グループメンバーにアクセスを許可するレポートスイートを選択します。
1. [!UICONTROL ツール]で、**[!UICONTROL すべてのツール]**&#x200B;を有効にします。

   このほか、「**[!UICONTROL カスタマイズ]**」をクリックして&#x200B;**[!UICONTROL カスタム Data Warehouse レポート]**&#x200B;を有効にすることができます。

1. [!UICONTROL ユーザーログインの割り当て]で、ユーザーログインを追加します。
1. 「**[!UICONTROL グループの保存]**」をクリックします。

   このグループに追加されたユーザーが次回ログインしたときには、Data Warehouse オプションが [!UICONTROL Reports &amp; Analytics] メニューに追加されています。

   >[!NOTE]
   >
   >（ユーザーが 2 つのグループに割り当てられており、一方のグループではある機能に対するアクセスが認められていないのに対して、もう一方のグループではアクセスが認められているなど）権限に競合が発生した場合には、システムによって権限に制限が加えられます。data warehouse に対するアクセスが認められていないグループに所属するユーザーを、そのグループから削除する必要があります。

>[!MORELIKETHIS]
>
>* [グループ](/help/admin/user-management2/c-user-groups/groups.md)

