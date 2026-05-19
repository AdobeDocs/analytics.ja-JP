---
description: Analytics ユーザーのレガシーログインを無効にする方法について説明します。
title: 従来のログインの無効化
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 60%

---

# 従来のログインの無効化

Analytics ユーザーのレガシーログインを無効にする方法について説明します。

ユーザーが従来のAnalytics ユーザー管理システムからAdobe Admin Consoleに移行した後、従来のログインを無効にできます。 レガシーログインを無効にすると、ユーザーがレガシーログインを使用しようとすると、CX Enterprise ログインにリダイレクトされます。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー ID の移行]**&#x200B;を選択して移行ツールを起動します。
1. [!DNL User Information] セクションで、従来のログインを無効にするユーザーを含むドメインを探し、「**[!UICONTROL ユーザーを選択]**」をクリックします。
1. 無効にする従来のログインを持つユーザーを選択します。

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   有効なユーザーのステータスは、「移行ステータス」列の下に「*`Migrated`*」と表示されます。 ユーザーが移行されるまで、従来のログインを無効にすることはできません。
1. 「**[!UICONTROL 従来のログインを無効化]**」をクリックしてから、「**[!UICONTROL 完了]**」をクリックします。

   「従来のログインを無効化」には、従来の [!DNL my.omniture.com] ユーザー名とパスワードを引き続き使用できるユーザーが表示されます。

   移行する前のユーザーのレガシーログインを無効にすることはできません。 無効化されると、ユーザーは Experience Cloud ID を使用して Analytics へログインおよびアクセスする必要があります。
