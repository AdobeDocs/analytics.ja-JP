---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: レポートの送信先の設定リクエストのData Warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d40e03ce743c286abe8364ff99f5c3c3a1fe6ecc
workflow-type: tm+mt
source-wordcount: '2342'
ht-degree: 14%

---

# レポートの送信先の設定リクエストのData Warehouse

>[!AVAILABILITY]
>
>この記事 ( およびこの節の他のData Warehouse記事 ) で説明するData Warehouse機能の一部は、リリースの制限付きテスト段階でのみ使用でき、お使いの環境ではまだ使用できない場合があります。
>
>すべてのお客様がまだ利用できない機能について、およびこれらの機能のリリースのタイムラインについて詳しくは、 [リリースノート](/help/release-notes/latest.md).
>
>このメモは、機能が一般入手可能になったら削除されます。Analytics リリースプロセスについて詳しくは、[Adobe Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

設定リクエストを作成する際には、様々な設定オプションをData Warehouseできます。 次の情報では、リクエストのレポートの宛先を設定する方法を説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>レポートの宛先を設定する際は、次の点を考慮してください。
>
>* レポートの送信先には、クラウドアカウントまたは電子メールを使用することをお勧めします。 レガシー FTP および SFTP アカウントを使用できますが、お勧めしません。
>
>* クラウドアカウントはAdobe Analyticsユーザーアカウントに関連付けられています。 他のユーザーは、設定したクラウドアカウントを使用または表示できません。
>
>* 以前に使用したすべてのクラウドアカウント [データフィード用に設定](/help/export/analytics-data-feed/create-feed.md) は、Data Warehouseに使用できます。
>
>* 用に設定されたクラウドアカウント [Adobe Analytics分類データのインポート](/help/components/locations/locations-manager.md) クラウドからの宛先は、レポートの宛先を設定する際に使用できます。 ただし、分類データのインポート用に設定されている場所は使用できません。

Data Warehouseレポートの送信先を設定するには：

1. Adobe Analyticsでのリクエストの作成を開始するには、「 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **レポートの送信先**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-report-destination.png)

1. （条件付き）レポートの宛先として使用するアカウント（およびそのアカウントの宛先）を以前に設定した場合：

   1. 次の中からアカウントを選択します： [!UICONTROL **アカウントを選択**] ドロップダウンメニュー。

      設定した任意のクラウドアカウント [Adobe Analytics分類データのインポート](/help/components/locations/locations-manager.md) クラウドの宛先がここに表示され、使用できます。 ただし、分類データのインポート用に設定されている場所は使用できません。 代わりに、以下に示すように、新しい宛先を追加します。

   1. アカウントに関連付けられている宛先を [!UICONTROL **宛先を選択**] ドロップダウンメニュー。 <!-- Is this correct? -->

