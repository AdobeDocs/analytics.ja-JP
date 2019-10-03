---
description: Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。
seo-description: Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。
seo-title: Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行
title: Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。

## 前提条件 {#concept-e60d8deb3fc54a1a81f1f47a26658de3}

Admin Console でユーザーを管理するための前提条件。

新しいドメインおよびディレクトリの場合は、次の手順に従います。

* ディレクトリの設定
* ドメインの設定
* ドメインをディレクトリにリンクさせる

詳しくは、[ID システムの設定](https://helpx.adobe.com/enterprise/using/set-up-identity.html)を参照してください。

別の事業部門またはチームによって、別の組織でディレクトリを作成済みの場合は、[直接信頼](https://helpx.adobe.com/enterprise/using/set-up-identity.html#Directorytrusting)の手順に従い、Analytics 用に使用している組織でディレクトリを確立してください。

## Enterprise ID と Federated ID のユーザー ID の移行 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

この手順では、以下をおこないます。

* **[!UICONTROL Analytics/]** Analytics Users &amp; Assetsからユーザーログインリストをダウンロードします ****。

* Download a current users list from the **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**.

* リストを比較します（Admin Console でアカウントデータが上書きされるのを防ぐため、重複がないか探します）。
* Upload a finished [!DNL .csv] (from **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**) with Enterprise ID or Federated ID users to the Admin Console.

既存の Adobe ID ユーザーアカウントを Enterprise ID または Federated ID へ移行する必要がある場合は、Adobe Customer Care に連絡するか、[ユーザー ID の一括切り替え](https://helpx.adobe.com/enterprise/using/bulk-operations.html)をリクエストしてください。

**ユーザーアカウントを移行するには**

1. 次のいずれかのメソッド（ユーザーを移行済みかどうかによって異なります）を使用して、Analytics User Management から Analytics ユーザーログインファイル（[!DNL User Logins List.tab]）をダウンロードします。
   1. *移行する前に、管理者* /ユーザー管理（レガシー）/ユーザーの編集 **** (レガシー)に移動し、「ダウンロードレポート ************」をクリックします。

      ![](assets/download-report.png)

      Download Report リンクは、ユーザーを移行していない顧客にのみ表示されます。

   1. *ユーザーを既に移行済みの場合は* 、 **[!UICONTROL Analytics]** / **[!UICONTROL Analyticsのユーザーとアセットに移動します]**。

      ![Step Info](assets/admin-analytics-users-assets.png)

   1. On the [!DNL Users] page, select users, then click **[!UICONTROL Export to CSV]**.

      ![Step Info](assets/export-csv-migrate.png)

   1. Open the downloaded [!DNL User List.csv] file in Excel.

      Be prepared to copy the , , and  values to a  file (described in the next step).*`Email`**`First Name`**`Last Name`*[!DNL sample.csv]

      >[!IMPORTANT]
      >
      >The values in the CSV file must be comma delimited.

      **ヒント**：この手順の間に、ユーザーリストを整理して、Enterprise または Federated ID 移行に有効な電子メール ID を持つユーザーのみを含めることをお勧めします。

1. Admin Console で、Admin Console ユーザーのリストをダウンロードします。

   1. Navigate to [Admin Console](http://adminconsole.adobe.html/#) &gt; **[!UICONTROL Users]**, then click [Export users list to CSV](https://helpx.adobe.com/enterprise/using/users.html).

      ![](assets/export-csv.png)

   1. Compare the two files: the existing Admin Console users in the exported [!DNL .csv] file ( [!DNL sample.csv], in this example) with the users in the Analytics [!DNL User Logins List.csv] file.

      >[!IMPORTANT]
      >
      >If you find duplicates, delete them from the Analytics [!DNL User Logins List.csv] file. この手順は、Admin Console の既存の Experience Cloud ユーザー権限が上書きされるのを防ぎ、移行するアカウントのリストを提供します。

1. Admin Console から CSV テンプレートをダウンロード：
   1. On the Users tab, click **[!UICONTROL Add users by CSV]**, then **[!UICONTROL Download CSV Template]**.

      ![Step Info](assets/add-users-csv.png)

   1. Choose **[!UICONTROL Standard Template]**.

      この手順では、[!DNL sample.csv] テンプレートファイルをダウンロードします。

      ![](assets/download-csv-template.png)

1. Copy the , , and  column values from  to the corresponding columns in the  template.*`Email`**`First Name`**`Last Name`*[!DNL User Logins List.tab][!DNL sample.csv]

   **テンプレートファイルの例**

   ![](assets/sample.png)

1. テンプレート（[!DNL sample.csv]）で、次の必須フィールドに入力します。

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>電子メール </p> </td> 
   <td colname="col2"> <p><span class="filepath">User Logins List.tab</span> からコピーしたもの。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名 </p> </td> 
   <td colname="col2"> <p><span class="filepath">User Logins List.tab</span> からコピーしたもの。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>姓 </p> </td> 
   <td colname="col2"> <p><span class="filepath">User Logins List.tab</span> からコピーしたもの。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID タイプ </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID or  Enterprise ID.</span><span class="term"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ドメイン </p> </td> 
   <td colname="col2"> <p>ドメインが  Domain and  Email column are matching the domain(s) established in the  prerequisites.<span class="term"></span><span class="term"></span><a href="../c-migration-tool/migrate-enterprise.md#concept-e60d8deb3fc54a1a81f1f47a26658de3" format="dita" scope="local"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>国コード </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

For more information about the fields in the [!DNL .csv] file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html).

>[!NOTE]
>
>Other columns, such as  and  can be blank.*`Product Configurations`**`Admin Roles`*

1. On the Users tab in the Admin Console, upload the template file by clicking **[!UICONTROL Add users by CSV]** (as shown in [Step 3](../c-migration-tool/migrate-enterprise.md#step-190321c6025947e38b195daed122c063).).
1. In Analytics, run the migration tool (as described in Migrate Analytics user accounts).[](../c-migration-tool/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9)
1. Click **[!UICONTROL Migrate]** &gt; **[!UICONTROL Migrate as Enterprise IDs]**.

   ![Step Info](assets/migrate-as-enterprise.png)

   When you click **[!UICONTROL Migrate]**, user are linked to the Enterprise ID/Federated ID account in Admin Console. The permissions of the legacy user account in Analytics will match the permissions granted to the Enterprise/Federated ID login in **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL Product Profiles]**. 「移行完了」バケットにユーザー ID が表示されます。従来の [!DNL my.omniture.com] アクセスを無効にできます。

   After migrating users, the status under the Migration Status column changes from *`Not Initiated`* to *`Migrated`*.

   移行ツールに表示される Adobe ID ユーザーも、このプロセスで移行できます。これらのユーザーは、ID 切り替えが実行されるまで、引き続き Adobe ID を使用してログインする必要があります。ID 切り替えに関してサポートが必要な場合は、Adobe カスタマーケアにお問合せください。
