---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストのレポートの宛先を設定する
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: f0a5f72667fd6fc7847ede82d5196d9159fc558c
workflow-type: tm+mt
source-wordcount: '1980'
ht-degree: 82%

---

# Data Warehouse リクエストのレポートの宛先を設定する

Data Warehouse を作成する際には、様々な設定オプションを使用できます。次の情報では、リクエストのレポートの宛先を設定する方法を説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

>[!NOTE]
>
>レポートの宛先を設定する際には、次の点を考慮してください。
>
>* レポートの宛先には、クラウドアカウントまたはメールを使用することをお勧めします。[従来の FTP および SFTP アカウント](#legacy-destinations)を使用することはできますが、推奨していません。
>
>* 以前に設定したクラウドアカウントは、データウェアハウスに使用できます。クラウドアカウントは、次のいずれかの方法で設定できます。
>
>   * [データフィード](/help/export/analytics-data-feed/create-feed.md)を設定する場合
>   
>   * [Adobe Analytics 分類データを読み込む](/help/components/locations/locations-manager.md)場合（アカウントは使用できますが、それらのアカウントに設定されている場所は使用できません。）
>   
>   * 場所マネージャー（[コンポーネント／場所](/help/components/locations/configure-import-accounts.md)）から
>
>* クラウドアカウントは Adobe Analytics ユーザーアカウントに関連付けられています。他のユーザーは、設定したクラウドアカウントを使用したり、表示したりできません。
>
>* 場所マネージャー（[コンポーネント／場所](/help/components/locations/configure-import-accounts.md)）から作成した任意の場所を編集できます。

データウェアハウスレポートの送信先を設定するには、次の手順に従います。

1. まだ作成していない場合は、**[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]**／[!UICONTROL **追加**]&#x200B;を選択して、Adobe Analytics でリクエストの作成を開始します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しい Data Warehouse リクエストページで、「[!UICONTROL **レポートの宛先**]」タブを選択します。

   ![レポートの宛先タブ](assets/dw-report-destination.png)

1. （条件付き）クラウドアカウント（およびそのアカウントの宛先）が Adobe Analytics で既に設定されている場合は、それをレポートの宛先として使用できます。

   >[!NOTE]
   >
   >アカウントは、自分で設定した場合、または自分が属する組織と共有されていた場合にのみ使用できます。
   >
   >システム管理者の場合、「[!UICONTROL **すべての宛先を表示**]」オプションを使用できます。組織内のユーザーが作成したすべてのアカウントと場所にアクセスする場合は、このオプションを有効にします。

   1. [!UICONTROL **アカウント**] ドロップダウンメニューからアカウントを選択します。

      Adobe Analytics の次の領域のいずれかで設定したクラウドアカウントを使用できます。

      * [スキーマ](/help/components/classifications/sets/manage/schema.md)の説明に従って、Adobe Analytics 分類データを読み込む場合。

        ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

      * [クラウドの読み込みアカウントと書き出しアカウントの設定](/help/components/locations/configure-import-accounts.md)および[クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md)の説明に従って、場所領域でアカウントと場所を設定する場合。

   1. [!UICONTROL **宛先を選択**]&#x200B;ドロップダウンメニューから、アカウントに関連付けられている宛先を選択します。<!-- Is this correct? -->

1. （条件付き）Adobe Analytics で既に設定されているクラウドアカウントへのアクセス権がない場合は、次のいずれかのアカウントを設定できます。

   1. [!UICONTROL **アカウント**] ドロップダウンメニューを選択し、「[!UICONTROL **アカウントを追加**]」を選択します。

   1. アカウントを追加ダイアログボックスで、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **場所アカウント名**] | 場所アカウントの名前。 この名前は、場所を作成する際に表示されます。 |
      | [!UICONTROL **場所アカウントの説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの短い説明を入力します。 |
      | [!UICONTROL **組織内のすべてのユーザーがアカウントを使用できるようにする**] | 組織内の他のユーザーがアカウントを使用できるようにするには、このオプションを有効にします。<p>アカウントを共有する際は、次の点に注意してください。</p><ul><li>共有しているアカウントの共有を解除することはできません。</li><li>共有アカウントは、そのアカウントの所有者のみが編集できます。</li><li>共有アカウントの場所は誰でも作成できます。</li></ul> |
      | [!UICONTROL **アカウントタイプ**] | クラウドのアカウントタイプを選択します。アカウントタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を使用することをお勧めします。<p>システム管理者は、[ ユーザーがアカウントを作成できるかどうかを設定 ](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts) で説明されているように、ユーザーが作成できるアカウントタイプを制限できます。 この節で説明するようにアカウントを作成できない場合は、システム管理者にお問い合わせください。</p> |

   1. 「[!UICONTROL **アカウントのプロパティ**]」セクションで、選択したアカウントタイプに固有の情報を指定します。

      設定手順については、選択した [!UICONTROL **アカウントタイプ**] に対応する以下の節を展開してください。 （追加の従来のアカウントタイプも使用できますが、推奨されません。）

      **アカウントの種類**

      +++Amazon S3 Role ARN

      **注意：** Amazon S3 をData Warehouseで使用する場合、SSE-S3 暗号化のみがサポートされます。

      Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

      | フィールド | 機能 |
      |---------|----------|
      | [!UICONTROL **役割 ARN**] | アドビが Amazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN（Amazon リソースネーム）を指定する必要があります。これを行うには、ソースアカウントの IAM 権限ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントの役割を作成します。詳しくは、[この AWS ドキュメント](https://repost.aws/ja/knowledge-center/cross-account-access-iam)を参照してください。 |

      {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

      Google Cloud Platform アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **プロジェクト ID**] | お客様の Google Cloud プロジェクト ID。[プロジェクト ID の取得に関する Google Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=ja#identifying_projects)を参照してください。 |

      {style="table-layout:auto"}

      +++

      +++Azure SAS

      Azure SAS アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault 内の SAS トークンへのパス。Azure SAS を設定するには、Azure Key Vault を使用して SAS トークンをシークレットとして保存する必要があります。 詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。</p><p>Key Vault の URI が作成されたら、Key Vault にアクセスポリシーを追加して、作成した Azure アプリケーションに権限を付与します。 詳しくは、[Key Vault アクセスポリシーの割り当て方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/assign-access-policy?tabs=azure-portal)を参照してください。</p><p>または</p><p>アクセスポリシーを作成せずに直接アクセスロールを付与する場合は、[Azure Portal を使用して Azure ロールを割り当てる方法に関するMicrosoft Azure ドキュメントを参照してください ](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal)。 これにより、Key Vault URI にアクセスするためのアプリケーション ID の役割の割り当てが追加されます。 </p> |
      | [!UICONTROL **Key Vault シークレット名**] | Azure Key Vault にシークレットを追加する際に作成したシークレット名。 Microsoft Azure では、この情報は、作成した Key Vault の **Key Vault** 設定ページにあります。 詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。 |
      | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

      {style="table-layout:auto"}

      +++   

      +++Azure RBAC

      Azure RBAC アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

      {style="table-layout:auto"}

      +++

      +++電子メール

      >[!NOTE]
      >
      >電子メールアカウントは、[ データフィード ](/help/export/analytics-data-feed/create-feed.md) でのみ使用できます。 （メールアカウントは、[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) または [ 分類セット ](/help/components/classifications/sets/overview.md) ではサポートされていません）。

      Azure RBAC アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **受信者**] | レポートの送信時に、特定のユーザーにメール通知を送信できます。単一のメールアドレスまたはメールアドレスのコンマ区切りのリストを指定します。 |

      {style="table-layout:auto"}

      +++

1. 「[!UICONTROL **レポートオプション**]」タブでデータウェアハウスリクエストを引き続き設定します。詳しくは、[データウェアハウスのリクエストに対するレポートの宛先の設定](/help/export/data-warehouse/create-request/dw-request-report-options.md)を参照してください。

## 従来のアカウントタイプ

>[!IMPORTANT]
>
>この節で説明する宛先は従来のもので、お勧めしません。データウェアハウスの宛先を作成する際は、代わりに、Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS、またはメールのいずれかの宛先を使用してください。これらの推奨される各宛先の詳細については、上記の情報を参照してください。

次の情報は、従来の各宛先の設定情報を示します。

### FTP

データウェアハウスのデータは、アドビまたは顧客のホストする FTP の場所に配信できます。FTP ホスト、ユーザー名、パスワードが必要です。パスフィールドを使用して、フィードファイルをフォルダーに配置します。フォルダーが既に存在する必要があります。指定されたパスが存在しない場合、フィードはエラーをスローします。

使用可能フィールドに入力する際は、次の情報を使用してください。

#### アカウントフィールド

* [!UICONTROL **アカウント名**]：FTP アカウントの名前

* [!UICONTROL **アカウントの説明**]：FTP アカウントの説明

* [!UICONTROL **ホスト名**]：目的の FTP 宛先 URL を入力します。例：`ftp.company.com`。

  >[!NOTE]
  >
  >  `ftp://` を URL の先頭に含めないようにします。

* [!UICONTROL **ユーザー名**]：FTP サイトにログインするためのユーザー名を入力します。

* [!UICONTROL **パスワードとパスワードの確認**]：FTP サイトにログインするためのパスワードを入力します。

#### 場所フィールド

* [!UICONTROL **場所名**]：ファイルを送信する FTP アカウント上の場所の名前

* [!UICONTROL **場所の説明**]：FTP アカウント上の場所の説明

* [!UICONTROL **ディレクトリパス**]：FTP アカウント上の場所のパス

### SFTP

データウェアハウスの SFTP サポートを利用できます。SFTP ホスト、ユーザー名、および宛先サイトに有効な RSA または DSA 公開鍵が含まれている必要があります。データウェアハウスの宛先の作成時に、適切な公開キーをダウンロードできます。

使用可能フィールドに入力する際は、次の情報を使用してください。

#### アカウントフィールド

* [!UICONTROL **アカウント名**]：FTP アカウントの名前

* [!UICONTROL **アカウントの説明**]：FTP アカウントの説明

* [!UICONTROL **ホスト名**]：目的の SFTP 宛先 URL を入力します。例：`sftp.company.com`。

  >[!NOTE]
  >
  >  `sftp://` を URL の先頭に含めることはできません。

* [!UICONTROL **ユーザー名**]：SFTP サイトにログインするためのユーザー名を入力します。

* [!UICONTROL **アップロード時に一時ファイル拡張子を使用**]：有効にすると、`.part` ファイル拡張子は、アップロードプロセス中に使用されます。SFTP サーバーがアップロード完了後のファイル名の変更を制限しない限り、このオプションは有効のままにします。

* [!UICONTROL **公開鍵**]：データウェアハウスの宛先を作成する際に、適切な公開鍵をダウンロードします。

#### 場所フィールド

* [!UICONTROL **場所名**]：ファイルを送信する SFTP アカウント上の場所の名前

* [!UICONTROL **場所の説明**]：SFTP アカウント上の場所の説明

* [!UICONTROL **ディレクトリパス**]：SFTP アカウント上の場所のパス

SFTP の設定について詳しくは、[SFTP サーバーへのデータウェアハウスのリクエストの送信](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md)を参照してください。

### S3

ウェアハウスデータは Amazon S3 バケットに直接送信できます。この宛先タイプには、バケット名、アクセスキー ID および秘密キーが必要です。詳しくは、Amazon S3 ドキュメント内の [Amazon S3 バケットの命名要件](https://docs.aws.amazon.com/ja_jp/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)を参照してください。

データウェアハウスのデータをアップロードするために指定するユーザーには、次の[権限](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)が必要です。

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

以下の 16 の標準 AWS 地域がサポートされます（必要に応じて適切な署名アルゴリズムを使用）。

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>Cn-north-1 地域はサポートされていません。

### Azure BLOB

データウェアハウスは Azure BLOB の宛先をサポートしています。コンテナ、アカウント、およびキーが必要です。Amazon は保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。詳細については、Microsoft Azure ドキュメント内の「[ストレージアカウントの作成](https://docs.microsoft.com/ja-jp/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)」を参照してください。

>[!NOTE]
>
>データウェアハウス宛先のディスク領域を管理するには、独自のプロセスを実装する必要があります。アドビはサーバーからデータを削除しません。
