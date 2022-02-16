---
description: Admin Console で Analytics ユーザー、グループおよび製品を管理します。
subtopic: Users and groups
title: ユーザーと製品の管理
feature: Admin Tools
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
source-git-commit: 0143496648e59e95c360388735def726e63ee71b
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# ユーザーと製品の管理

Admin Console で Analytics ユーザー、グループおよび製品を管理します。

>[!IMPORTANT]
>
>ユーザーと製品の管理は [Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移動しました。ユーザーを移行する時期に、アドビから通知があります。

## Admin Console 管理者向けヘルプリソース {#section_C13BBB89E4F248F193358BB3A59DD502}

| タスクまたはリソース | 説明 |
| --- | --- |
| Analytics ユーザー ID の Adobe Admin Console への移行 | Analytics 管理者がユーザー ID を Adobe Admin Console に移行する際には、アドビがお手伝いします。この対応は順次おこなわれます。お客様のユーザーを移行する順番になったら、手順を含む電子メールでアドビから Analytics 管理者に通知されます。このタスクを簡素化するために、 [Analytics ユーザー管理](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=ja) で移行ツールを使用できます。<p>**重要**：ユーザーの移行当日に、以前の権限グループが自動的に Admin Console にコピーされます。Analytics 管理ツールで新規ユーザーを招待したり、新規グループを作成したりできなくなります。移行の準備方法と影響を受ける管理機能については、「Adobe Admin Console への Analytics ユーザーの移行」の FAQ とヘルプを参照してください。 |
| Adobe Admin Console の起動 | ユーザーアカウントが移行されたら、すべてのソリューションのユーザーおよび製品を Admin Console で管理できます。`https://adminconsole.adobe.com/enterprise/` に移動します。[Experience Cloud ユーザーと製品の管理](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ja) も参照してください。 |
| Adobe Analytics 製品プロファイル、ユーザーおよび権限の管理 | [Adobe Admin Console の Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=ja) を参照してください。 |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->