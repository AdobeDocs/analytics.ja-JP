---
description: Analytics ユーザーの従来のログインを無効化する方法を学習します。
title: 従来のログインの無効化
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: 1ec080acf65c31b077a3daf3846f233f01e011b8
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---


# 従来のログインの無効化 {#disable-legacy-logins}

Analytics ユーザーの従来のログインを無効化する方法を学習します。

ユーザーを従来の Analytics ユーザー管理システムから Adobe Admin Console に移行した後は、従来のログインを無効にすることができます。従来のログインを無効化した場合、従来の方法でログインしようとするユーザーは Experience Cloud ログインにリダイレクトされます。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー ID の移行]**&#x200B;を選択して移行ツールを起動します。
1. [!DNL User Information] セクションで、従来のログインを無効にするユーザーを含むドメインを探し、「**[!UICONTROL ユーザーを選択]**」をクリックします。
1. 無効にする従来のログインを持つユーザーを選択します。

   ![](assets/user-info.png)

   有効なユーザーのステータスは、「移行ステータス」列の下に「*`Migrated`*」と表示されます。ユーザーが移行されるまで、従来のログインを無効にすることはできません。
1. 「**[!UICONTROL 従来のログインを無効化]**」をクリックしてから、「**[!UICONTROL 完了]**」をクリックします。

   「従来のログインを無効化」には、従来の [!DNL my.omniture.com] ユーザー名とパスワードを引き続き使用できるユーザーが表示されます。

   まだ移行されていないユーザーの従来のログインを無効化することはできません。無効化されると、ユーザーは Experience Cloud ID を使用して Analytics へログインおよびアクセスする必要があります。

