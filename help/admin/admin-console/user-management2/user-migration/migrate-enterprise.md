---
description: Enterprise ID または Federated ID として Analytics ユーザーアカウントをAdobe Admin Consoleに移行する方法。
title: Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 75%

---

# Enterprise ID と Federated ID の Analytics ユーザーアカウントの移行 {#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

Enterprise ID または Federated ID として Analytics ユーザーアカウントをAdobe Admin Consoleに移行する方法。

## 前提条件 {#prereqs}

Adobe Admin Consoleでユーザーを管理するための前提条件。

新しいドメインおよびディレクトリの場合は、次の手順に従います。

* ディレクトリの設定
* ドメインの設定
* ドメインをディレクトリにリンクさせる

詳しくは、[ID システムの設定](https://helpx.adobe.com/jp/enterprise/using/set-up-identity.html)を参照してください。

別の事業部門またはチームによって、別の組織でディレクトリを作成済みの場合は、[直接信頼](https://helpx.adobe.com/jp/enterprise/using/set-up-identity.html#Directorytrusting)の手順に従い、Analytics 用に使用している組織でディレクトリを確立してください。

## Enterprise ID と Federated ID の ユーザーアカウントの移行 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

この手順では、以下をおこないます。

* **[!UICONTROL Analytics]**／**[!UICONTROL Analytics ユーザーおよびアセット]**&#x200B;からユーザーログインリストをダウンロードします。

* **[!UICONTROL Admin Console]**／**[!UICONTROL ユーザー]**&#x200B;から現在のユーザーリストをダウンロードします。

* リストを比較します (Adobe Admin Consoleでアカウントデータが上書きされるのを防ぐため、重複がないか探します )。
* 完了したをアップロード [!DNL .csv] （から） **[!UICONTROL Admin Console]** > **[!UICONTROL ユーザー]**) をAdobe Admin ConsoleにEnterprise IDまたはFederated IDのユーザーと共に追加します。

既存の Adobe ID ユーザーアカウントを Enterprise ID または Federated ID へ移行する必要がある場合は、Adobe Customer Care に連絡するか、[ユーザー ID の一括切り替え](https://helpx.adobe.com/jp/enterprise/using/bulk-operations.html)をリクエストしてください。

**ユーザーアカウントを移行するには**

1. 次のいずれかのメソッド（ユーザーを移行済みかどうかによって異なります）を使用して、Analytics User Management から Analytics ユーザーログインファイル（[!DNL User Logins List.tab]）をダウンロードします。
   1. *移行する前に、***[!UICONTROL Admin]** ／ **[!UICONTROL User Management (Legacy)]** ／ **[!UICONTROL Edit Users]** へ移動してから、「**[!UICONTROL Download Report]**」をクリックします。

      ![](/help/admin/admin-console/user-management2/user-migration/assets/download-report.png)

      Download Report リンクは、ユーザーを移行していない顧客にのみ表示されます。

   1. *ユーザーを移行済みの場合は、* **[!UICONTROL Analytics]**／**[!UICONTROL Analytics ユーザーおよびアセット]**&#x200B;へ移動します。

      ![ステップ情報](/help/admin/admin-console/user-management2/user-migration/assets/admin-analytics-users-assets.png)

   1. [!DNL Users] ページでユーザーを選択し、「**[!UICONTROL CSV に書き出し]**」をクリックします。

      ![ステップ情報](/help/admin/admin-console/user-management2/user-migration/assets/export-csv-migrate.png)

   1. Excel で、ダウンロードした [!DNL User List.csv] ファイルを開きます。

      *`Email`*、*`First Name`*、および *`Last Name`* の値を [!DNL sample.csv] ファイルにコピーする準備をします（次の手順で説明）。

      >[!IMPORTANT]
      >
      >CSV ファイル内の値はコンマで区切る必要があります。

      >[!TIP]
      >
      >この手順の間に、ユーザーリストを整理して、Enterprise ID または Federated ID 移行に有効なメール ID を持つユーザーのみを含めることをお勧めします。

1. 内 [!UICONTROL Admin Console]、Adobe Admin Consoleユーザーのリストをダウンロードします。

   1. [!UICONTROL Admin Console]／**[!UICONTROL ユーザー]**&#x200B;に移動してから、「[ユーザーリストを CSV に書き出し](https://helpx.adobe.com/jp/enterprise/using/users.html)」をクリックします。

      ![](/help/admin/admin-console/user-management2/user-migration/assets/export-csv.png)

   1. 2 つのファイルを比較します。書き出されたの既存のAdobe Admin Consoleユーザー [!DNL .csv] ファイル ( [!DNL sample.csv]（この例では）Analytics のユーザーと共に [!DNL User Logins List.csv] ファイル。

      >[!IMPORTANT]
      >
      >重複が見つかったら、それらを Analytics の [!DNL User Logins List.csv] ファイルから削除してください。この手順は、Adobe Admin Consoleの既存のExperience Cloudユーザー権限が上書きされるのを防ぎ、移行するアカウントのリストを提供します。

1. Adobe Admin Consoleから CSV テンプレートをダウンロードします。
   1. 「ユーザー」タブで、「**[!UICONTROL CSV によるユーザーの追加]**」、「**[!UICONTROL CSV テンプレートのダウンロード]**」の順にクリックします。

      ![ステップ情報](/help/admin/admin-console/user-management2/user-migration/assets/add-users-csv.png)

   1. 「**[!UICONTROL 標準テンプレート]**」を使用します。

      この手順では、[!DNL sample.csv] テンプレートファイルをダウンロードします。

      ![](/help/admin/admin-console/user-management2/user-migration/assets/download-csv-template.png)

1. [!DNL User Logins List.tab] から、*`Email`*、*`First Name`*、*`Last Name`* 列の値を [!DNL sample.csv] テンプレートの対応する列にコピーします。

   **テンプレートファイルの例**

   ![](/help/admin/admin-console/user-management2/user-migration/assets/sample.png)

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
   <td colname="col2"> <p><span class="term">Federated ID</span> または<span class="term"> Enterprise ID</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ドメイン </p> </td> 
   <td colname="col2"> <p> 「<span class="term">ドメイン</span>」列と「<span class="term">電子メール</span>」列は、前提条件</a>で確立されたドメインと一致します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>国コード </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL .csv] ファイルのフィールドについての詳細は、[CSV ファイル形式](https://helpx.adobe.com/enterprise/using/users.html)を参照してください。

>[!NOTE]
>
>その他の列（[!UICONTROL 製品設定]や[!UICONTROL 管理者の役割]など）は空白にできます。

1. Adobe Admin Consoleの「ユーザー」タブで、「 **[!UICONTROL CSV でのユーザーの追加]** （手順 3 で示すように）。
1. Analytics で、移行ツールを実行します（[Analytics ユーザーアカウントの移行](/help/admin/admin-console/user-management2/user-migration/t-migrate-users.md)を参照）。
1. **[!UICONTROL 移行]**／**[!UICONTROL Enterprise ID として移行]**&#x200B;をクリックします。

   ![ステップ情報](/help/admin/admin-console/user-management2/user-migration/assets/migrate-as-enterprise.png)

   クリック時 **[!UICONTROL 移行]**」をクリックすると、ユーザーはAdobe Admin ConsoleのEnterprise ID/Federated IDアカウントにリンクされます。 Analytics での従来のユーザーアカウントの権限は、**[!UICONTROL Admin Console]**／**[!UICONTROL Analytics]**／**[!UICONTROL 製品プロファイル]**&#x200B;で Enterprise／Federated ID ログインに付与された権限を照合します。「移行完了」バケットにユーザー ID が表示されます。従来の [!DNL my.omniture.com] アクセスを無効にできます。

   ユーザー移行後、「移行ステータス」列のステータスが「**[!UICONTROL 未開始]**」から「**[!UICONTROL 移行済み]**」に変わります。

   移行ツールに表示される Adobe ID ユーザーも、このプロセスで移行できます。これらのユーザーは、ID 切り替えが実行されるまで、引き続き Adobe ID を使用してログインする必要があります。ID 切り替えに関してサポートが必要な場合は、Adobe カスタマーケアにお問合せください。
