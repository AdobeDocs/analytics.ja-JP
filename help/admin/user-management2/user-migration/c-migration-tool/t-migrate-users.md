---
description: 従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。
seo-description: 従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。
seo-title: Adobe ID 用に Analytics ユーザーアカウントを移行する
title: Adobe ID 用に Analytics ユーザーアカウントを移行する
uuid: 734e9f14-ef8d-44de-8ff3-3ee6dfe0a214
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Adobe ID 用に Analytics ユーザーアカウントを移行する{#migrate-analytics-user-accounts-for-adobe-ids}

従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。

## Adobe ID 用に Analytics ユーザーアカウントを移行する {#task-f3355f3b14a340feae58cfa04c0ba1c9}

従来の Analytics ユーザー管理システムから Admin Console へユーザーを移行します。

> [!NOTE] Experience cloud経由でログインしていない管理者がユーザーID移行ツールにアクセスしようとすると、Experience cloudのログインページにリダイレクトされます。

**Analytics ユーザーを移行するには**

1. **[!UICONTROL Analytics]** /管理者 **[!UICONTROL /ユー]** ザーID **[!UICONTROL の移行に移動します]**。

   ![](assets/migration-progress.png)

   ユーザー ID の移行ページには、*以降の進行状況*&#x200B;および&#x200B;*ユーザー情報*&#x200B;の 2 つのセクションがあります。

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
   <td colname="col1"> <p>従来のログインの無効化 </p> </td> 
   <td colname="col2"> <p>会社 ID を使用している従来のログインが無効化されます。ユーザーは、Adobe ID または Enterprise ID を使用して、Experience Cloud にアクセスするようになります。すべてのユーザーがこのフェーズに達すると、移行が完了します。 </p> <p>移行時には、従来のログインは無効になります。 ユーザーはExperienceCloud.adobe.com <span class="filepath"> にリダイレクトされ、</span> Adobe IDまたはEnterprise IDを使用してログインする必要があります。 </p> <p>See <a href="/help/admin/user-management2/user-migration/c-migration-tool/t-disable-legacy-login.md"> Disable Legacy Logins</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**ユーザー情報**

ユーザー情報は、組織内のユーザーの概要を、ドメイン名で区切って表示します。

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
   <td colname="col2"> <p>ドメインは、現在の Analytics ユーザーベースの電子メール ID に固有のものとなります。1 つのドメインを複数の組織がクレームすることはできません。また、ドメインをクレームできるのはシステム管理者のみです。詳しくは、<a href="https://helpx.adobe.com/enterprise/help/request-access-to-claimed-domain.html">クレームされたドメインへのアクセスを要求する</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>申請されたドメイン </p> </td> 
   <td colname="col2"> <p>ユーザーを Enterprise または Federated ID として移行する場合はシステム管理者であり、かつ、ユーザーを移行する前に Admin Console から利用可能なドメインを申請する必要があります。詳しくは<a href="https://helpx.adobe.com/enterprise/help/identity.html">こちら</a>。 </p> <p>Enterprise またはr Federated ID のドメインを申請する場合は、この手順をスキップして、ユーザーを Adobe ID として移行します。ID タイプの詳細については<a href="https://helpx.adobe.com/enterprise/help/identity.html">ここ</a>をクリックしてください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Locate the domain containing the user IDs you want to migrate, then, under **[!UICONTROL Requiring Migration]**, click **[!UICONTROL Select Users]**.
1. On the [!DNL Users] page, select the users you want to migrate, then click **[!UICONTROL Migrate]**.

   When you click **[!UICONTROL Migrate]**, users receive an invitation (Migration Initiated) and must accept it. このアクションにより、ユーザー ID が「移行完了」に変わります。その後、[!DNL my.omniture.com] への従来のアクセスをオフにすることができます。

   ![](assets/user-info.png)

1. ユーザーを移行する ID タイプを [Adobe ID または Enterprise ID](https://helpx.adobe.com/enterprise/help/identity.html) として指定します。

   After migrating users, the status under the column Migration Status changes from *`Not Initiated`* to *`Migrated`*.

   If *`Failed`* displays, hover over the icon for a description about why the migration failed.
