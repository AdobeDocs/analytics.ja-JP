---
description: Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。
seo-description: Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。
seo-title: Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行
title: Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

Enterprise または Federated ID として Analytics ユーザーアカウントを Admin Console に移行する方法。

## 前提条件 {#prereqs}

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

      ![ステップ情報](assets/admin-analytics-users-assets.png)

   1. On the [!DNL Users] page, select users, then click **[!UICONTROL Export to CSV]**.

      ![ステップ情報](assets/export-csv-migrate.png)

   1. Open the downloaded [!DNL User List.csv] file in Excel.

      、、およびの値をファ *`Email`*&#x200B;イルにコ *`First Name`*&#x200B;ピ *`Last Name`* ーす [!DNL sample.csv] る準備をします（次の手順で説明）。

      > [!IMPORTANT] CSVファイル内の値はコンマで区切る必要があります。

      > [!TIP] この手順では、有効な電子メールIDを持つユーザーのみがEnterprise IDまたはFederated IDへの移行に含まれるように、ユーザーリストを合理化することをお勧めします。

1. Admin Console で、Admin Console ユーザーのリストをダウンロードします。

   1. Navigate to [Admin Console](http://adminconsole.adobe.html/#) &gt; **[!UICONTROL Users]**, then click [Export users list to CSV](https://helpx.adobe.com/enterprise/using/users.html).

      ![](assets/export-csv.png)

   1. Compare the two files: the existing Admin Console users in the exported [!DNL .csv] file ( [!DNL sample.csv], in this example) with the users in the Analytics [!DNL User Logins List.csv] file.

      > [!IMPORTANT] 重複が見つかった場合は、Analyticsファイルから削除し [!DNL User Logins List.csv] ます。 この手順は、Admin Console の既存の Experience Cloud ユーザー権限が上書きされるのを防ぎ、移行するアカウントのリストを提供します。

1. Admin Console から CSV テンプレートをダウンロード：
   1. On the Users tab, click **[!UICONTROL Add users by CSV]**, then **[!UICONTROL Download CSV Template]**.

      ![ステップ情報](assets/add-users-csv.png)

   1. Choose **[!UICONTROL Standard Template]**.

      この手順では、[!DNL sample.csv] テンプレートファイルをダウンロードします。

      ![](assets/download-csv-template.png)

1. の、および *`Email`*&#x200B;列の値を、テ *`First Name`*&#x200B;ンプレート *`Last Name`* 内の対応する列 [!DNL User Logins List.tab] にコピー [!DNL sample.csv] します。

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
   <td colname="col2"> <p><span class="term"> Federated IDまたは</span> Enterprise ID <span class="term"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ドメイン </p> </td> 
   <td colname="col2"> <p>ドメインが 「 <span class="term"> Domain</span> 」列と「 <span class="term"> Email</span> 」列は、前提条件で確立されたドメインと一致し <a href="/help/admin/user-management2/user-migration/c-migration-tool/migrate-enterprise.md#prereqs" format="dita" scope="local"> ます</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>国コード </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

For more information about the fields in the [!DNL .csv] file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html).

> [!NOTE] その他の列（およびなど） *`Product Configurations`* は空白 *`Admin Roles`* にできます。

1. On the Users tab in the Admin Console, upload the template file by clicking **[!UICONTROL Add users by CSV]** (as shown in Step 3.).
1. Analyticsで、移行ツールを実行します(Analyticsユーザーアカウントの移 [行を参照](/help/admin/user-management2/user-migration/c-migration-tool/t-migrate-users.md))。
1. Click **[!UICONTROL Migrate]** &gt; **[!UICONTROL Migrate as Enterprise IDs]**.

   ![ステップ情報](assets/migrate-as-enterprise.png)

   When you click **[!UICONTROL Migrate]**, user are linked to the Enterprise ID/Federated ID account in Admin Console. The permissions of the legacy user account in Analytics will match the permissions granted to the Enterprise/Federated ID login in **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL Product Profiles]**. 「移行完了」バケットにユーザー ID が表示されます。従来の [!DNL my.omniture.com] アクセスを無効にできます。

   After migrating users, the status under the Migration Status column changes from *`Not Initiated`* to *`Migrated`*.

   移行ツールに表示される Adobe ID ユーザーも、このプロセスで移行できます。これらのユーザーは、ID 切り替えが実行されるまで、引き続き Adobe ID を使用してログインする必要があります。ID 切り替えに関してサポートが必要な場合は、Adobe カスタマーケアにお問合せください。
