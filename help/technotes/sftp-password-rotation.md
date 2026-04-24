---
title: FTPおよびSFTP サーバーのセキュリティ要件
description: FTPおよびSFTP サーバーのセキュリティ要件について説明します。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 40c4d507a885e9d8b91ba296db4884bc7c8b98b8
workflow-type: tm+mt
source-wordcount: '1933'
ht-degree: 4%

---

# FTPおよびSFTP サーバーのセキュリティ要件

このページでは、Adobe Analytics Data FeedsまたはData Warehouseによって配信されるデータを受信する既存のFTP サーバーとSFTP サーバーのセキュリティ要件について説明します。

* **既存のFTP サーバー**: SFTPを使用するようにアップグレードする必要があります。以下の節「[SFTP サーバーをSFTP](#upgrade-ftp-servers-to-use-sftp)を使用するようにアップグレードする」で説明します。

  SFTPからSFTPへのアップグレードは、SFTPでセキュリティを強化できるため、必須です。

  また、より高度なセキュリティを確保するために、最新のクラウドの宛先に移行することもできます。 （詳しくは、[ クラウドのインポートとエクスポートのアカウントの設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts)を参照してください）。

* **既存のSFTP サーバー（および新しくアップグレードされたSFTP サーバー）**：古いパスワードをローテーションする必要があります。以下の節「[SFTP パスワードをローテーションする](#rotate-your-sftp-password)」で説明します。

  SFTP パスワードの定期的なローテーションは、データの保護に役立つセキュリティのベストプラクティスです。

>[!IMPORTANT]
>
>この記事の手順を完了する前に、次の状況を考慮してください。
>
>* **Adobeでは、可能であればSFTPにアップグレードするのではなく、最新のクラウドの宛先に移行することをお勧めします。**
>FTPとSFTPは従来の宛先タイプです。 この記事で説明したように、FTP アカウントをSFTPにアップグレードしてSFTP パスワードをローテーションするのではなく、Adobeでは、最新のクラウド宛先タイプ（Amazon S3、Google Cloud Platform、Azureなど）に移行することをお勧めします。 これらのクラウドの宛先は、より高いレベルのセキュリティを提供します。 詳しくは、[ クラウドのインポートとエクスポートのアカウントの設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts)を参照してください。
>
>* **FTP アカウントとSFTP アカウントが分類にのみ使用されている場合は、分類セットに移行します。**
>お使いのFTP アカウントまたはSFTP アカウントがClassifications専用に使用されている場合は、この記事で説明されているように、FTP アカウントをSFTPにアップグレードしてSFTP パスワードをローテーションするのではなく、**Classifications インポーター**&#x200B;から&#x200B;**Classification セット**&#x200B;に移行する必要があります。 分類インポーターは廃止され、2026年8月31日&#x200B;**以降はアクセスできなくなります。**&#x200B;詳しくは、[分類セットの概要](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview)を参照してください。

## 前提条件

### FTP アカウントのインベントリ

データフィードまたはData Warehouseで使用されるすべてのFTP サイトについて、このページのSFTP アップグレード手順を完了する必要があります。

そのため、データフィードまたはData Warehouseのデータを受信しているすべてのFTP アカウントを特定する必要があります。 この情報は、[ クラウドの読み込みと書き出しのアカウントの設定](/help/components/locations/configure-import-accounts.md)の記事[従来のアカウントタイプ ](/help/components/locations/configure-import-accounts.md#configure-a-location-account) セクションで説明されているように、FTPの設定設定に表示されます。

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

   AdobeでホストされているSFTP サーバーを使用する場合、AdobeはRSA キーとed25519 キーをサポートしています。

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

1. [!UICONTROL **アカウントタイプ**] ドロップダウンメニューで、[!UICONTROL **SFTP （レガシー）**]&#x200B;を選択します。

1. 以下のフィールドに入力します。

   | フィールド名 | 関数 |
   |---------|----------|
   | [!UICONTROL **ホスト名**] | SFTP ホスト名（例：`ftp.omniture.com`）。 |
   | [!UICONTROL **ポート**] | データを送信するファイアウォールポート。 これは、AdobeでホストされるSFTP接続のポート 22です。 |
   | [!UICONTROL **ユーザー名**] | SFTP ユーザー名。 FTP アカウントに使用したのと同じユーザー名を使用します。 |

1. 「[!UICONTROL **保存**]」を選択します。

1. [!UICONTROL **Account created**] ダイアログで、RSAまたはed25519公開鍵をダウンロードし、[!UICONTROL **OK**]&#x200B;を選択します。 これは、AdobeがSFTP サーバーにデータをアップロードするために使用するSSH公開鍵です。 （このキーは、次の節「[AdobeのSSH公開鍵をSFTP サーバーに追加](#add-adobes-ssh-public-key-to-the-sftp-server)」で使用します）。

1. 作成するSFTP アカウントごとに、このプロセスを繰り返します。

1. 次の節に進み、[公開鍵をSFTP サーバー](#upload-the-public-key-to-the-sftp-server)にアップロードします。

#### AdobeのSSH公開鍵を[!DNL `authorized_keys`] ファイルに追加し、FTP サーバーにアップロードします

前のセクションの手順7でダウンロードした公開鍵は、AdobeがSFTP サーバーに&#x200B;**データをアップロード**&#x200B;するために使用する公開鍵と秘密鍵のペアの一部です。

この公開鍵は、以前に組織のダウンロードキーを追加した同じ[!DNL `authorized_keys`] ファイル（[で生成した公開鍵）に追加する必要があります。手順1: データをダウンロードするための組織のSSH キーを生成](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)）。

AdobeのSSH公開鍵を[!DNL `authorized_keys`] ファイルに追加し、FTP サーバーにアップロードするには：

1. FTP サーバーからデータをダウンロードするワークステーションにログインします。

1. [!DNL `authorized_keys`] ファイルを開き、Adobeのアップロードキーをファイルに追加します。 このファイルには、[から組織のダウンロードキーが既に含まれている必要があります。手順1: データをダウンロードするための組織のSSH キーを生成する](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)。

1. [!DNL `authorized_keys`] ファイルをFTP サーバーにアップロードします。

   1. FTP サーバーに接続し、ユーザー名とパスワードでログインします。
これは、AdobeがホストするFTP サーバーまたは独自のFTP サーバーです。
   1. [!DNL .ssh] ディレクトリを作成します（存在しない場合）。
   1. [!DNL `authorized_keys`] ファイルを [!DNL .ssh] ディレクトリにアップロードします。

1. ファイアウォール設定を更新して、SFTP サーバーからのインバウンド接続を許可します。 AdobeでホストされているSFTP サーバーを使用する場合は、ポート 22でAdobeのIP範囲からのインバウンド接続を許可します。

1. SFTP クライアントを使用してサーバーにログインして、接続をテストします。

1. 前のセクション [SFTP アカウントを作成](#create-the-sftp-account)で作成した各SFTP アカウントに対して、このプロセスを繰り返します。

1. 次のセクションに進みます。[ アカウント内の場所を追加する](#add-a-location-within-the-account)。

#### アカウント内の場所の追加

1. 「[!UICONTROL **場所**]」タブで、「[!UICONTROL **場所を追加**]」を選択します。

1. 名前、説明、およびこの場所をデータフィードまたはData Warehouseで使用するかどうかを指定します。

1. [!UICONTROL **場所アカウント**] フィールドで、作成したアカウントを選択します。

1. 「[!UICONTROL **ディレクトリパス**]」フィールドで、SFTP サーバー上のディレクトリへのパスを指定します。 パス内のフォルダーは既に存在している必要があります。存在しない場合は、エラーが発生します。 例：`/folder_name/folder_name`。

1. 「[!UICONTROL **保存**]」を選択します。

1. 作成したSFTP アカウントごとに、このプロセスを繰り返します。

詳しい手順については、[ クラウドの読み込みと書き出しの場所の設定](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations)を参照してください。

### 手順3：新しいSFTP宛先を使用するようにデータフィードとData Warehouse リクエストを編集する

現在FTP宛先にデータを送信している既存のスケジュール済みデータフィードとData Warehouse リクエストを更新して、作成した新しいSFTP宛先を使用します。

#### データフィードを編集

古いFTP宛先で設定されているスケジュールされた各データフィードを編集して、新しいSFTP宛先を使用します。

1. Adobe Analyticsで、[!UICONTROL **管理者**] > [!UICONTROL **データフィード**]&#x200B;を選択します。

1. 編集するデータフィードを探します。 データフィードを検索するには、[ フィルターを実行して、データフィードのリストを検索します](#filter-and-search-the-list-of-data-feeds)。

1. [!UICONTROL **フィード名**]&#x200B;列でデータフィードを選択します。

   [!UICONTROL **編集&#x200B;_フィード名_**] ページが表示されます。

1. [!UICONTROL **宛先**] セクションの&#x200B;[!UICONTROL **アカウント**] フィールドで、ドロップダウンメニューを使用して、作成した新しいSFTP宛先を選択します。

1. [!UICONTROL **場所**] フィールドで、ドロップダウンメニューを使用してSFTP アカウント内の場所を選択します。

1. 「[!UICONTROL **保存**]」を選択します。

詳しくは、[ データフィードの管理](/help/export/analytics-data-feed/df-manage-feeds.md)の[ データフィードの編集](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)を参照してください。

#### Data Warehouse リクエストの編集

古いFTP宛先で設定されているスケジュールされた各Data Warehouse リクエストを編集して、新しいSFTP宛先を使用します。

1. Adobe Analytics で、[!UICONTROL **ツール**]／[!UICONTROL **データウェアハウス**]&#x200B;を選択します。

1. データウェアハウスページで、編集するリクエストを選択します。

   ![リクエストの管理](/help/technotes/assets/dw-manage-request.png)

1. 「[!UICONTROL **編集**]」を選択します。

1. 「[!UICONTROL **レポートの宛先**]」タブを選択します。

1. [!UICONTROL **アカウント**] フィールドで、ドロップダウンメニューを使用して、作成した新しいSFTP宛先を選択します。

1. [!UICONTROL **場所**] フィールドで、ドロップダウンメニューを使用してSFTP アカウント内の場所を選択します。

1. 「[!UICONTROL **変更を保存**]」を選択します。

詳しくは、[Data Warehouse リクエストの管理](/help/export/data-warehouse/data-warehouse-requests-manage.md)の[ リクエストの編集](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)を参照してください。

### 手順4：ファイアウォール設定の更新

ファイアウォールの設定をまだ更新していない場合は、次のように更新する必要があります。

* **AdobeのFTP サーバーを使用する場合**: ファイアウォールの設定を更新して、ポート 22で&#x200B;**送信**&#x200B;接続を許可する必要があります。

* **独自のFTP サーバーを使用する場合**: サービスをホストしているポート（通常はポート 22）で&#x200B;**インバウンド**&#x200B;接続を許可するように、ファイアウォールの設定を更新する必要があります。

また、ポート 21でインバウンド接続を許可するなど、古いFTP固有のルールを削除する必要があります。 （FTPはポート 21と、データ転送のための追加ポートの範囲を使用します。 セキュリティのベストプラクティスとして、最終的にファイアウォールを通じてこの不要なアクセスを削除する必要があります）。

### 手順5：スケジュールされたデータフィードとData Warehouse リクエストが正しく配信されていることを確認する

既存のデータフィードとData Warehouseの各リクエストを更新して、新しいSFTP アカウントと場所を使用し、次にスケジュールされた配信を待ちます。 データが期待どおりに新しい宛先に届くことを確認します。

### 手順6：アップグレードしたSFTP サーバーでパスワードを回転する

FTP サーバーをSFTPにアップグレードした後、次の節「[SFTP パスワードのローテーション ](#rotate-your-sftp-password)」で説明しているように、SFTP パスワードもローテーションする必要があります。

## SFTP パスワードのローテーション

キーベースの認証が失敗した場合、SFTP パスワードはフォールバック認証方法として機能します。

FTPからSFTPにアップグレードした後、すぐにSFTP パスワードを回転します。 確立したポリシーに従って、定期的にローテーションを継続する必要があります。

1. Adobe カスタマーケアにお問い合わせいただき、新しいパスワードをリクエストしてください。

1. SFTP アカウントごとに、**ホスト名**&#x200B;と&#x200B;**ユーザー名**&#x200B;を指定します。

   カスタマーケアは、各FTP アカウントに新しいパスワードを生成します。

1. SFTP サーバーへの接続に使用するクライアントのパスワードを更新します。


