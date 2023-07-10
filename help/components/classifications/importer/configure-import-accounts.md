---
description: 分類データのアップロード先となるクラウドインポートアカウントを設定する
keywords: Analysis Workspace
title: クラウドの読み込み場所の設定
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 6%

---

# クラウドの読み込み場所の設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

クラウドの宛先からAdobe Analytics分類データをインポートする前に、分類データを収集する場所を追加して設定する必要があります。

このプロセスは、アカウント (Amazon S3 の役割 ARN、Google Cloud Platform など ) とアカウント内の場所（アカウント内のフォルダーなど）の追加と設定で構成されます。

## アカウントを追加

クラウドの宛先アカウントにアクセスするために必要な情報をAdobe Analyticsに設定する必要があります。

1. Adobe Analyticsで、 [!UICONTROL **コンポーネント**] > [!UICONTROL **場所**].
1. の [!UICONTROL 場所] ページで、 [!UICONTROL **場所の資格情報**] タブをクリックします。
1. 選択 [!UICONTROL **アカウントを追加**]. <!-- add screenshot? -->

   アカウントを追加ダイアログが表示されます。
1. 次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **場所のアカウント名**] |ロケーションアカウントの名前。 この名前は、ロケーションを作成する際に表示されます | | [!UICONTROL **場所アカウントの説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **アカウントタイプ**] |クラウドアカウントのタイプを選択します。 アカウントのタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を持つことをお勧めします。 |
1. 内 [!UICONTROL **アカウントのプロパティ**] 「 」セクションで、選択したアカウントタイプに固有の情報を指定します。

   設定手順については、 [!UICONTROL **アカウントタイプ**] を選択します。

   +++Amazon S3 Role ARN

   Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けて、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
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
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS トークンへのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS トークンを秘密鍵として保存する必要があります。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>キー Vault URI を作成したら、作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。 詳しくは、 [Key Vault アクセスポリシーの割り当て方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Key Vault シークレットの名前**] | Azure Key Vault に秘密鍵を追加する際に作成した秘密鍵の名前。 Microsoft Azure では、この情報は、次の場所で作成した Key Vault の **Key Vault** 設定ページ 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Azure RBAC アカウントを設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **場所アカウントの秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. 「[!UICONTROL **保存**]」を選択します。

1. 続行 [場所を追加](#add-a-location).

## 場所を追加

1. 場所を追加する前に、アカウントを追加する必要があります。 [アカウントを追加](#add-an-account) まだお持ちでない場合は、
1. Adobe Analyticsで、 [!UICONTROL **コンポーネント**] > [!UICONTROL **場所**].
1. の [!UICONTROL 場所] ページで、 [!UICONTROL **場所**] タブをクリックします。
1. 選択 [!UICONTROL **場所を追加**]. <!-- add screenshot? -->

   [ ロケーション ] ダイアログが表示されます。
1. 次の情報を指定します。 |フィールド |関数 | |—|—| | [!UICONTROL **名前**] |場所の名前。  | | [!UICONTROL **説明**] |同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 | | [!UICONTROL **場所アカウント**] |で作成したロケーションアカウントを選択します [アカウントを追加](#add-an-account). |

1. 内 [!UICONTROL **場所のプロパティ**] 「 」セクションで、ロケーションアカウントのアカウントタイプに固有の情報を指定します。

   設定手順については、 [!UICONTROL **場所のアカウント**] フィールドに入力します。

   +++Amazon S3 Role ARN

   Amazon S3 の役割の ARN の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット名**] | Adobe Analyticsデータを送信するAmazon S3 アカウント内のバケット。 Adobeが提供したユーザー ARN が、このバケットにファイルをアップロードするためのアクセス権を持っていることを確認します。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Google Cloud Platform の場所を設定するには、次の情報を指定します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **バケット名**] | Adobe Analyticsデータを送信する GCP アカウント内のバケット。 ファイルをこのバケットにアップロードするための権限が、Adobeから提供されるプリンシパルに対して付与されていることを確認します。 |
   | [!UICONTROL **キープレフィックス**] | データを配置するバケット内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例えば、folder_name/ |

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