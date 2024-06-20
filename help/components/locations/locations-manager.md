---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: 場所マネージャー
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 1%

---

# 場所マネージャー

場所マネージャーを使用すると、アカウントと場所を表示、作成、編集または削除できます。 これらは、次のいずれかの目的で使用できます。

* を使用したファイルのエクスポート [データフィード](/help/export/analytics-data-feed/create-feed.md)
* を使用したレポートのエクスポート [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* を使用したスキーマのインポート [分類セット](/help/components/classifications/sets/overview.md)

## 場所の表示、フィルター、検索

場所マネージャーを使用すると、自分で作成した場所や組織と共有されている場所を表示できます。 システム管理者は、共有されているかどうかに関係なく、すべてのユーザーが作成した場所を表示できます。

1. Adobe Analyticsのロケーションマネージャーにアクセスするには、 **[!UICONTROL Components]** > **[!UICONTROL 場所]**.

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーの場所を表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。 <!-- Maybe add a screenshot? This is new functionality -->

1. 場所のリストをフィルタリングまたは検索：

   * **フィルター：** 場所のリストをフィルターするには、フィルターアイコンを選択します。

     場所は、次の項目でフィルタリングできます **[!UICONTROL 場所タイプ]**, **[!UICONTROL アカウント]**、または **[!UICONTROL 作成者]**.

     ![場所フィルター](assets/locations-filters.png)

   * **検索：** 検索フィールドに、表示する場所の名前を入力します。 入力した結果がフィルタリングされます。 次の列が検索されます。 **場所名**, **場所タイプ**, **アカウント**、および **作成者**.

1. （オプション） 1,000 個を超える場所がある場合は、最初の 1,000 個の場所のみが表示されます。 を選択 [!UICONTROL **さらに読み込む**] を選択して、さらに 1,000 個の場所を読み込みます。

## 場所マネージャーで列を設定

場所マネージャーでは、次の列を使用できます。 テーブルに表示される列をカスタマイズするには、 **テーブルをカスタマイズ** アイコン ![テーブルアイコンのカスタマイズ](assets/customize-table-icon.png).

* **[!UICONTROL 場所名]**：場所の名前。 場所名の横にある「。..」メニューを選択すると、次のいずれかを実行できます [場所を編集](/help/components/locations/configure-import-locations.md) または削除します。
* **[!UICONTROL 場所タイプ]**：場所に関連付けられたアカウントのタイプ。
* **[!UICONTROL アカウント]**：場所に関連付けられた特定のアカウント。
* **用途**：場所を使用できるアプリケーションのタイプ（データフィード、Data Warehouse、分類セットなど）。
* **[!UICONTROL 前回の使用]**：場所が最後に使用された日付。
* **[!UICONTROL 作成者]**：場所を作成したユーザー。
* **[!UICONTROL 作成日]**：場所が作成された日付。

## ロケーションの作成と管理

場所を作成、編集、削除できます。

### 場所の作成

場所の作成方法については、を参照してください。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 場所の編集

場所は、作成したユーザーまたはシステム管理者のみが編集できます。

場所の編集方法については、を参照してください。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

### 場所の削除

>[!IMPORTANT]
>
>場所が削除された場合、その削除された場所に関連付けられているデータフィードファイル、Data Warehouseレポートまたは分類セットスキーマは、次回使用される際に失敗します。
>
>場所を削除する場合、次の操作を行う必要があります [データフィードの編集](/help/export/analytics-data-feed/create-feed.md), [Data Warehouseレポート](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)、および [分類セットスキーマ](/help/components/classifications/sets/manage/schema.md) 機能する場所を使用する。

場所を削除できるのは、その場所を作成したユーザーまたはシステム管理者のみです。

Adobe Analyticsの Locations Manager で場所を削除するには：

1. を選択 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所**] タブ。

1. で 3 ドットメニューを選択します。 [!UICONTROL **場所名**] 削除する場所の列。

1. 「[!UICONTROL **削除**]」を選択します。

## アカウントの作成と管理

アカウントの作成、編集、削除が可能です。

### アカウントの作成

アカウントの作成方法については、を参照してください [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md).

### アカウントの編集

アカウントは、作成したユーザーまたはシステム管理者のみが編集できます。

アカウントの編集方法については、を参照してください。 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md).

### アカウントキーの表示

アカウントを作成すると、そのアカウントに関連付けられているアカウントキーを表示できます。 次の場合に、クラウドプロバイダーでアカウントの設定を完了していない場合は、この情報を表示する必要があります [最初にアカウントを設定した](/help/components/locations/configure-import-accounts.md).

エクスポートアカウントに関連付けられているキーを表示するには：

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所アカウント**] タブ。

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーの場所を表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。 <!-- Maybe add a screenshot? This is new functionality -->

1. 編集するアカウント上の「。..」アイコンを選択し、次に選択します [!UICONTROL **アカウントキー**].

### アカウントの削除

>[!IMPORTANT]
>
>アカウントを削除できるのは、そのアカウントを使用している場所がない場合のみです。 アカウントを削除する前に、の説明に従って、アカウント上の場所をすべて削除する必要があります [場所の削除](#delete-a-location).

アカウントを削除できるのは、そのアカウントを作成したユーザーまたはシステム管理者のみです。

アカウントを削除するには：

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所アカウント**] タブ。

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーのアカウントの表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。

