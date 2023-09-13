---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: レポートの送信先の設定リクエストのData Warehouse
feature: Data Warehouse
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 7%

---

# レポートの送信先の設定リクエストのData Warehouse

{{release-limited-testing}}

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
      | [!UICONTROL **アカウントタイプ**] | クラウドアカウントのタイプを選択します。 アカウントのタイプごとに 1 つのアカウントを作成し、そのアカウント内で必要に応じて複数の場所を持つことをお勧めします。 <p>アカウントタイプを選択すると、そのアカウントタイプに固有のフィールドが表示されます。 各アカウントタイプの設定手順については、選択したに対応する以下のセクションを展開してください。 </p> |
      | [!UICONTROL **アカウント名**] | アカウントの名前を指定します。 この名前は、ロケーションを作成する際に表示されます。 <!-- true? --> |
      | [!UICONTROL **アカウントの説明**] | 同じアカウントタイプの他のアカウントと区別するのに役立つ、アカウントの簡単な説明を入力します。 |

      設定手順については、 [!UICONTROL **アカウントタイプ**] を選択します。

      レポートの宛先を設定する際は、次のいずれかのアカウントタイプを使用します。 設定手順については、アカウントタイプを展開します。 （その他の従来の宛先） <!-- add link --> はまた使用できますが、お勧めしません )。

      +++Amazon S3

      Amazon S3 Role ARN アカウントを設定するには、次の情報を指定します。

      | フィールド | 関数 |
      |---------|----------|
      | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
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

      設定手順については、前に選択したアカウントタイプに対応する以下のセクションを展開してください。

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