1. （条件付き）以前にアカウントを設定していない場合：

   1. 選択 [!UICONTROL **アカウントを追加**]&#x200B;次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アカウントタイプ**] | クラウドアカウントのタイプを選択します。 アカウントのタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を持つことをお勧めします。 <p>アカウントタイプを選択すると、そのアカウントタイプに固有のフィールドが表示されます。 </p> |
      | [!UICONTROL **アカウント名**] | アカウントの名前を指定します。 この名前は、ロケーションを作成する際に表示されます。 <!-- true? --> |
      | [!UICONTROL **アカウントの説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 |

      設定手順については、 [!UICONTROL **アカウントタイプ**] を選択します。

      レポートの宛先を設定する際は、次のいずれかのアカウントタイプを使用します。 設定手順については、アカウントタイプを展開します。 ( 追加の [従来の宛先](#legacy-destinations) はまた使用できますが、お勧めしません )。

      +++Amazon S3

      Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>バケットの権限の設定方法について詳しくは、 [Amazon S3 バケット内のオブジェクトへのクロスアカウントアクセスを提供するにはどうすればよいですか？](https://repost.aws/knowledge-center/cross-account-access-s3) (Amazonナレッジセンター ) |
      | [!UICONTROL **ユーザーARN**] | ユーザー ARN(Amazon Resource Name) は、Adobeが提供します。 作成したポリシーにこのユーザーを添付する必要があります。 |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Google Cloud Platform アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **プロジェクト ID**] | Google Cloud プロジェクト ID。 詳しくは、 [プロジェクト ID の取得に関するGoogle Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Azure SAS アカウントを構成するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS トークンへのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS トークンを秘密鍵として保存する必要があります。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>キー Vault URI を作成したら、作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。 詳しくは、 [Key Vault アクセスポリシーの割り当て方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Key Vault シークレットの名前**] | Azure Key Vault に秘密鍵を追加する際に作成した秘密鍵の名前。 Microsoft Azure では、この情報は、次の場所で作成した Key Vault 内の **Key Vault** 設定ページ。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Azure RBAC アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform でのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++電子メール

      電子メールアカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **受信者**] | レポートの送信時に、特定のユーザーにメール通知を送信できます。1 つの電子メールアドレスを指定するか、電子メールアドレスのコンマ区切りリストを指定します。 <!-- How does this differ from the Notification email tab? --> |

   1. 選択 [!UICONTROL **場所を追加**]&#x200B;次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **名前**] |場所の名前。  | | [!UICONTROL **説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **場所アカウント**] |で作成したロケーションアカウントを選択します。 [アカウントを追加](#add-an-account). |

   1. Adobe Analytics の [!UICONTROL **場所のプロパティ**] 「 」セクションで、ロケーションアカウントのアカウントタイプに固有の情報を指定します。

      設定手順については、 [!UICONTROL **アカウントタイプ**] を選択します。

      +++Amazon S3

      Amazon S3 の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **バケット名**] | Adobe Analyticsデータを送信するAmazon S3 アカウント内のバケット。 Adobeから提供されたユーザー ARN が、このバケットにファイルをアップロードするためのアクセス権を持っていることを確認します。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Google Cloud Platform の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **バケット名**] | Adobe Analyticsデータを送信する GCP アカウント内のバケット。 ファイルをこのバケットにアップロードするための権限が、Adobeから提供されるプリンシパルに対して付与されていることを確認します。 権限の付与について詳しくは、 [プリンシパルをバケットレベルのポリシーに追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) ( Google Cloud ドキュメント ) を参照してください。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Azure SAS の場所を構成するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **コンテナ名**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Azure RBAC の場所を設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **コンテナ名**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 前に作成した Azure アプリケーションにファイルをアップロードする権限を付与してください。 |
      | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |
      | [!UICONTROL **アカウント名**] | Azure ストレージアカウント。 |

      {style="table-layout:auto"}

+++

   1. 「[!UICONTROL **保存**]」を選択します。

      これで、設定したアカウントと場所にデータをインポートできます。

1. 引き続き、 [!UICONTROL **レポートのオプション**] タブをクリックします。 詳しくは、 [レポートリクエストのレポートオプションのData Warehouseを設定する](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## 従来の宛先

>[!IMPORTANT]
>
>この節で説明する宛先は従来のもので、お勧めしません。 Data Warehouse の宛先を作成する際は、代わりに、 Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS、電子メールのいずれかの宛先を使用してください。 これらの推奨される各宛先の詳細については、上記の情報を参照してください。

次の情報は、レガシーの各宛先の設定情報を示します。

### FTP

Data Warehouse のデータは、Adobeまたは顧客がホストする FTP の場所に配信できます。 FTP ホスト、ユーザー名、パスワードが必要です。パスフィールドを使用して、フィードファイルをフォルダーに配置します。フォルダーが既に存在する必要があります。指定されたパスが存在しない場合、フィードはエラーをスローします。

使用可能フィールドに入力する際は、次の情報を参照してください。

#### アカウントフィールド

* [!UICONTROL **アカウント名**]:FTP アカウントの名前。

* [!UICONTROL **アカウントの説明**]:FTP アカウントの説明。

* [!UICONTROL **ホスト名**]：目的の FTP の宛先 URL を入力します。 例：`ftp.company.com`。

  >[!NOTE]
  >
  >  次を含めない `ftp://` を URL の先頭に追加します。

* [!UICONTROL **ユーザー名**]:FTP サイトにログインするユーザー名を入力します。

* [!UICONTROL **パスワードとパスワードの確認**]:FTP サイトにログインするためのパスワードを入力します。

#### 場所フィールド

* [!UICONTROL **場所名**]：ファイルを送信する FTP アカウント上の場所の名前。

* [!UICONTROL **場所の説明**]:FTP アカウント上の場所の説明。

* [!UICONTROL **ディレクトリパス**]:FTP アカウント上の場所のパス。

### SFTP

Data Warehouse の SFTP サポートを利用できます。 SFTP ホスト、ユーザー名、および宛先サイトに有効な RSA または DSA 公開鍵が含まれている必要があります。Data Warehouse の宛先を作成する際に、適切な公開鍵をダウンロードできます。

使用可能フィールドに入力する際は、次の情報を参照してください。

#### アカウントフィールド

* [!UICONTROL **アカウント名**]:FTP アカウントの名前。

* [!UICONTROL **アカウントの説明**]:FTP アカウントの説明。

* [!UICONTROL **ホスト名**]：目的の SFTP の宛先 URL を入力します。 例：`sftp.company.com`。

  >[!NOTE]
  >
  >  次を含めない `sftp://` を URL の先頭に追加します。

* [!UICONTROL **ユーザー名**]:SFTP サイトにログインするユーザー名を入力します。

* [!UICONTROL **アップロード時に一時ファイル拡張子を使用**]：有効にすると、 `.part` ファイル拡張子は、アップロードプロセス中に使用されます。 SFTP サーバーでアップロード完了後にファイル名の変更が制限されていない場合は、このオプションを有効にしておきます。

* [!UICONTROL **公開鍵**]:Data Warehouse の宛先を作成する際に、適切な公開鍵をダウンロードします。

#### 場所フィールド

* [!UICONTROL **場所名**]：ファイルを送信する SFTP アカウント上の場所の名前。

* [!UICONTROL **場所の説明**]:SFTP アカウント上の場所の説明。

* [!UICONTROL **ディレクトリパス**]:SFTP アカウント上の場所のパス。

SFTP の設定について詳しくは、 [SFTP サーバーへのData Warehouseリクエストの送信](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

ウェアハウスデータはAmazon S3 バケットに直接送信できます。 この宛先タイプには、バケット名、アクセスキー ID および秘密キーが必要です。詳しくは、Amazon S3 ドキュメント内の [Amazon S3 バケットの命名要件](https://docs.aws.amazon.com/ja_jp/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)を参照してください。

Data Warehouse データをアップロードするために指定するユーザーには、以下が必要です [権限](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

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

Data Warehouse は Azure BLOB の宛先をサポートしています。 コンテナ、アカウント、およびキーが必要です。Amazon は保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。詳細については、Microsoft Azure ドキュメント内の「[ストレージアカウントの作成](https://docs.microsoft.com/ja-jp/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)」を参照してください。

>[!NOTE]
>
>Data Warehouse の宛先のディスク領域を管理するには、独自のプロセスを実装する必要があります。 アドビはサーバーからデータを削除しません。
