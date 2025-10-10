---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: 場所マネージャー
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 5c02b46a7757e07a23505dc8e3dc21b6353aa9e2
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 1%

---

# 場所マネージャー

場所マネージャーを使用すると、アカウントと場所を表示、作成、編集または削除できます。 これらは、次のいずれかの目的で使用できます。

* [&#x200B; データフィード &#x200B;](/help/export/analytics-data-feed/create-feed.md) を使用したファイルの書き出し
* [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) を使用したレポートのエクスポート
* [Report Builder](/help/analyze/report-builder/report-builder-export.md) を使用する場合のファイルのエクスポート
* [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/overview.md) を使用したスキーマのインポート

## 場所の表示、フィルター、検索

場所マネージャーを使用すると、自分で作成した場所や組織と共有されている場所を表示できます。 システム管理者は、共有されているかどうかに関係なく、すべてのユーザーが作成した場所を表示できます。

1. Adobe Analyticsのロケーションマネージャーにアクセスするには、**[!UICONTROL コンポーネント]**/**[!UICONTROL ロケーション]** を選択します。

1. （条件付き）システム管理者の場合は、「[!UICONTROL **すべてのユーザーの場所を表示**] オプションを有効にして、組織内のすべてのユーザーが作成した場所を表示できます。<!-- Maybe add a screenshot? This is new functionality -->

1. 場所のリストをフィルタリングまたは検索：

   * **フィルター：** フィルターアイコンを選択して、場所のリストをフィルタリングします。

     場所は、**[!UICONTROL 場所タイプ]**、**[!UICONTROL アカウント]** または **[!UICONTROL 作成者]** でフィルタリングできます。

     ![&#x200B; 場所フィルター &#x200B;](assets/locations-filters.png)

   * **検索：** 検索フィールドに、表示する場所の名前の入力を開始します。 入力した結果がフィルタリングされます。 検索される列は、「**Location Name**」、「**Location Type**」、「**Account**」、「**Created By** です。

1. （オプション） 1,000 個を超える場所がある場合は、最初の 1,000 個の場所のみが表示されます。 「[!UICONTROL **さらに読み込む**]」を選択して、さらに 1,000 か所を読み込みます。

## 場所マネージャーで列を設定

場所マネージャーでは、次の列を使用できます。 テーブルに表示される列をカスタマイズするには、「**テーブルをカスタマイズ**」アイコン ![&#x200B; テーブルアイコンをカスタマイズ &#x200B;](assets/customize-table-icon.png) を選択します。

* **[!UICONTROL 場所名]**：場所の名前。 場所名の横にある「。..」メニューを選択すると、[&#x200B; 場所を編集 &#x200B;](/help/components/locations/configure-import-locations.md) または削除できます。
* **[!UICONTROL 場所タイプ]**：場所に関連付けられたアカウントのタイプ。
* **[!UICONTROL アカウント]**：場所に関連付けられた特定のアカウント。
* **アプリケーション**：場所を使用できるアプリケーションのタイプ（データフィード、Data Warehouse、分類セットなど）。
* **[!UICONTROL 最終使用]**：場所が最後に使用された日付。
* **[!UICONTROL 作成者]**：場所を作成したユーザー。
* **[!UICONTROL 作成日]**：場所が作成された日付。

## ロケーションの作成と管理

場所を作成、編集、削除できます。

### 場所の作成

場所の作成方法について詳しくは、[&#x200B; クラウドのインポートとエクスポートの場所の設定 &#x200B;](/help/components/locations/configure-import-locations.md) を参照してください。

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 場所の編集

場所は、作成したユーザーまたはシステム管理者のみが編集できます。

場所の編集方法について詳しくは、[&#x200B; クラウドの読み込み場所と書き出し場所の設定 &#x200B;](/help/components/locations/configure-import-locations.md) を参照してください。

### 場所の削除

>[!IMPORTANT]
>
>場所が削除された場合、削除された場所に関連付けられているデータフィードファイル、Data Warehouse レポートまたは分類セットスキーマは、次回使用される際に失敗します。
>
>場所を削除する場合は、機能する場所を使用するために、[&#x200B; データフィードを編集 &#x200B;](/help/export/analytics-data-feed/create-feed.md)、[Data Warehouse レポート &#x200B;](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) および [&#x200B; 分類セットスキーマを編集 &#x200B;](/help/components/classifications/sets/manage/schema.md) する必要があります。

場所を削除できるのは、その場所を作成したユーザーまたはシステム管理者のみです。

Adobe Analyticsの Locations Manager で場所を削除するには：

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL ロケーション]** を選択し、「[!UICONTROL **ロケーション**]」タブを選択します。

1. 削除する場所の [!UICONTROL **場所名**] 列の 3 ドットメニューを選択します。

1. 「[!UICONTROL **削除**]」を選択します。

## アカウントの作成と管理

アカウントの作成、編集、削除が可能です。

### アカウントの作成

アカウントの作成方法について詳しくは、[&#x200B; クラウドへのインポートおよびエクスポートアカウントの設定 &#x200B;](/help/components/locations/configure-import-accounts.md) を参照してください。

### アカウントの編集

アカウントは、作成したユーザーまたはシステム管理者のみが編集できます。

アカウントの編集方法について詳しくは、[&#x200B; クラウドへのインポートおよびエクスポートアカウントの設定 &#x200B;](/help/components/locations/configure-import-accounts.md) を参照してください。

### アカウントキーの表示

アカウントを作成すると、そのアカウントに関連付けられているアカウントキーを表示できます。 この情報は、アカウントの初回設定時に、クラウドプロバイダーでアカウントの設定を完了しなかった場合に表示する必要がある可能性が [&#x200B; ります &#x200B;](/help/components/locations/configure-import-accounts.md)。

エクスポートアカウントに関連付けられているキーを表示するには：

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL 場所]** を選択し、「[!UICONTROL **場所アカウント**]」タブを選択します。

1. （条件付き）システム管理者の場合は、「[!UICONTROL **すべてのユーザーの場所を表示**] オプションを有効にして、組織内のすべてのユーザーが作成した場所を表示できます。<!-- Maybe add a screenshot? This is new functionality -->

1. 編集するアカウント上にある 3 ドットアイコンを選択し、「[!UICONTROL **アカウントキー**] を選択します。

### アカウントの削除

>[!IMPORTANT]
>
>アカウントを削除できるのは、そのアカウントを使用している場所がない場合のみです。 アカウントを削除する前に、まずアカウント上の場所を削除する必要があります。詳細は、[&#x200B; 場所の削除 &#x200B;](#delete-a-location) を参照してください。

アカウントを削除できるのは、そのアカウントを作成したユーザーまたはシステム管理者のみです。

アカウントを削除するには：

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL 場所]** を選択し、「[!UICONTROL **場所アカウント**]」タブを選択します。

1. （条件付き）システム管理者の場合は、「[!UICONTROL **すべてのユーザーのアカウントを表示**] オプションを有効にして、組織内のすべてのユーザーが作成した場所を表示できます。

1. 編集するアカウント上にある 3 ドットアイコンを選択し、「[!UICONTROL **アカウントを削除**]」を選択します。

## 会社全体の設定を行う（管理者のみ）

システム管理者は、ユーザーによるアカウントと場所の作成を制限したり、ユーザーが作成および使用できるアカウントのタイプを制限したりできます。

![&#x200B; 「管理設定」タブ &#x200B;](assets/locations-admin-settings.png)

### ユーザーがアカウントを作成および編集できるかどうかを構成します

デフォルトでは、組織内のすべてのユーザーがアカウントを作成し、Adobe Analytics環境で作成したアカウントを編集できます。詳しくは、[&#x200B; クラウドへのアカウントのインポートおよびエクスポートの設定 &#x200B;](/help/components/locations/configure-import-accounts.md) を参照してください。

ユーザーによるアカウントの作成を制限できます。 その場合、ユーザーは作成済みの任意のアカウントを引き続き使用できますが、編集はできません。 [&#x200B; アカウントの削除 &#x200B;](#delete-an-account) で説明しているように、ユーザーが作成したアカウントを削除できます。

すべてのユーザーによるアカウントの作成および編集を制限するには：

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL 場所]** を選択し、「[!UICONTROL **管理設定**]」タブを選択します。

1. 「[!UICONTROL **場所アカウント**]」セクションで、「[!UICONTROL **ユーザーが場所アカウントを作成および管理することを許可**]」オプションの選択を解除します。

1. 「[!UICONTROL **保存**]」を選択します。

1. （任意）ユーザーが作成したアカウントのうち、使用を希望しないものについては、「[&#x200B; アカウントの削除 &#x200B;](#delete-an-account)」の説明に従って削除します。

### ユーザーが場所を作成および編集できるかどうかを構成します

デフォルトでは、[&#x200B; クラウドのインポートとエクスポートの場所の設定 &#x200B;](/help/components/locations/configure-import-locations.md) に示すように、組織内のすべてのユーザーが、Adobe Analytics環境で作成した場所を作成および編集できます。

ユーザーによる場所の作成を制限できます。 その場合、ユーザーは作成済みの任意の場所を引き続き使用できますが、編集できなくなります。 [&#x200B; 場所の削除 &#x200B;](#delete-a-location) の説明に従って、ユーザーが作成した場所を削除できます。

すべてのユーザーに対してロケーションの作成および編集を制限するには、次のようにします。

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL 場所]** を選択し、「[!UICONTROL **管理設定**]」タブを選択します。

1. 「[!UICONTROL **場所**]」セクションで、「[!UICONTROL **ユーザーが場所を作成および管理することを許可**]」オプションの選択を解除します。

1. 「[!UICONTROL **保存**]」を選択します。

1. （任意）ユーザーが作成した場所で、使用したくない場所を削除します。詳しくは、[&#x200B; 場所の削除 &#x200B;](#delete-a-location) を参照してください。

### ユーザーが作成および使用できるアカウントタイプを制限する

次の状況では、ユーザーに表示されるアカウントタイプを制限できます。

* [&#x200B; 新しいアカウントの作成 &#x200B;](/help/components/locations/configure-import-accounts.md) の場合。

* [&#x200B; データフィード &#x200B;](/help/export/analytics-data-feed/create-feed.md) を使用したファイルの書き出し、[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) を使用したレポートの書き出し、または [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/overview.md) を使用したスキーマの読み込みの際に使用するアカウントを選択する場合。

この節で説明するようにアカウントタイプを制限すると、制限したタイプのアカウントはユーザーに表示されなくなります。 つまり、そのタイプの新しいアカウントは作成できず、そのタイプの既存のアカウントは、データフィード、Data Warehouseまたは分類セットを作成する際には使用できません。

ただし、スケジュールされた書き出し用に設定された既存のアカウントを使用しないようにする場合は、それらを削除する必要があります。

#### スケジュールされた書き出しにアカウントが使用されていないことを確認します

勘定科目のタイプを制限すると、既存の勘定科目は非表示になり、削除されません。

制限したタイプのアカウントにデータを送信するようにスケジュールが既に設定されている場合、アカウントのタイプを制限した後もスケジュールは引き続き実行され、データは引き続きアカウントに送信されます。  例えば、制限したアカウントタイプにデータを送信するようにデータフィードがスケジュールされている場合、スケジュールは引き続き実行されます。

スケジュールされた書き出しで特定のタイプのアカウントが使用されないようにする必要がある場合は、[&#x200B; アカウントのタイプを制限 &#x200B;](#limit-the-account-types-that-are-available-to-users) する前に、アカウントを削除できます。

アカウントを削除するには：

1. スケジュールされた書き出しに使用されている、制限する予定の勘定科目タイプの勘定科目を見つけます。

1. [&#x200B; アカウントの削除 &#x200B;](#delete-an-account) の説明に従って、アカウントを削除します。

1. 次の節 [&#x200B; ユーザーが使用できるアカウントタイプを制限する &#x200B;](#limit-the-account-types-that-are-available-to-users) を続行します。

#### ユーザーが使用できるアカウントタイプを制限する

アカウントの作成時および使用時にユーザーが使用できるアカウントタイプを制限するには：

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]**/**[!UICONTROL 場所]** を選択し、「[!UICONTROL **管理設定**]」タブを選択します。

1. 「[!UICONTROL **許可されるアカウントタイプ**] セクションを見つけます。

   デフォルトでは、次のアカウントタイプをユーザーが使用できます。 ユーザーによる使用を制限する勘定科目タイプの選択を解除します。

   少なくとも 1 つのアカウントタイプを選択する必要があります。

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **電子メール**]

   * 従来のアカウントタイプ（[!UICONTROL **Amazon S3**]、&lbrace;Azure [!UICONTROL **&#x200B;**]、&lbrace;FTP [!UICONTROL **、**] SFTP [!UICONTROL **など**]）

1. 「[!UICONTROL **保存**]」を選択します。