1. 編集するアカウント上の「。..」アイコンを選択し、次に選択します [!UICONTROL **アカウントを削除**]

## 会社全体の設定を行う（管理者のみ）

システム管理者は、ユーザーによるアカウントと場所の作成を制限したり、ユーザーが作成および使用できるアカウントのタイプを制限したりできます。

![「管理設定」タブ](assets/locations-admin-settings.png)

### ユーザーがアカウントを作成および編集できるかどうかを構成します

デフォルトでは、組織内のすべてのユーザーは、「」の説明に従って、Adobe Analytics環境で作成したアカウントを作成および編集できます [クラウドの読み込みアカウントと書き出しアカウントの設定](/help/components/locations/configure-import-accounts.md).

ユーザーによるアカウントの作成を制限できます。 その場合、ユーザーは作成済みの任意のアカウントを引き続き使用できますが、編集はできません。 ユーザーが作成したアカウントは、の説明に従って削除できます [アカウントの削除](#delete-an-account).

すべてのユーザーによるアカウントの作成および編集を制限するには：

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **管理設定**] タブ。

1. が含まれる [!UICONTROL **場所アカウント**] セクションで、「」オプションの選択を解除します。 [!UICONTROL **ユーザーが場所アカウントを作成および管理できるようにする**].

1. 「[!UICONTROL **保存**]」を選択します。

1. （オプション）ユーザーが作成したアカウントのうち、使用したくないアカウントを削除します（「」を参照） [アカウントの削除](#delete-an-account).

### ユーザーが場所を作成および編集できるかどうかを構成します

デフォルトでは、の説明に従って、組織内のすべてのユーザーがAdobe Analytics環境で場所を作成および編集することができます。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

ユーザーによる場所の作成を制限できます。 その場合、ユーザーは作成済みの任意の場所を引き続き使用できますが、編集できなくなります。 ユーザが作成したロケーションは、の説明に従って削除できます [場所を削除](#delete-a-location).

すべてのユーザーに対してロケーションの作成および編集を制限するには、次のようにします。

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **管理設定**] タブ。

1. が含まれる [!UICONTROL **場所**] セクションで、「」オプションの選択を解除します。 [!UICONTROL **ユーザーに場所の作成と管理を許可**].

1. 「[!UICONTROL **保存**]」を選択します。

1. （オプション）の説明に従って、ユーザーが作成した使用しない場所を削除します [場所の削除](#delete-a-location).

### ユーザーが作成および使用できるアカウントタイプを制限する

次の状況では、ユーザーに表示されるアカウントタイプを制限できます。

* 条件 [新しいアカウントの作成](/help/components/locations/configure-import-accounts.md).

* を使用してファイルを書き出すときに使用するアカウントを選択する場合 [データフィード](/help/export/analytics-data-feed/create-feed.md)、を使用したレポートのエクスポート [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)または、を使用したスキーマのインポート [分類セット](/help/components/classifications/sets/overview.md).

この節で説明するようにアカウントタイプを制限すると、制限したタイプのアカウントはユーザーに表示されなくなります。 つまり、そのタイプの新しいアカウントは作成できず、そのタイプの既存のアカウントは、データフィード、分類またはData Warehouseセットを作成する際には使用できません。

ただし、スケジュールされた書き出し用に設定された既存のアカウントを使用しないようにする場合は、それらを削除する必要があります。

#### スケジュールされた書き出しにアカウントが使用されていないことを確認します

勘定科目のタイプを制限すると、既存の勘定科目は非表示になり、削除されません。

制限したタイプのアカウントにデータを送信するようにスケジュールが既に設定されている場合、アカウントのタイプを制限した後もスケジュールは引き続き実行され、データは引き続きアカウントに送信されます。  例えば、制限したアカウントタイプにデータを送信するようにデータフィードがスケジュールされている場合、スケジュールは引き続き実行されます。

スケジュールされた書き出しで特定のタイプのアカウントが使用されないようにする必要がある場合は、事前にアカウントを削除できます [アカウントタイプの制限](#limit-the-account-types-that-are-available-to-users).

アカウントを削除するには：

1. スケジュールされた書き出しに使用されている、制限する予定の勘定科目タイプの勘定科目を見つけます。

1. アカウントを削除します（「」を参照） [アカウントの削除](#delete-an-account).

1. 次の節に進みます。 [ユーザーが使用できるアカウントタイプを制限する](#limit-the-account-types-that-are-available-to-users).

#### ユーザーが使用できるアカウントタイプを制限する

アカウントの作成時および使用時にユーザーが使用できるアカウントタイプを制限するには：

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **管理設定**] タブ。

1. を見つけます。 [!UICONTROL **許可されるアカウントタイプ**] セクション。

   デフォルトでは、次のアカウントタイプをユーザーが使用できます。 ユーザーによる使用を制限する勘定科目タイプの選択を解除します。

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **電子メール**]

   * 従来のアカウントタイプ （以下を含む） [!UICONTROL **Amazon S3**], [!UICONTROL **Azure**], [!UICONTROL **FTP**]、および [!UICONTROL **SFTP**]

1. 「[!UICONTROL **保存**]」を選択します。


