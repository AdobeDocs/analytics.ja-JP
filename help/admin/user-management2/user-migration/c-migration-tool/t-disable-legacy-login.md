---
description: Analytics ユーザーの従来のログインを無効化する方法を学習します。
seo-description: Analytics ユーザーの従来のログインを無効化する方法を学習します。
seo-title: 従来のログインの無効化
title: 従来のログインの無効化
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# 従来のログインの無効化{#disable-legacy-logins}

Analytics ユーザーの従来のログインを無効化する方法を学習します。

ユーザーを従来の Analytics ユーザー管理システムから Adobe Admin Console に移行した後は、従来のログインを無効にすることができます。従来のログインを無効化した場合、従来の方法でログインしようとするユーザーは Experience Cloud ログインにリダイレクトされます。

1. **[!UICONTROL Analytics]** /管理者/ユーザーIDの移行で **[!UICONTROL 移行ツ]** ールを開きます ****。
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. 無効にする従来のログインを持つユーザーを選択します。

   ![](assets/user-info.png)

   The users that are eligible will have a status of  under the Migration Status column. *`Migrated`*&#x200B;ユーザーが移行されるまで、従来のログインを無効にすることはできません。
1. Click **[!UICONTROL Disable Legacy Login]**, then click **[!UICONTROL Done]**.

   「従来のログインを無効化」には、従来の [!DNL my.omniture.com] ユーザー名とパスワードを引き続き使用できるユーザーが表示されます。

   まだ移行されていないユーザーの従来のログインを無効化することはできません。無効化されると、ユーザーは Experience Cloud ID を使用して Analytics　へログインおよびアクセスする必要があります。

