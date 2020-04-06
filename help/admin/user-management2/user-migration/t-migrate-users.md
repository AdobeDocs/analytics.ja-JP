---
description: 従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。
title: 'Adobe ID 用に Analytics ユーザーアカウントを移行する '
uuid: 734e9f14-ef8d-44de-8ff3-3ee6dfe0a214
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe ID 用に Analytics ユーザーアカウントを移行する {#migrate-analytics-user-accounts-for-adobe-ids}

従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。

## Adobe ID 用に Analytics ユーザーアカウントを移行する {#task-f3355f3b14a340feae58cfa04c0ba1c9}

従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。

>[!NOTE]Experience Cloud でログインしていない管理者がユーザー ID 移行ツールにアクセスしようとすると、Experience Cloud のログインページにリダイレクトされます。

**Analytics ユーザーを移行するには**

1. //に移 **[!UICONTROL Analytics]** 動し **[!UICONTROL Admin]** ます **[!UICONTROL User ID Migration]**。

   ![](assets/migration-progress.png)

   ユーザー ID の移行ページには、*移行の進行状況*&#x200B;および&#x200B;*ユーザー情報*&#x200B;の 2 つのセクションがあります。

   **移行の進行状況**

   <table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> フェーズ </th> 
      <th colname="col2" class="entry"> 説明 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>移行完了 </p> </td> 
      <td colname="col2"> <p>ユーザーが招待を受け入れました。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>従来のログインが無効 </p> </td> 
      <td colname="col2"> <p>従来のログインでは会社IDを使用できません。 ユーザーは、Adobe IDまたはEnterprise IDを使用してExperience Cloudにアクセスできるようになりました。 すべてのユーザーがこの段階に達したら、移行を完了します。 </p> <p>移行時には、従来のログインは無効になります。ユーザーは <span class="filepath"> experiencecloud.adobe.com</span> にリダイレクトされ、Adobe IDまたは Enterprise ID を使用してログインする必要があります。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

   **ユーザー情報**

   「ユーザー情報」は、組織内のユーザーの概要をドメイン名で区切って示します。

   <table id="table_3822E27AF81E4A188562FEB5131548A5"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 要素 </th> 
      <th colname="col2" class="entry"> 説明 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>ドメイン </p> </td> 
      <td colname="col2"> <p>ドメインは、現在のAnalyticsユーザーベースの電子メールIDに固有です。 1 つのドメインを複数の組織がクレームすることはできません。また、ドメインをクレームできるのはシステム管理者のみです。詳しくは、<a href="https://helpx.adobe.com/jp/enterprise/help/request-access-to-claimed-domain.html">クレームされたドメインへのアクセスを要求する</a>を参照してください。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>申請されたドメイン </p> </td> 
      <td colname="col2"> <p>ユーザーを Enterprise または Federated ID として移行する場合はシステム管理者であり、かつ、ユーザーを移行する前に Admin Console から利用可能なドメインを申請する必要があります。詳しくは<a href="https://helpx.adobe.com/jp/enterprise/help/identity.html">こちら</a>。 </p> <p>Enterprise またはr Federated ID のドメインを申請する場合は、この手順をスキップして、ユーザーを Adobe ID として移行します。ID タイプの詳細については<a href="https://helpx.adobe.com/jp/enterprise/help/identity.html">ここ</a>をクリックしてください。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Locate the domain containing the user IDs you want to migrate, then, under **[!UICONTROL Requiring Migration]**, click **[!UICONTROL Select Users]**.
1. On the [!DNL Users] page, select the users you want to migrate, then click **[!UICONTROL Migrate]**.

   When you click **[!UICONTROL Migrate]**, users receive an invitation (Migration Initiated) and must accept it. このアクションにより、ユーザー ID が「移行完了」に変わります。その後、`[!DNL my.omniture.com].` への従来のアクセスをオフにすることができます。

   ![](assets/user-info.png)

1. ユーザーを移行する ID タイプを Adobe ID または Enterprise ID として指定します。

   ユーザー移行後、「移行ステータス」列のステータスが「*`Not Initiated`*」から「*`Migrated`*」に変わります。

   「*`Failed`*」が表示された場合は、アイコンの上にマウスポインターを合わせると、移行失敗の理由に関する説明が表示されます。
