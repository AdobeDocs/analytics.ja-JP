---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストのレポートの宛先を設定する
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: f41144d5889d03441f06806256ec79aa25d242cf
workflow-type: tm+mt
source-wordcount: '2615'
ht-degree: 99%

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

   1. [!UICONTROL **アカウントを選択**]&#x200B;ドロップダウンメニューからアカウントを選択します。

      Adobe Analytics の次の領域のいずれかで設定したクラウドアカウントを使用できます。

      * [スキーマ](/help/components/classifications/sets/manage/schema.md)の説明に従って、Adobe Analytics 分類データを読み込む場合。

        ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

      * [クラウドの読み込みアカウントと書き出しアカウントの設定](/help/components/locations/configure-import-accounts.md)および[クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md)の説明に従って、場所領域でアカウントと場所を設定する場合。

   1. [!UICONTROL **宛先を選択**]&#x200B;ドロップダウンメニューから、アカウントに関連付けられている宛先を選択します。<!-- Is this correct? -->

1. （条件付き）Adobe Analytics で既に設定されているクラウドアカウントへのアクセス権がない場合は、次のいずれかのアカウントを設定できます。

   1. 「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アカウントタイプ**] | クラウドのアカウントタイプを選択します。アカウントタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を使用することをお勧めします。 <p>アカウントタイプを選択すると、そのアカウントタイプに固有のフィールドが表示されます。 </p> |
      | [!UICONTROL **アカウント名**] | アカウントの名前を指定します。この名前は、場所を作成する際に表示されます。<!-- true? --> |
      | [!UICONTROL **アカウントの説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの短い説明を入力します。 |

      設定手順については、選択した&#x200B;[!UICONTROL **アカウントタイプ**]&#x200B;に対応する以下の節を展開します。

      レポートの宛先を設定する際は、次のいずれかのアカウントタイプを使用します。設定手順については、アカウントタイプを展開します（追加の[従来の宛先](#legacy-destinations)も使用できますが、お勧めしません）。

      +++Amazon S3

      Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

      | フィールド | 機能 |
      |---------|----------|
      | [!UICONTROL **役割 ARN**] | アドビが Amazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN（Amazon リソースネーム）を指定する必要があります。これを行うには、ソースアカウントの IAM 権限ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントの役割を作成します。詳しくは、[この AWS ドキュメント](https://repost.aws/ja/knowledge-center/cross-account-access-iam)を参照してください。<p>バケットの権限の設定方法については、Amazon ナレッジセンターで [How can I provide cross-account access to objects that are in Amazon S3 buckets?](https://repost.aws/ja/knowledge-center/cross-account-access-s3)の記事を参照してください。 |
      | [!UICONTROL **ユーザー ARN**] | ユーザー ARN（Amazon リソースネーム）は、アドビが指定します。このユーザーを作成したポリシーに関連付ける必要があります。 |

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
      | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault 内の SAS URI へのパス。Azure SAS を設定するには、Azure Key Vault を使用して SAS URI を秘密鍵として保存する必要があります。詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。</p><p>Key Vault URI の作成後：<ul><li>作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。</li><li>Key Vault URI にアクセスするには、アプリケーション ID に `Key Vault Certificate User` 組み込みの役割が付与されていることを確認してください。</br><p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p></li></ul><p>詳しくは、[Key Vault アクセスポリシーの割り当て方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/assign-access-policy?tabs=azure-portal)を参照してください。</p> |
      | [!UICONTROL **Key Vault シークレット名**] | Azure Key Vault にシークレットを追加する際に作成したシークレット名。Microsoft Azure では、この情報は、作成した Key Vault の **Key Vault** 設定ページにあります。詳しくは、[Azure Key Vault からシークレットを設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。 |
      | [!UICONTROL **シークレット**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Azure RBAC アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーションの登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
      | [!UICONTROL **シークレット**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーションの登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

      {style="table-layout:auto"}

+++

      +++メール

      メールアカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **受信者**] | レポートの送信時に、特定のユーザーにメール通知を送信できます。単一のメールアドレスまたはメールアドレスのコンマ区切りのリストを指定します。<!-- How does this differ from the Notification email tab? --> |

   1. 「[!UICONTROL **場所を追加**]」を選択して、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **名前**] | 場所の名前。 |
      | [!UICONTROL **説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの短い説明を入力します。 |
      | [!UICONTROL **場所アカウント**] | [ アカウントの追加 ](#add-an-account) で作成した場所アカウントを選択します。 |

   1. Adobe Analytics の「[!UICONTROL **場所のプロパティ**]」セクションで、場所アカウントのアカウントタイプに固有の情報を指定します。

      設定手順については、以前に選択した&#x200B;[!UICONTROL **アカウントタイプ**]&#x200B;に対応する以下のセクションを展開してください。

      +++Amazon S3

      Amazon S3 の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **バケット名**] | Adobe Analytics データを送信する Amazon S3 アカウント内のバケット。 <p>このバケットにファイルをアップロードするには、アドビが提供したユーザー ARN に `S3:PutObject` 権限があることを確認してください。この権限により、ユーザー ARN は初期ファイルをアップロードし、以降のアップロードでファイルを上書きできます。</p><p>バケット名は、特定の命名規則を満たす必要があります。例えば、3〜63 文字までの長さで、小文字、数字、ドット（.）、ハイフン（-）のみで構成でき、先頭と末尾は文字または数字にする必要があります。[命名規則の完全なリストについて詳しくは、AWS ドキュメントを参照してください](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
      | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Google Cloud Platform の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **バケット名**] | Adobe Analytics データを送信する GCP アカウント内のバケット。 <p>アドビが提供するプリンシパルに次のいずれかの権限を付与していることを確認します（権限の付与について詳しくは、Google Cloud ドキュメントの[バケットレベルのポリシーにプリンシパルを追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=ja#bucket-add)を参照してください）。<ul><li>`roles/storage.objectCreator`：プリンシパルで GCP アカウント内のファイルの作成にのみ制限する場合は、この権限を使用します。</br>**重要：**&#x200B;スケジュールされたレポートでこの権限を使用する場合は、新しくスケジュールされた書き出しごとに一意のファイル名を使用する必要があります。そうしないと、プリンシパルには既存のファイルを上書きするアクセス権がないので、レポートの生成は失敗します。</li><li>`roles/storage.objectUser`：プリンシパルで GCP アカウント内のファイルの表示、一覧表示、更新、削除へのアクセス権を付与する場合は、この権限を使用します。</br>この権限により、プリンシパルで、新しくスケジュールされた書き出しごとに一意のファイル名を自動生成することなく、以降のアップロードのために既存のファイルを上書きできます。</li></ul><p>組織が[組織ポリシーの制約](https://cloud.google.com/storage/docs/org-policy-constraints)を使用して許可リスト内の Google Cloud Platform アカウントのみを許可している場合は、次のアドビ所有の Google Cloud Platform 組織 ID が必要です。 <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
      | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Azure SAS の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **コンテナ名**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure SAS アカウントを設定する際に、Key Vault 秘密鍵名フィールドに指定した SAS URI ストアに `Write` 権限があることを確認します。これにより、SAS URI で Azure コンテナにファイルを作成できます。 <p>SAS URI でファイルも上書きする場合は、SAS URI ストアに `Delete` 権限があることを確認します。</p><p>詳しくは、Azure Blob Storage ドキュメントの [Blob Storage のリソース](https://learn.microsoft.com/ja-jp/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)を参照してください。</p> |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Azure RBAC の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **コンテナ名**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure RBAC アカウントの設定時に指定したアプリケーション ID に、コンテナ（フォルダー）にアクセスするための `Storage Blob Data Contributor` の役割が付与されていることを確認します。</p> <p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p> |
      | [!UICONTROL **アカウント名**] | Azure ストレージアカウント。 |

      {style="table-layout:auto"}

+++

1. 「[!UICONTROL **レポートオプション**]」タブでデータウェアハウスリクエストを引き続き設定します。詳しくは、[データウェアハウスのリクエストに対するレポートの宛先の設定](/help/export/data-warehouse/create-request/dw-request-report-options.md)を参照してください。

## 従来の宛先

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
