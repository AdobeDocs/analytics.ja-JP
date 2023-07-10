---
description: 分類データのアップロード先となるクラウドインポートアカウントを設定する
keywords: Analysis Workspace
title: クラウドインポートアカウントの設定
feature: Classifications
source-git-commit: 6010c65571b326759eeddc5e71f8a52212ddbb98
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 5%

---

# クラウドインポートアカウントの設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

クラウドの宛先からAdobe Analytics分類データをインポートする前に、アカウントと、そのアカウント内で分類データを収集する場所を追加して設定する必要があります。

このプロセスは、この記事で説明するアカウント (Amazon S3 の役割 ARN、Google Cloud Platform など ) の追加と設定の後、アカウント内の場所（アカウント内のフォルダーなど）の追加と設定で構成します。詳しくは、 [クラウドの読み込み場所の設定](/help/components/locations/configure-import-locations.md).

クラウドの宛先アカウントにアクセスするために必要な情報をAdobe Analyticsに設定する必要があります。

クラウドインポートアカウントを設定するには：

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

1. 続行 [クラウドの読み込み場所の設定](/help/components/locations/configure-import-locations.md).

