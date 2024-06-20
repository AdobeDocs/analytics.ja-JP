---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: クラウドの読み込み場所と書き出し場所の設定
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '1687'
ht-degree: 30%

---

# クラウドの読み込み場所と書き出し場所の設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>場所を作成および編集する際は、次の点を考慮してください。<ul><li>システム管理者は、の説明に従って、ユーザーによるロケーションの作成を制限できます。 [ユーザーが場所を作成できるかどうかを構成します](/help/components/locations/locations-manager.md#configure-whether-users-can-create-locations). この節で説明するように場所を作成できない場合は、システム管理者にお問い合わせください。</li><li>場所は、作成したユーザーまたはシステム管理者のみが編集できます。</li></ul>

お先に [クラウドアカウントの設定](/help/components/locations/configure-import-accounts.md)を選択すると、そのアカウント上の場所を設定できます。 次のいずれかの目的に対して、1 つの場所を使用できます（1 つの場所を複数の目的に関連付けることはできません）。

* を使用したファイルのエクスポート [データフィード](/help/export/analytics-data-feed/create-feed.md)
* を使用したレポートのエクスポート [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* を使用したスキーマのインポート [分類セット](/help/components/classifications/sets/overview.md)

Cloud アカウントにアクセスするために必要な情報をAdobe Analyticsに入力する必要があります。 このプロセスでは、に示すように、アカウント（Amazon S3 Role ARN、Google Cloud Platform など）を追加して設定します。 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md)を設定した後、そのアカウント内での場所の追加と設定を行います（この記事で説明しています）。

既存の場所の表示および削除方法については、を参照してください [Locations manager](/help/components/locations/locations-manager.md).

## 場所の作成または編集を開始

1. Adobe Analyticsで、を選択します。 [!UICONTROL **Components**] > [!UICONTROL **場所**].

1. 日 [!UICONTROL 場所] ページで、 [!UICONTROL **場所**] タブ。

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーの場所を表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。
   ![すべてのユーザーの場所を表示](assets/locations-all-users.png)

1. 新しい場所を追加するには、を選択します。 [!UICONTROL **場所を追加**]. （アカウントをまだ追加していない場合は、の説明に従って追加します。 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md).）

   この [!UICONTROL **場所を追加**] ダイアログ表示

   または

   既存の場所を編集するには、場所名の横の「。..」メニューを選択し、次のいずれかを選択します [!UICONTROL **編集**].

   この [!UICONTROL **場所の詳細**] ダイアログが表示されます。

1. 次の情報を指定します。 |フィールド |関数 | |---------|----------| | [!UICONTROL **名前**] |場所の名前。  |
| [!UICONTROL **説明**] | 同じアカウントタイプの他のアカウントと区別できるように、アカウントの簡単な説明を入力します。| | [!UICONTROL **での使用**] |この場所を一緒に使用するかどうかを選択 [!UICONTROL **データフィード**], [!UICONTROL **Data Warehouse**]、または [!UICONTROL **分類セット**]. <p>選択を行う場合は、次の点に注意してください。</p><ul><li>1 つの場所を複数の目的に使用することはできません。 例えば、データフィードに使用される場所は、分類セットまたはData Warehouseセットにも使用できません。</li><li>ある場所内でのファイルの競合を回避するには、の値を変更しないでください [!UICONTROL **での使用**] を使用した後のフィールド。</li><li>メールアカウントの場所を作成する場合は、 [!UICONTROL **Data Warehouse**] このフィールド。 データフィードと分類セットでは、メールの場所はサポートされていません。</li></ul> | | [!UICONTROL **組織内のすべてのユーザーが場所を利用できるようにする**] |組織内の他のユーザーが場所を使用できるようにするには、このオプションを有効にします。<p>場所を共有する際は、次の点に注意してください。</p><ul><li>共有する場所の共有を解除することはできません。</li><li>共有場所は、その場所の所有者のみが編集できます。</li><li>場所を共有できるのは、その場所が関連付けられているアカウントも共有されている場合のみです。</li></ul> | | [!UICONTROL **場所アカウント**] |この場所を作成する場所アカウントを選択します。 アカウントの作成方法については、を参照してください [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md). |

1. 場所を設定するためのフォームに入力するには、で選択したアカウントタイプに対応する以下の節を続行します [!UICONTROL **場所アカウント**] フィールド。 （追加の従来のアカウントタイプも使用できますが、推奨されません。）

### Amazon S3 Role ARN

Amazon S3 ロール ARN の場所を設定するには、次の情報を指定します。

