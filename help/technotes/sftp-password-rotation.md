---
title: FTPおよびSFTP サーバーのセキュリティ要件
description: FTPおよびSFTP サーバーのセキュリティ要件について説明します。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 3%

---

# FTPおよびSFTP サーバーのセキュリティ要件

このページでは、Adobe Analytics Data FeedsまたはData Warehouseによって配信されるデータを受信する既存のFTP サーバーとSFTP サーバーのセキュリティ要件について説明します。

* **既存のFTP サーバー**: SFTPを使用するようにアップグレードする必要があります。以下の節「[SFTP サーバーをSFTP](#upgrade-ftp-servers-to-use-sftp)を使用するようにアップグレードする」で説明します。

  SFTPからSFTPへのアップグレードは、SFTPでセキュリティを強化できるため、必須です。

  また、より高度なセキュリティを確保するために、最新のクラウドの宛先に移行することもできます。 （詳しくは、[&#x200B; クラウドのインポートとエクスポートのアカウントの設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts)を参照してください）。

* **既存のSFTP サーバー（および新しくアップグレードされたSFTP サーバー）**：古いパスワードをローテーションする必要があります。以下の節「[SFTP パスワードをローテーションする](#rotate-your-sftp-password)」で説明します。

  SFTP パスワードの定期的なローテーションは、データの保護に役立つセキュリティのベストプラクティスです。

>[!IMPORTANT]
>
>この記事の手順を完了する前に、次の状況を考慮してください。
>
>* **Adobeでは、可能であればSFTPにアップグレードするのではなく、最新のクラウドの宛先に移行することをお勧めします。**
>FTPとSFTPは従来の宛先タイプです。 この記事で説明したように、FTP アカウントをSFTPにアップグレードしてSFTP パスワードをローテーションするのではなく、Adobeでは、最新のクラウド宛先タイプ（Amazon S3、Google Cloud Platform、Azureなど）に移行することをお勧めします。 これらのクラウドの宛先は、より高いレベルのセキュリティを提供します。 詳しくは、[&#x200B; クラウドのインポートとエクスポートのアカウントの設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts)を参照してください。
>
>* **FTP アカウントとSFTP アカウントが分類専用で使用されている場合は、分類セットに移行します。**
>お使いのFTP アカウントまたはSFTP アカウントがClassifications専用に使用されている場合は、この記事で説明されているように、FTP アカウントをSFTPにアップグレードしてSFTP パスワードをローテーションするのではなく、**Classifications インポーター**&#x200B;から&#x200B;**Classification セット**&#x200B;に移行する必要があります。 分類インポーターは廃止され、2026年8月31日&#x200B;**以降はアクセスできなくなります。**&#x200B;詳しくは、[分類セットの概要](https://experienceleague.adobe.com/ja/docs/analytics/components/classifications/sets/overview)を参照してください。

## 前提条件

### FTP アカウントのインベントリ

SFTP サーバーをSFTPを使用するようにアップグレードする場合は、データフィードとData Warehouseに使用されているすべてのFTP サイトについて、このページで説明されているプロセスを完了する必要があります。

そのため、データフィードまたはData Warehouseのデータを受信しているすべてのFTP アカウントを特定する必要があります。 この情報は、[&#x200B; クラウドの読み込みと書き出しのアカウントの設定](/help/components/locations/configure-import-accounts.md#configure-a-location-account)の記事[従来のアカウントタイプ &#x200B;](/help/components/locations/configure-import-accounts.md) セクションで説明されているように、FTPの設定設定に表示されます。

アカウントごとに、次の情報を収集します。

* **ホスト**: アカウントが接続するFTP サーバーのホスト名（`ftp.omniture.com`、`ftp2.omniture.com`など）。

* **ポート**: AdobeでホストされているSFTP サーバーを使用している場合、SFTP クライアントはポート 22で接続します。 安全でないFTP接続はポート 21を使用します。

* **ユーザー名**: FTP サーバーへのログインに使用するユーザー名。

* **場所アカウント秘密鍵**: アカウントの現在のアカウント秘密鍵。 これは、FTPの場所に配信されたデータのダウンロード時に現在使用するアカウント秘密鍵（パスワード）です。 この情報は、Adobe Analyticsのインターフェイスからは入手できません。

### ツールで資格情報を更新できることを確認してください

SFTP サイトへの接続に使用するツールやスクリプト（SFTP クライアント、自動スクリプト、サードパーティのプラットフォームなど）でSFTP パスワードを更新できることを確認してください。

すべてのクライアントは、フォールバックとしてパスワードを使用してSFTP経由で接続する必要があります。

## SFTPを使用するようにFTP サーバーをアップグレードする

>[!IMPORTANT]
>
>FTP データがサードパーティのパートナー（コンサルティング会社や分析ベンダーなど）に配信される場合は、この記事の手順に従う前にサードパーティと調整してください。

### 手順1：組織のSSH キーを生成してデータをダウンロードする

この節では、SFTP サーバーから&#x200B;**データをダウンロード**&#x200B;するために使用される組織のSSH キー（公開/秘密鍵のペア）を生成する方法について説明します。

>[!NOTE]
>
>今後の手順では、Adobeが提供する別の公開鍵をダウンロードします。 これは、2番目の公開鍵と秘密鍵のペアの一部で、Adobeによって&#x200B;**SFTP サーバーにデータをアップロード**&#x200B;するために使用されます。

FTP サーバーからデータをダウンロードするための安全な転送を設定するには：

1. FTP サーバーからデータをダウンロードするワークステーションにログインします。

1. 安全な転送に使用する公開鍵と秘密鍵のペアを生成します。

   AdobeでホストされているFTP サーバーを使用する場合、AdobeはRSA キーとed25519 キーをサポートしています。

   * **Linux環境**：次のコマンドを実行して、ed25519 キーペアを生成します。

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     ポリシーでed25519 キーを使用できない場合は、次のコマンドを実行してRSA キーペアを生成します。

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **Windows環境**: PuTTYgenを使用します。

1. [!DNL `authorized_keys`]（拡張子なし）という名前のファイルを作成します。

1. 公開鍵の内容を[!DNL `authorized_keys`] ファイルにコピーします。

1. 今後の手順では、この[!DNL `authorized_keys`] ファイルに戻ってAdobeの公開鍵を追加します。この公開鍵は、AdobeがSFTP サーバーにデータをアップロードするために使用します。 次に、[!DNL `authorized_keys`] ファイルをSFTP サーバーに追加します。

### 手順2:Adobe Analyticsで新しいSFTPの場所アカウントを作成する

既存の各FTP アカウントを置き換える新しいSFTP場所アカウントを作成します。

新しいSFTP場所アカウントを作成する場合は、置き換える既存のFTP アカウントで使用されているのと同じホスト名とユーザー名を使用する必要があります。

>[!NOTE]
>
>今後の手順では、この新しい場所アカウントをデータフィードとData Warehouse配信の宛先として使用するように設定します。

#### SFTP アカウントの作成

1. Adobe Analyticsで、[!UICONTROL **コンポーネント**] > [!UICONTROL **場所**]&#x200B;に移動します。

1. 「[!UICONTROL **場所アカウント**]」タブを選択します。

1. 「[!UICONTROL **アカウントを追加**]」を選択します。

1. 「[!UICONTROL **アカウントタイプ**]」ドロップダウンフィールドで、[!UICONTROL **SFTP （レガシー）**]&#x200B;を選択します。

1. 以下のフィールドに入力します。

   | フィールド名 | 関数 |
   |---------|----------|
   | [!UICONTROL **ホスト名**] | SFTP ホスト名（例：`ftp.omniture.com`）。 |
   | [!UICONTROL **ポート**] | データを送信するファイアウォールポート。 これは、AdobeでホストされるSFTP接続のポート 22です。 |
   | [!UICONTROL **ユーザー名**] | SFTP ユーザー名。 FTP アカウントに使用したのと同じユーザー名を使用します。 |

1. 「[!UICONTROL **保存**]」を選択します。

1. [!UICONTROL **Account created**] ダイアログで、RSAまたはed25519公開鍵をダウンロードし、**[!UICONTROL OK]**&#x200B;を選択します。 これは、AdobeがSFTP サーバーにデータをアップロードするために使用するSSH公開鍵です。 （このキーは、次の節「[AdobeのSSH公開鍵をSFTP サーバーに追加](#add-adobes-ssh-public-key-to-the-sftp-server)」で使用します）。

1. 作成するSFTP アカウントごとに、このプロセスを繰り返します。

1. 次の節に進み、[公開鍵をSFTP サーバー](#upload-the-public-key-to-the-sftp-server)にアップロードします。

#### AdobeのSSH公開鍵を`authorized_keys` ファイルに追加し、FTP サーバーにアップロードします

前のセクションの手順7でダウンロードした公開鍵は、AdobeがSFTP サーバーに&#x200B;**データをアップロード**&#x200B;するために使用する公開鍵と秘密鍵のペアの一部です。

この公開鍵は、以前に組織のダウンロードキーを追加した同じ`authorized_keys` ファイルに追加する必要があります（[で生成した公開鍵ステップ 1：組織のダウンロードキーを生成し、FTP サーバーに追加する](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)）。

AdobeのSSH公開鍵を`authorized_keys` ファイルに追加し、FTP サーバーにアップロードするには：

1. FTP サーバーからデータをダウンロードするワークステーションにログインします。

1. [!DNL `authorized_keys`] ファイルを開き、Adobeのアップロードキーをファイルに追加します。 このファイルには、[から組織のダウンロードキーが既に含まれている必要があります。手順1：組織のダウンロードキーを生成し、FTP サーバーに追加します](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)。

1. [!DNL `authorized_keys`] ファイルをFTP サーバーにアップロードします。

   1. FTP サーバーに接続し、ユーザー名とパスワードでログインします。\
      これは、AdobeがホストするFTP サーバーまたは独自のFTP サーバーです。
   1. [!DNL .ssh] ディレクトリを作成します（存在しない場合）。
   1. [!DNL `authorized_keys`] ファイルを [!DNL .ssh] ディレクトリにアップロードします。

1. ファイアウォール設定を更新して、SFTP サーバーからのインバウンド接続を許可します。 AdobeでホストされているSFTP サーバーを使用する場合は、ポート 22でAdobeのIP範囲からのインバウンド接続を許可します。

1. SFTP クライアントを使用してサーバーにログインして、接続をテストします。

1. 前のセクション [SFTP アカウントを作成](#create-the-sftp-account)で作成した各SFTP アカウントに対して、このプロセスを繰り返します。

1. 次のセクションに進みます。[&#x200B; アカウント内の場所を追加する](#add-a-location-within-the-account)。

#### アカウント内の場所の追加

1. 「**場所**」タブで、「**場所を追加**」を選択します。

1. 名前、説明、およびこの場所をデータフィードまたはData Warehouseで使用するかどうかを指定します。

1. [!UICONTROL **場所アカウント**] フィールドで、作成したアカウントを選択します。

1. 「[!UICONTROL **ディレクトリパス**]」フィールドで、SFTP サーバー上のディレクトリへのパスを指定します。 パス内のフォルダーは既に存在している必要があります。存在しない場合は、エラーが発生します。 例：`/folder_name/folder_name`。

1. 「**保存**」を選択します。

1. 作成したSFTP アカウントごとに、このプロセスを繰り返します。

詳しい手順については、[&#x200B; クラウドの読み込みと書き出しの場所の設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-locations)を参照してください。

### 手順3：新しいSFTP宛先を使用するようにデータフィードとData Warehouse リクエストを編集する

現在FTP宛先にデータを送信している既存のスケジュール済みデータフィードとData Warehouse リクエストを更新して、作成した新しいSFTP宛先を使用します。

#### データフィードを編集

古いFTP宛先で設定されているスケジュールされた各データフィードを編集して、新しいSFTP宛先を使用します。

1. Adobe Analyticsで、[!UICONTROL **管理者**] > [!UICONTROL **データフィード**]&#x200B;を選択します。

1. 編集するデータフィードを探します。 データフィードを検索するには、[&#x200B; フィルターを実行して、データフィードのリストを検索します](#filter-and-search-the-list-of-data-feeds)。

1. [!UICONTROL **フィード名**]&#x200B;列でデータフィードを選択します。

   [!UICONTROL **編集&#x200B;_フィード名_**] ページが表示されます。

1. [!UICONTROL **宛先**] セクションの&#x200B;[!UICONTROL **アカウント**] フィールドで、ドロップダウンメニューを使用して、作成した新しいSFTP宛先を選択します。

1. [!UICONTROL **場所**] フィールドで、ドロップダウンメニューを使用してSFTP アカウント内の場所を選択します。

1. 「[!UICONTROL **保存**]」を選択します。

詳しくは、[&#x200B; データフィードの管理](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)の[&#x200B; データフィードの編集](/help/export/analytics-data-feed/df-manage-feeds.md)を参照してください。

#### Data Warehouse リクエストの編集

古いFTP宛先で設定されているスケジュールされた各Data Warehouse リクエストを編集して、新しいSFTP宛先を使用します。

1. Adobe Analytics で、[!UICONTROL **ツール**]／[!UICONTROL **データウェアハウス**]&#x200B;を選択します。

1. データウェアハウスページで、編集するリクエストを選択します。

   ![リクエストの管理](assets/dw-manage-request.png)

1. 「[!UICONTROL **編集**]」を選択します。

1. 「[!UICONTROL **レポートの宛先**]」タブを選択します。

1. [!UICONTROL **アカウント**] フィールドで、ドロップダウンメニューを使用して、作成した新しいSFTP宛先を選択します。

1. [!UICONTROL **場所**] フィールドで、ドロップダウンメニューを使用してSFTP アカウント内の場所を選択します。

1. 「[!UICONTROL **変更を保存**]」を選択します。

詳しくは、[Data Warehouse リクエストの管理](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)の[&#x200B; リクエストの編集](/help/export/data-warehouse/data-warehouse-requests-manage.md)を参照してください。

### 手順4：ファイアウォール設定の更新

ファイアウォールの設定をまだ更新していない場合は、次のように更新する必要があります。

* **AdobeのFTP サーバーを使用する場合**: ファイアウォールの設定を更新して、ポート 22で&#x200B;**送信**&#x200B;接続を許可する必要があります。

* **独自のFTP サーバーを使用する場合**: サービスをホストしているポート（通常はポート 22）で&#x200B;**インバウンド**&#x200B;接続を許可するように、ファイアウォールの設定を更新する必要があります。

また、ポート 21でインバウンド接続を許可するなど、古いFTP固有のルールを削除する必要があります。 （FTPはポート 21と、データ転送のための追加ポートの範囲を使用します。 セキュリティのベストプラクティスとして、最終的にファイアウォールを通じてこの不要なアクセスを削除する必要があります）。

### 手順5：スケジュールされたデータフィードとData Warehouse リクエストが正しく配信されていることを確認する

既存のデータフィードとData Warehouseの各リクエストを更新して、新しいSFTP アカウントと場所を使用し、次にスケジュールされた配信を待ちます。 データが期待どおりに新しい宛先に届くことを確認します。

### 手順6：アップグレードしたSFTP サーバーでパスワードを回転する

FTP サーバーをSFTPにアップグレードした後、次の節「[SFTP パスワードのローテーション &#x200B;](#rotate-your-sftp-password)」で説明しているように、SFTP パスワードもローテーションする必要があります。

## SFTP パスワードのローテーション

キーベースの認証が失敗した場合、SFTP パスワードはフォールバック認証方法として機能します。

FTPからSFTPにアップグレードした後、すぐにSFTP パスワードを回転します。 確立したポリシーに従って、定期的にローテーションを継続する必要があります。

1. Adobe カスタマーケアにお問い合わせいただき、新しいパスワードをリクエストしてください。

1. SFTP アカウントごとに、**ホスト名**&#x200B;と&#x200B;**ユーザー名**&#x200B;を指定します。

   カスタマーケアは、各FTP アカウントに新しいパスワードを生成します。

1. SFTP サーバーへの接続に使用するクライアントのパスワードを更新します。


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/ja/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

