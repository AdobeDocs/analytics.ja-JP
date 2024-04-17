---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: クラウドの読み込み場所と書き出し場所の設定
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: c81f0b8dffe07789fce1dda6efcb5ce17406be71
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 40%

---

# クラウドの読み込み場所と書き出し場所の設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

クラウドアカウント（およびそのアカウント上の場所）を設定できます。 次のいずれかの目的で 1 つの場所を使用できます（1 つの場所を、データフィードやデータウェアハウス、Data Warehouseセットや分類セットなどの複数の目的に関連付けることはできません）。

* を使用したファイルのエクスポート [データフィード](/help/export/analytics-data-feed/create-feed.md)
* を使用したレポートのエクスポート [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* を使用したスキーマのインポート [分類セット](/help/components/classifications/sets/overview.md)

Cloud アカウントにアクセスするために必要な情報をAdobe Analyticsに入力する必要があります。 このプロセスでは、に示すように、アカウント（Amazon S3 Role ARN、Google Cloud Platform など）を追加して設定します。 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md)を設定した後、そのアカウント内での場所の追加と設定を行います（この記事で説明しています）。

新しいクラウドのインポートまたはエクスポートの場所を設定したり、既存の場所を編集したりするには：

1. Adobe Analyticsで、を選択します。 [!UICONTROL **Components**] > [!UICONTROL **場所**].
1. 日 [!UICONTROL 場所] ページで、 [!UICONTROL **場所**] タブ。
1. 新しい場所を作成するには、次を選択します [!UICONTROL **場所を追加**]. （アカウントをまだ追加していない場合は、の説明に従って追加します。 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md).）

   または

   既存の場所を編集するには、で 3 ドットメニューを選択します。 [!UICONTROL **場所名**] 編集する場所の列を選択し、 [!UICONTROL **編集**].
場所ダイアログが表示されます。

1. 次の情報を指定します。 |フィールド |関数 | |---------|----------| | [!UICONTROL **名前**] |場所の名前。  |
| [!UICONTROL **説明**] | 同じアカウントタイプの他のアカウントと区別できるように、アカウントの簡単な説明を入力します。| | [!UICONTROL **での使用**] |この場所を一緒に使用するかどうかを選択 [!UICONTROL **データフィード**], [!UICONTROL **Data Warehouse**]、または [!UICONTROL **分類セット**]. <p>選択を行う場合は、次の点に注意してください。</p><ul><li>1 つの場所を複数の目的に使用することはできません。 例えば、データフィードに使用される場所は、分類セットまたはData Warehouseセットにも使用できません。</li><li>ある場所内でのファイルの競合を回避するには、の値を変更しないでください [!UICONTROL **での使用**] を使用した後のフィールド。</li></ul> | | [!UICONTROL **場所アカウント**] |この場所を作成する場所アカウントを選択します。 アカウントの作成方法については、を参照してください [アカウントを追加](#add-an-account). |

1. Adobe Analytics の「[!UICONTROL **場所のプロパティ**]」セクションで、場所アカウントのアカウントタイプに固有の情報を指定します。

   設定手順については、で選択したアカウントタイプに対応する以下の節を展開してください [!UICONTROL **場所アカウント**] フィールド。 （追加の従来のアカウントタイプも使用できますが、推奨されません。）

   **アカウントタイプ**

   +++Amazon S3 Role ARN

   Amazon S3 ロール ARN の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット名**] | Adobe Analytics データを送信する Amazon S3 アカウント内のバケット。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Google Cloud Platform の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット名**] | Adobe Analytics データを送信する GCP アカウント内のバケット。 Adobeが指定したプリンシパルに、このバケットにファイルをアップロードする権限を付与していることを確認してください。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Azure SAS の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Azure RBAC の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **コンテナ名**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |
   | [!UICONTROL **アカウント名**] | Azure ストレージアカウント。 |

   {style="table-layout:auto"}

+++

   **従来のアカウントタイプ**

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

1. 「[!UICONTROL **保存**]」を選択します。

   設定したアカウントと場所から、または設定したアカウントと場所にデータを読み込んだり書き出したりできるようになりました。

   読み込まれたデータは、読み込まれた後、クラウドの宛先から削除されません。

   >[!NOTE]
   >
   >   以前にを使用したことがある場合 [分類をインポートするための FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) Adobe Analyticsには、FIN ファイルをアップロードする必要がありました。 この FIN ファイルは、クラウドアカウントから読み込む場合は必要ありません。