1. [場所の作成または編集を開始](#begin-creating-or-editing-a-location)（前述）。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Adobe Analytics データを送信する Amazon S3 アカウント内のバケット。 <p>Adobeから提供されたユーザー ARN に、次のものが含まれていることを確認します `S3:PutObject` このバケットにファイルをアップロードするための権限。 </p><p>バケット名は、特定の命名規則を満たす必要があります。例えば、3〜63 文字までの長さで、小文字、数字、ドット（.）、ハイフン（-）のみで構成でき、先頭と末尾は文字または数字にする必要があります。[命名規則の完全なリストについて詳しくは、AWS ドキュメントを参照してください](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   設定したアカウントと場所から、または設定したアカウントと場所にデータを読み込んだり書き出したりできるようになりました。 データをエクスポートするには、を使用します。 [データフィード](/help/export/analytics-data-feed/create-feed.md) または [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). データをインポートするには、を使用します。 [分類セット](/help/components/classifications/sets/overview.md).

   読み込まれたデータは、読み込まれた後、クラウドの宛先から削除されません。

   >[!NOTE]
   >
   >   以前にを使用したことがある場合 [分類をインポートするための FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) Adobe Analyticsには、FIN ファイルをアップロードする必要がありました。 この FIN ファイルは、クラウドアカウントから読み込む場合は必要ありません。


### Google Cloud Platform

Google Cloud Platform の場所を設定するには、次の情報を指定します。

1. [場所の作成または編集を開始](#begin-creating-or-editing-a-location)（前述）。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット**] | Adobe Analytics データを送信する GCP アカウント内のバケット。 Adobeが指定したプリンシパルに、このバケットにファイルをアップロードする権限を付与していることを確認してください。 |
   | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   設定したアカウントと場所から、または設定したアカウントと場所にデータを読み込んだり書き出したりできるようになりました。 データをエクスポートするには、を使用します。 [データフィード](/help/export/analytics-data-feed/create-feed.md) または [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). データをインポートするには、を使用します。 [分類セット](/help/components/classifications/sets/overview.md).

   読み込まれたデータは、読み込まれた後、クラウドの宛先から削除されません。

   >[!NOTE]
   >
   >   以前にを使用したことがある場合 [分類をインポートするための FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) Adobe Analyticsには、FIN ファイルをアップロードする必要がありました。 この FIN ファイルは、クラウドアカウントから読み込む場合は必要ありません。


### Azure SAS

Azure SAS の場所を設定するには、次の情報を指定します。

1. [場所の作成または編集を開始](#begin-creating-or-editing-a-location)（前述）。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   設定したアカウントと場所から、または設定したアカウントと場所にデータを読み込んだり書き出したりできるようになりました。 データをエクスポートするには、を使用します。 [データフィード](/help/export/analytics-data-feed/create-feed.md) または [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). データをインポートするには、を使用します。 [分類セット](/help/components/classifications/sets/overview.md).

   読み込まれたデータは、読み込まれた後、クラウドの宛先から削除されません。

   >[!NOTE]
   >
   >   以前にを使用したことがある場合 [分類をインポートするための FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) Adobe Analyticsには、FIN ファイルをアップロードする必要がありました。 この FIN ファイルは、クラウドアカウントから読み込む場合は必要ありません。


### Azure RBAC

Azure RBAC の場所を設定するには、次の情報を指定します。

1. [場所の作成または編集を開始](#begin-creating-or-editing-a-location)（前述）。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |
   | [!UICONTROL **コンテナ**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
   | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   設定したアカウントと場所から、または設定したアカウントと場所にデータを読み込んだり書き出したりできるようになりました。 データをエクスポートするには、を使用します。 [データフィード](/help/export/analytics-data-feed/create-feed.md) または [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). データをインポートするには、を使用します。 [分類セット](/help/components/classifications/sets/overview.md).

   読み込まれたデータは、読み込まれた後、クラウドの宛先から削除されません。

   >[!NOTE]
   >
   >   以前にを使用したことがある場合 [分類をインポートするための FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) Adobe Analyticsには、FIN ファイルをアップロードする必要がありました。 この FIN ファイルは、クラウドアカウントから読み込む場合は必要ありません。

### 電子メール

メールの場所を設定するには、次の情報を指定します。

1. [場所の作成または編集を開始](#begin-creating-or-editing-a-location)（前述）。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **件名**] | 電子メールメッセージの件名。 |
   | [!UICONTROL **メモ**] | 電子メールメッセージのコンテンツ。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **保存**]」を選択します。

   を使用する際に設定したアカウントと場所にデータを書き出せるようになりました [データフィード](/help/export/analytics-data-feed/create-feed.md). （メールの場所は、ではサポートされていません。 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) または [分類セット](/help/components/classifications/sets/overview.md)）に設定します。

### 従来のアカウントタイプ

これらのレガシーアカウントタイプは、でデータを書き出す場合にのみ使用できます [データフィード](/help/export/analytics-data-feed/create-feed.md) および [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). でデータをインポートする場合、これらのオプションは使用できません [分類セット](/help/components/classifications/sets/manage/schema.md).

+++FTP

データフィードデータは、Adobeまたは顧客がホストする FTP ロケーションに配信できます。 ディレクトリの指定パスフィールドを使用して、フィードファイルをフォルダーに配置します。

| フィールド | 関数 |
|---------|----------|
| [!UICONTROL **ディレクトリパス**] | FTP サーバー上のディレクトリのパスを入力します。 フォルダーは既に存在する必要があります。指定したパスが存在しない場合、フィードはエラーをスローします。 </br>例： `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

データフィードデータは、Adobeまたは顧客がホストする SFTP の場所に配信できます。 宛先サイトには、有効な RSA または DSA 公開キーが含まれている必要があります。 フィードの作成時に、適切な公開キーをダウンロードできます。

| フィールド | 関数 |
|---------|----------|
| [!UICONTROL **ディレクトリパス**] | FTP サーバー上のディレクトリのパスを入力します。 フォルダーは既に存在する必要があります。指定したパスが存在しない場合、フィードはエラーをスローします。 </br>例： `/folder_name/folder_name`. |

{style="table-layout:auto"}

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

+++Azure Blob

データウェアハウスは Azure BLOB の宛先をサポートしています。コンテナ、アカウント、およびキーが必要です。Amazon は保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。詳細については、Microsoft Azure ドキュメント内の「[ストレージアカウントの作成](https://docs.microsoft.com/ja-jp/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)」を参照してください。

>[!NOTE]
>
>データウェアハウス宛先のディスク領域を管理するには、独自のプロセスを実装する必要があります。アドビはサーバーからデータを削除しません。

+++


