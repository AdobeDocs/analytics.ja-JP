---
description: 管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。
title: Data Warehouse ユーザーグループの追加
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%

---


# Data Warehouse ユーザーグループの追加

管理者がユーザーグループに対して Data Warehouse レポートのアクセスを有効にする方法について手順を説明します。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー管理]**&#x200B;の順にクリックします。
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
>* [グループ ](/help/admin/user-management2/c-user-groups/groups.md)

