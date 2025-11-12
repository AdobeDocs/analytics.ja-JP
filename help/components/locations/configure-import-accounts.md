---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: クラウドのインポートおよびエクスポートアカウントの設定
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 55%

---

# クラウドのインポートおよびエクスポートアカウントの設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>アカウントを作成および編集する際は、次の点に注意してください。 <ul><li>システム管理者は、[&#x200B; ユーザーがアカウントを作成できるかどうかを設定 &#x200B;](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts) で説明しているように、ユーザーによるアカウントの作成を制限できます。 この節で説明するようにアカウントを作成できない場合は、システム管理者にお問い合わせください。</li><li>アカウントは、作成したユーザーまたはシステム管理者のみが編集できます。</li></ul>

次の目的の一部またはすべてに使用するクラウドアカウントを設定できます。

* [&#x200B; データフィード &#x200B;](/help/export/analytics-data-feed/create-feed.md) を使用したファイルの書き出し
* [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) を使用したレポートのエクスポート
* [Report Builder](/help/analyze/report-builder/report-builder-export.md) を使用する場合のファイルのエクスポート
* [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/overview.md) を使用したスキーマのインポート

Cloud アカウントにアクセスするために必要な情報をAdobe Analyticsに入力する必要があります。 このプロセスでは、この記事で説明しているアカウント（Amazon S3 ロール ARN、Google Cloud Platform など）を追加して設定し、[&#x200B; クラウドの読み込みと書き出しの場所の設定 &#x200B;](/help/components/locations/configure-import-locations.md) で説明しているアカウント内の場所（アカウント内のフォルダーなど）を追加して設定します。

既存のアカウントの表示および削除方法について詳しくは、[&#x200B; ロケーションマネージャー &#x200B;](/help/components/locations/locations-manager.md) を参照してください。

クラウドのインポートまたはエクスポートアカウントを設定するには：

1. Adobe Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **場所**] を選択します。
1. [!UICONTROL Locations] ページで、「[!UICONTROL **Location アカウント**]」タブを選択します。
1. （条件付き）システム管理者の場合、「[!UICONTROL **すべてのユーザーのアカウントを表示**]」オプションを有効にすると、組織内のすべてのユーザーが作成したアカウントを表示できます。
   ![&#x200B; すべてのユーザーのアカウントを表示 &#x200B;](assets/accounts-all-users.png)
1. 新しいアカウントを作成するには、「[!UICONTROL **アカウントを追加**]」を選択します。

   [!UICONTROL **場所アカウントの詳細**] ダイアログが表示されます。

   または

   既存のアカウントを編集するには、編集するアカウントを見つけ、「[!UICONTROL **詳細を編集**]」ボタンを選択します。

   [!UICONTROL **アカウントを追加**] ダイアログが表示されます。

1. 次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **場所アカウント名**] | 場所アカウントの名前。 この名前は、場所を作成する際に表示されます。 |
   | [!UICONTROL **場所アカウントの説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの短い説明を入力します。 |
   | [!UICONTROL **組織内のすべてのユーザーがアカウントを使用できるようにする**] | 組織内の他のユーザーがアカウントを使用できるようにするには、このオプションを有効にします。<p>アカウントを共有する際は、次の点に注意してください。</p><ul><li>共有しているアカウントの共有を解除することはできません。</li><li>共有アカウントは、そのアカウントの所有者のみが編集できます。</li><li>共有アカウントの場所は誰でも作成できます。</li></ul> |
   | [!UICONTROL **アカウントタイプ**] | クラウドのアカウントタイプを選択します。アカウントタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を使用することをお勧めします。<p>システム管理者は、[&#x200B; ユーザーがアカウントを作成できるかどうかを設定 &#x200B;](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts) で説明されているように、ユーザーが作成できるアカウントタイプを制限できます。 この節で説明するようにアカウントを作成できない場合は、システム管理者にお問い合わせください。</p> |

1. 「[!UICONTROL **アカウントのプロパティ**]」セクションで、選択したアカウントタイプに固有の情報を指定します。

   設定手順については、選択した [!UICONTROL **アカウントタイプ**] に対応する以下の節を展開してください。 （追加の従来のアカウントタイプも使用できますが、推奨されません。）

   **アカウントの種類**

   +++Amazon S3 Role ARN

   **メモ：** データフィードとData WarehouseでAmazon S3 を使用する場合、SSE-S3 暗号化のみがサポートされます。

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
   | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault 内の SAS トークンへのパス。Azure SAS を設定するには、Azure Key Vault を使用して SAS トークンをシークレットとして保存する必要があります。 詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。</p><p>Key Vault の URI が作成されたら、Key Vault にアクセスポリシーを追加して、作成した Azure アプリケーションに権限を付与します。 詳しくは、[Key Vault アクセスポリシーの割り当て方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/assign-access-policy?tabs=azure-portal)を参照してください。</p> |
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
   >電子メール アカウントは、[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) でのみ使用できます。 （メールアカウントは、[&#x200B; データフィード &#x200B;](/help/export/analytics-data-feed/create-feed.md) または [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/overview.md)）ではサポートされていません）。

   Azure RBAC アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **受信者**] | レポートの送信時に、特定のユーザーにメール通知を送信できます。単一のメールアドレスまたはメールアドレスのコンマ区切りのリストを指定します。 |

   {style="table-layout:auto"}

   +++

   **従来のアカウントタイプ**

   これらの従来のアカウントタイプは、{ データフィード [&#x200B; および &#x200B;](/help/export/analytics-data-feed/create-feed.md)2}Data Warehouse[&#x200B; を使用してデータを書き出す場合にのみ使用できます。 &#x200B;](/help/export/data-warehouse/create-request/t-dw-create-request.md) [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/manage/schema.md) を使用してデータをインポートする場合、これらのオプションは使用できません。

   +++FTP

   データフィードデータは、Adobeまたは顧客がホストする FTP の場所に配信できます。 FTP ホスト、ユーザー名、パスワードが必要です。パスフィールドを使用して、フィードファイルをフォルダーに配置します。フォルダーが既に存在する必要があります。指定されたパスが存在しない場合、フィードはエラーをスローします。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **ホスト**] | 目的の FTP 宛先 URL を入力します。 例：`ftp.adobe.com`。 |
   | [!UICONTROL **パス**] | 空白のままにすることができます。 |
   | [!UICONTROL **ユーザー名**] | FTP サイトにログインするためのユーザー名を入力します。 |
   | [!UICONTROL **パスワードとパスワードの確認**] | FTP サイトにログインするためのパスワードを入力します。 |

   {style="table-layout:auto"}

   +++

   +++SFTP

   データフィードの SFTP サポートを利用できます。SFTP ホスト、ユーザー名、および宛先サイトに有効な RSA または DSA 公開鍵が含まれている必要があります。フィードの作成時に、適切な公開キーをダウンロードできます。

   +++

   +++S3

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

   +++

   +++Azure BLOB

   Data Warehouse は、Azure Blob 宛先をサポートします。 コンテナ、アカウント、およびキーが必要です。Amazon は保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。詳細については、Microsoft Azure ドキュメント内の「[ストレージアカウントの作成](https://docs.microsoft.com/ja-jp/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)」を参照してください。

   >[!NOTE]
   >
   >データウェアハウス宛先のディスク領域を管理するには、独自のプロセスを実装する必要があります。アドビはサーバーからデータを削除しません。

   +++

1. 「[!UICONTROL **保存**]」を選択します。

1. 引き続き [&#x200B; クラウドのインポートとエクスポートの場所を設定 &#x200B;](/help/components/locations/configure-import-locations.md) します。
