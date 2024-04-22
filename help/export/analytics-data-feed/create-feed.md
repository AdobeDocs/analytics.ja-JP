---
title: データフィードの作成
description: データフィードの作成方法を説明します。
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 40c64e104dbc3ba97807ef9fee653252d2fdd55e
workflow-type: tm+mt
source-wordcount: '4043'
ht-degree: 42%

---

# データフィードの作成

データフィードを作成する際は、次のAdobeを提供します。

* 生データファイルの送信先に関する情報

* 各ファイルに含めるデータ

>[!NOTE]
>
>データフィードを作成する前に、データフィードの基本を理解し、すべての前提条件を満たしていることを確認することが重要です。 詳しくは、を参照してください [データフィードの概要](data-feed-overview.md).

## データフィードの作成と設定

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
1. 右上の 9 つの正方形のアイコンを選択し、 [!UICONTROL **Analytics**].
1. 上部のナビゲーションバーで、 [!UICONTROL **Admin**] > [!UICONTROL **データフィード**].
1. を選択 [!UICONTROL **追加**].

   ![データフィードを追加](assets/datafeed-add.png)

   ページには、次の 3 つの主なカテゴリが表示されます。 [!UICONTROL **フィード情報**], [!UICONTROL **宛先**]、および [!UICONTROL **データ列の定義**].
1. が含まれる [!UICONTROL **フィード情報**] セクションで、次のフィールドに入力します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **名前**] | データフィードの名前。 選択したレポートスイート内で一意である必要があり、最大 255 文字まで設定できます。 |
   | [!UICONTROL **レポートスイート**] | データフィードの基になるレポートスイート。 同じレポートスイートに対して複数のデータフィードを作成する場合は、異なる列定義を持つ必要があります。データフィードをサポートするのはソースレポートスイートのみです。仮想レポートスイートはサポートされていません。 |
   | [!UICONTROL **完了時にメールで通知**] | フィードの処理が完了したときに通知されるメールアドレス。 電子メールアドレスは正しい形式にする必要があります。 |
   | [!UICONTROL **フィード間隔**] | を選択 **日次** （バックフィルまたは履歴データ用）。 毎日のフィードには、レポートスイートのタイムゾーンの午前 0 時から午前 0 時まで、1 日分のデータが含まれます。 を選択 **毎時** データを継続する場合（必要に応じて、フィードを継続する場合は毎日も利用できます）。 時間別フィードには、1 時間分のデータが含まれます。 |
   | [!UICONTROL **遅延処理**] | データフィードファイルを処理するまで、所定の時間待機します。 遅延は、モバイル実装に、オフラインデバイスがオンラインになり、データを送信する機会を与えるのに役立ちます。また、以前に処理されたファイルを管理する際に、組織のサーバー側のプロセスに対応するためにも使用できます。ほとんどの場合、遅延は必要ありません。フィードは、最大 120 分遅れる可能性があります。 |
   | [!UICONTROL **開始日と終了日**] | 開始日は、データフィードを開始する日付を示します。 履歴データのデータフィードの処理をすぐに開始するには、データが収集される過去の任意の日付にこの日付を設定します。 開始日と終了日は、レポートスイートのタイムゾーンに基づきます。 |
   | [!UICONTROL **連続給紙**] | このチェックボックスをオンにすると、終了日が削除され、フィードを無期限に実行できます。 フィードが履歴データの処理を完了すると、フィードはデータが特定の時間または日に収集を完了するのを待ちます。現在の時間または日が終わると、指定した遅延の後に処理が開始されます。 |

1. が含まれる [!UICONTROL **宛先**] セクション、内 [!UICONTROL **タイプ**] ドロップダウンメニューで、データの送信先を選択します。

   >[!NOTE]
   >
   >レポートの宛先を設定する際には、次の点を考慮してください。
   >
   >* レポートの宛先にはクラウドアカウントを使用することをお勧めします。 [従来の FTP アカウントと SFTP アカウント](#legacy-destinations) は使用可能ですが、推奨されていません。
   >* 以前に設定したクラウドアカウントは、データフィードに使用できます。 クラウドアカウントは、次のいずれかの方法で設定できます。
   >
   >   * のクラウドアカウントを設定する場合 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
   >   
   >   * 条件 [Adobe Analytics分類データの読み込み](/help/components/locations/locations-manager.md) （分類データの読み込みのために設定された場所は使用できません。）
   >   
   >   * 場所マネージャーからの [コンポーネント/場所](/help/components/locations/configure-import-accounts.md)
   >
   >* クラウドアカウントは Adobe Analytics ユーザーアカウントに関連付けられています。他のユーザーは、設定したクラウドアカウントを使用したり、表示したりできません。
   >
   >* の場所マネージャーから作成した任意の場所を編集できます [コンポーネント/場所](/help/components/locations/configure-import-accounts.md)

   ![データフィードの宛先ドロップダウンメニュー](assets/datafeed-destinations-dropdown.png)

   データフィードを作成する際は、次のいずれかの宛先タイプを使用します。 設定手順については、宛先のタイプを展開してください。 （追加の[従来の宛先](#legacy-destinations)も使用できますが、お勧めしません）。

   +++Amazon S3

   フィードは Amazon S3 バケットに直接送信できます。この宛先タイプに必要なのは、Amazon S3 アカウントと場所（バケット）のみです。

   Adobe Analyticsでは、クロスアカウント認証を使用して、Adobe AnalyticsからAmazon S3 インスタンスの指定場所にファイルをアップロードします。

   Amazon S3 バケットをデータフィードの宛先として設定するには：

   1. の説明に従って、データ フィードの作成を開始します [データフィードの作成と設定](#create-and-configure-a-data-feed).

   1. が含まれる [!UICONTROL **宛先**] セクション、内 [!UICONTROL **タイプ**] ドロップダウンメニューから選択 [!UICONTROL **Amazon S3**].

      ![Amazon S3 の宛先](assets/datafeed-destination-amazons3.png)

   1. を選択 [!UICONTROL **場所を選択**].

      Amazon S3 の場所の書き出しページが表示されます。

   1. （条件付き）Amazon S3 アカウント（およびそのアカウント上の場所）が既にAdobe Analyticsで設定されている場合は、データフィードの宛先として使用できます。

      >[!NOTE]
      >
      >アカウントは、自分で設定した場合、または自分が属する組織と共有されていた場合にのみ使用できます。

      1. [!UICONTROL **アカウントを選択**]&#x200B;ドロップダウンメニューからアカウントを選択します。

         Adobe Analyticsの次の領域のいずれかで設定されたクラウドアカウントを使用できます。

         * Adobe Analytics分類データを読み込む場合（を参照） [スキーマ](/help/components/classifications/sets/manage/schema.md).

           ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

         * の説明に従って、[Locations] 領域でアカウントとロケーションを設定する場合 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md) および [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

      1. 「」から場所を選択します [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. を選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

      これで、指定したAmazon S3 の場所にデータを送信するように宛先が設定されました。

   1. （条件付き）Amazon S3 アカウントをまだ追加していない場合は次のようにします。

      1. 「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | アカウントの名前。 任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | アカウントの説明。 |
         | [!UICONTROL **役割 ARN**] | アドビが Amazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN（Amazon リソースネーム）を指定する必要があります。これを行うには、ソースアカウントの IAM 権限ポリシーを作成し、そのポリシーをユーザーに関連付けてから、宛先アカウントの役割を作成します。詳しくは、[この AWS ドキュメント](https://repost.aws/ja/knowledge-center/cross-account-access-iam)を参照してください。 |
         | [!UICONTROL **ユーザー ARN**] | ユーザー ARN（Amazon リソースネーム）は、アドビが指定します。このユーザーを作成したポリシーに関連付ける必要があります。 |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **場所を追加**]&#x200B;を入力し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | アカウントの名前。 |
         | [!UICONTROL **説明**] | アカウントの説明。 |
         | [!UICONTROL **バケット**] | Adobe Analytics データを送信する Amazon S3 アカウント内のバケット。 <p>このバケットにファイルをアップロードするには、アドビが提供したユーザー ARN に `S3:PutObject` 権限があることを確認してください。この権限により、ユーザー ARN は初期ファイルをアップロードし、以降のアップロードでファイルを上書きできます。</p><p>バケット名は、特定の命名規則を満たす必要があります。 例えば、3 ～ 63 文字の長さにする必要があり、小文字、数字、ドット （.）、ハイフン （–）のみで構成でき、先頭と末尾は文字または数字にする必要があります。 [命名規則の完全なリストについては、AWS ドキュメントを参照してください](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
         | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、指定したAmazon S3 の場所にデータを送信するように宛先が設定されました。

      1. （条件付き）作成したばかりの宛先（アカウントと場所）を管理する必要がある場合は、で使用できます [Locations manager](/help/components/locations/locations-manager.md).

+++

   +++Azure RBAC

   RBAC 認証を使用して、フィードを Azure コンテナに直接送信できます。 この宛先タイプには、アプリケーション ID、テナント ID および秘密鍵が必要です。

   データフィードの宛先として Azure RBAC アカウントを設定するには：

   1. Adobe Analyticsで認証に使用できる Azure アプリケーションをまだ作成していない場合は、作成し、アクセス制御（IAM）でアクセス権限を付与します。

      詳しくは、を参照してください [Azure Active Directory アプリケーションの作成方法に関するMicrosoft Azure のドキュメント](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Adobe Analyticsの Admin Console で、 [!UICONTROL **宛先**] セクション、内 [!UICONTROL **タイプ**] ドロップダウンメニューから選択 [!UICONTROL **Azure RBAC**].

      ![Azure RBAC の宛先](assets/datafeed-destination-azurerbac.png)

   1. を選択 [!UICONTROL **場所を選択**].

      Azure RBAC の書き出し場所ページが表示されます。

   1. （条件付き） Azure RBAC アカウント（およびそのアカウント上の場所）が既にAdobe Analyticsで設定されている場合は、データフィードの宛先として使用できます。

      >[!NOTE]
      >
      >アカウントは、自分で設定した場合、または自分が属する組織と共有されていた場合にのみ使用できます。

      1. [!UICONTROL **アカウントを選択**]&#x200B;ドロップダウンメニューからアカウントを選択します。

      Adobe Analyticsの次のエリアのいずれかで設定したクラウドアカウントを使用できます。

      * Adobe Analytics分類データを読み込む場合（を参照） [スキーマ](/help/components/classifications/sets/manage/schema.md).

        ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

      * の説明に従って、[Locations] 領域でアカウントとロケーションを設定する場合 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md) および [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

      1. 「」から場所を選択します [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. を選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、指定した Azure RBAC の場所にデータを送信するように宛先が設定されました。

   1. （条件付き） Azure RBAC アカウントをまだ追加していない場合：

      1. 「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | Azure RBAC アカウントの名前。 この名前は [!UICONTROL **アカウントを選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | Azure RBAC アカウントの説明。 この説明は [!UICONTROL **アカウントを選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
         | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーションの登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
         | [!UICONTROL **シークレット**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **場所を追加**]&#x200B;を入力し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | 場所の名前。 この名前は [!UICONTROL **場所を選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **説明**] | 場所の説明。 この説明は [!UICONTROL **場所を選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |
         | [!UICONTROL **コンテナ**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。以前に作成した Azure アプリケーションにファイルをアップロードする権限を付与します。 |
         | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure RBAC アカウントの設定時に指定したアプリケーション ID に、コンテナ（フォルダー）にアクセスするための `Storage Blob Data Contributor` の役割が付与されていることを確認します。</p> <p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p> |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、指定した Azure RBAC の場所にデータを送信するように宛先が設定されました。

      1. （条件付き）作成したばかりの宛先（アカウントと場所）を管理する必要がある場合は、で使用できます [Locations manager](/help/components/locations/locations-manager.md).

+++

   +++Azure SAS

   SAS 認証を使用して、フィードを Azure コンテナに直接送信できます。 この宛先タイプには、アプリケーション ID、テナント ID、Key Vault URI、Key Vault シークレット名、シークレットが必要です。

   Azure SAS をデータフィードの宛先として設定するには：

   1. Adobe Analyticsで認証に使用できる Azure アプリケーションをまだ作成していない場合は、作成します。

      詳しくは、を参照してください [Azure Active Directory アプリケーションの作成方法に関するMicrosoft Azure のドキュメント](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Adobe Analyticsの Admin Console で、 [!UICONTROL **宛先**] セクションで選択 [!UICONTROL **Azure SAS**].

      ![Azure SAS の宛先](assets/datafeed-destination-azuresas.png)

   1. を選択 [!UICONTROL **場所を選択**].

      Azure SAS エクスポートの場所ページが表示されます。

   1. （条件付き） Azure SAS アカウント（およびそのアカウント上の場所）が既にAdobe Analyticsで設定されている場合は、データフィードの宛先として使用できます。

      >[!NOTE]
      >
      >アカウントは、自分で設定した場合、または自分が属する組織と共有されていた場合にのみ使用できます。

      1. [!UICONTROL **アカウントを選択**]&#x200B;ドロップダウンメニューからアカウントを選択します。

         Adobe Analyticsの次のエリアのいずれかで設定したクラウドアカウントを使用できます。

         * Adobe Analytics分類データを読み込む場合（を参照） [スキーマ](/help/components/classifications/sets/manage/schema.md).

           ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

         * の説明に従って、[Locations] 領域でアカウントとロケーションを設定する場合 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md) および [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

      1. 「」から場所を選択します [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. を選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、指定した Azure SAS の場所にデータを送信するように宛先が設定されました。

   1. （任意） Azure SAS アカウントをまだ追加していない場合：

      1. 「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | Azure SAS アカウントの名前。 この名前は [!UICONTROL **アカウントを選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | Azure SAS アカウントの説明。 この説明は [!UICONTROL **アカウントを選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
         | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。Microsoft Azure では、この情報はアプリケーション内の「**概要**」タブにあります。詳しくは、[Microsoft ID プラットフォームにアプリケーションを登録する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |
         | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS URI へのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS URI をシークレットとして保存する必要があります。 詳しくは、[Azure Key Vault で秘密鍵を設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。</p><p>Key Vault URI の作成後：<ul><li>作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。</li><li>Key Vault URI にアクセスするには、アプリケーション ID に `Key Vault Certificate User` 組み込みの役割が付与されていることを確認してください。</br><p>詳しくは、[Azure の組み込みの役割](https://learn.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)を参照してください。</p></li></ul><p>詳しくは、[Key Vault アクセスポリシーの割り当て方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/general/assign-access-policy?tabs=azure-portal)を参照してください。</p> |
         | [!UICONTROL **Key Vault シークレット名**] | Azure Key Vault にシークレットを追加する際に作成したシークレット名。Microsoft Azure では、この情報は、作成した Key Vault の **Key Vault** 設定ページにあります。詳しくは、[Azure Key Vault からシークレットを設定および取得する方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/azure/key-vault/secrets/quick-create-portal?source=recommendations)を参照してください。 |
         | [!UICONTROL **シークレット**] | 作成した Azure アプリケーションからシークレットをコピーします。Microsoft Azure では、この情報はアプリケーション内の「**証明書とシークレット**」タブにあります。詳しくは、[Microsoft ID プラットフォームでのアプリケーション登録方法に関する Microsoft Azure ドキュメント](https://learn.microsoft.com/ja-jp/entra/identity-platform/quickstart-register-app)を参照してください。 |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **場所を追加**]&#x200B;を入力し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | 場所の名前。 この名前は [!UICONTROL **場所を選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **説明**] | 場所の説明。 この説明は [!UICONTROL **場所を選択**] ドロップダウンフィールド。任意の名前を指定できます。 |
         | [!UICONTROL **コンテナ**] | Adobe Analytics データの送信先として指定したアカウント内のコンテナ。 |
         | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/`<p>Azure SAS アカウントを設定する際に、Key Vault シークレット名フィールドで指定した SAS URI ストアに `Write` 権限。 これにより、SAS URI を使用して Azure コンテナにファイルを作成できます。 <p>SAS URI でファイルも上書きする場合は、SAS URI ストアにが含まれていることを確認してください `Delete` 権限。</p><p>詳しくは、Azure Blob Storage ドキュメントの [Blob Storage のリソース](https://learn.microsoft.com/ja-jp/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)を参照してください。</p> |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、指定した Azure SAS の場所にデータを送信するように宛先が設定されました。

      1. （条件付き）作成したばかりの宛先（アカウントと場所）を管理する必要がある場合は、で使用できます [Locations manager](/help/components/locations/locations-manager.md).

+++

   +++Google Cloud Platform

   フィードをGoogle Cloud Platform （GCP）バケットに直接送信できます。 この宛先タイプに必要なのは、GCP アカウント名と場所（バケット）名のみです。

   Adobe Analyticsは、クロスアカウント認証を使用して、Adobe Analyticsから GCP インスタンスの指定された場所にファイルをアップロードします。

   データフィードの宛先として GCP バケットを設定するには：

   1. Adobe Analyticsの Admin Console で、 [!UICONTROL **宛先**] セクションで選択 [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform の宛先](assets/datafeed-destination-gcp.png)

   1. を選択 [!UICONTROL **場所を選択**].

      GCP エクスポート場所ページが表示されます。

   1. （条件付き）Google Cloud Platform アカウント（およびそのアカウント上の場所）が既にAdobe Analyticsで設定されている場合は、データフィードの宛先として使用できます。

      >[!NOTE]
      >
      >アカウントは、自分で設定した場合、または自分が属する組織と共有されていた場合にのみ使用できます。

      1. [!UICONTROL **アカウントを選択**]&#x200B;ドロップダウンメニューからアカウントを選択します。

         Adobe Analyticsの次のエリアのいずれかで設定したクラウドアカウントを使用できます。

         * Adobe Analytics分類データを読み込む場合（を参照） [スキーマ](/help/components/classifications/sets/manage/schema.md).

           ただし、分類データの読み込み用に設定されている場所は使用できません。代わりに、以下に示すように、新しい宛先を追加します。

         * の説明に従って、[Locations] 領域でアカウントとロケーションを設定する場合 [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md) および [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

      1. 「」から場所を選択します [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. を選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、指定したGoogle Cloud Platform の場所にデータを送信するように宛先が設定されました。

   1. （条件付き） GCP アカウントをまだ追加していない場合は次のようにします。

      1. 「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | アカウントの名前。 任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | アカウントの説明。 |
         | [!UICONTROL **プロジェクト ID**] | お客様の Google Cloud プロジェクト ID。[プロジェクト ID の取得に関する Google Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=ja#identifying_projects)を参照してください。 |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **場所を追加**]&#x200B;を入力し、次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **元本**] | プリンシパルはAdobeで提供されます。 このプリンシパルへのフィードを受信する権限を付与する必要があります。 |
         | [!UICONTROL **名前**] | アカウントの名前。 |
         | [!UICONTROL **説明**] | アカウントの説明。 |
         | [!UICONTROL **バケット**] | Adobe Analytics データを送信する GCP アカウント内のバケット。 <p>アドビが提供するプリンシパルに対して、次のいずれかの権限を付与していることを確認します。<ul><li>`roles/storage.objectCreator`：プリンシパルで GCP アカウント内のファイルの作成にのみ制限する場合は、この権限を使用します。</br>**重要：**&#x200B;スケジュールされたレポートでこの権限を使用する場合は、新しくスケジュールされた書き出しごとに一意のファイル名を使用する必要があります。そうしないと、プリンシパルには既存のファイルを上書きするアクセス権がないので、レポートの生成は失敗します。</li><li>（推奨） `roles/storage.objectUser`:GCP アカウントのファイルを表示、リスト、更新、削除するためのアクセス権をプリンシパルに付与する場合は、この権限を使用します。</br>この権限により、プリンシパルで、新しくスケジュールされた書き出しごとに一意のファイル名を自動生成することなく、以降のアップロードのために既存のファイルを上書きできます。</li></ul><p>権限の付与について詳しくは、Google Cloud ドキュメントの[バケットレベルのポリシーにプリンシパルを追加する](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=ja#bucket-add)を参照してください。</p> |
         | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダー。フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。例：`folder_name/` |

         {style="table-layout:auto"}

      1. を選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、指定した GCP の場所にデータを送信するように宛先が設定されました。

      1. （条件付き）作成したばかりの宛先（アカウントと場所）を管理する必要がある場合は、で使用できます [Locations manager](/help/components/locations/locations-manager.md).

+++

1. が含まれる  [!UICONTROL **データ列の定義**] セクションで、最新のを選択します [!UICONTROL **すべてのAdobe Columns**] ドロップダウンでテンプレートを選択し、次のフィールドに入力します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **エスケープ文字の削除**] | データを収集する場合、一部の文字（改行など）が問題の原因となる可能性があります。 フィードファイルからこれらの文字を削除する場合は、このチェックボックスをオンにします。 |
   | [!UICONTROL **圧縮フォーマット**] | 使用する圧縮のタイプ。 **Gzip** 次の場所のファイルを出力 `.tar.gz` 形式。 **郵便番号** 次の場所のファイルを出力 `.zip` 形式。 |
   | [!UICONTROL **パッケージのタイプ**] | を選択 [!UICONTROL **複数のファイル**] ほとんどのデータフィードに適用できます。 このオプションは、データを非圧縮の 2 GB チャンクにページ化します。 （次の場合 [!UICONTROL **複数のファイル**] オプションが選択され、レポートウィンドウの非圧縮データが 2GB 未満で、1 つのファイルが送信されます）。 選択 **単一ファイル** がを出力します `hit_data.tsv` ファイルを 1 つの巨大なファイルに保存する場合。 |
   | [!UICONTROL **マニフェスト**] | Adobeがを配信するかどうかを決定します [マニフェストファイル](c-df-contents/datafeeds-contents.md#feed-manifest) フィード間隔でデータが収集されなかった場合に宛先に送信します。 を選択する場合 **マニフェストファイル**&#x200B;データが収集されない場合は、次のようなマニフェストファイルが返されます。<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **列テンプレート**] | 多数のデータフィードを作成する場合、Adobeでは、列テンプレートを作成することをお勧めします。 列テンプレートを選択すると、指定した列が自動的にテンプレートに含まれます。また、アドビでは、デフォルトで複数のテンプレートを提供しています。 |
   | [!UICONTROL **使用可能な列**] | Adobe Analyticsで使用可能なすべてのデータ列。 「[!UICONTROL すべて追加]」をクリックして、データフィードにすべての列を含めます。 |
   | [!UICONTROL **含まれる列**] | データフィードに含める列。 データフィードからすべての列を削除するには、[!UICONTROL すべて削除]をクリックします。 |
   | [!UICONTROL **CSV をダウンロード**] | 含まれているすべての列を含んだ CSV ファイルをダウンロードします。 |

1. を選択 [!UICONTROL **保存**] 右上。

   履歴データの処理は直ちに開始されます。 データの処理が 1 日完了すると、設定した宛先にファイルが送信されます。

   データフィードにアクセスする方法と、その内容の詳細については、を参照してください。 [データフィードの内容 – 概要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## 従来の宛先

>[!IMPORTANT]
>
>この節で説明する宛先は従来のもので、お勧めしません。データフィードを作成する際は、代わりに、Amazon S3、Google Cloud Platform、Azure RBAC または Azure SAS のいずれかの宛先を使用します。 参照： [データフィードの作成と設定](#create-and-configure-a-data-feed) これらの各推奨される宛先に関する詳細情報。


次の情報は、従来の各宛先の設定情報を示します。

### FTP

データフィードデータは、Adobeまたは顧客がホストする FTP ロケーションに配信できます。 FTP ホスト、ユーザー名、パスワードが必要です。パスフィールドを使用して、フィードファイルをフォルダーに配置します。フォルダーが既に存在する必要があります。指定されたパスが存在しない場合、フィードはエラーをスローします。

使用可能フィールドに入力する際は、次の情報を使用してください。

* [!UICONTROL **ホスト**]：目的の FTP 宛先 URL を入力します。 例：`ftp://ftp.omniture.com`。
* [!UICONTROL **パス**]：空白にできます
* [!UICONTROL **ユーザー名**]：FTP サイトにログインするためのユーザー名を入力します。
* [!UICONTROL **パスワードとパスワードの確認**]：FTP サイトにログインするためのパスワードを入力します。

### SFTP

データフィードの SFTP サポートを利用できます。SFTP ホスト、ユーザー名、および宛先サイトに有効な RSA または DSA 公開鍵が含まれている必要があります。フィードの作成時に、適切な公開キーをダウンロードできます。

### S3

フィードは Amazon S3 バケットに直接送信できます。この宛先タイプには、バケット名、アクセスキー ID および秘密キーが必要です。詳しくは、Amazon S3 ドキュメント内の [Amazon S3 バケットの命名要件](https://docs.aws.amazon.com/ja_jp/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)を参照してください。

データフィードのアップロードに使用するユーザーには、次の[権限](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)が必要です。

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >Amazon S3 バケットにアップロードするたびに、 [!DNL Analytics] バケットに必要なポリシーがあるかどうかに関係なく、バケットの所有者を BucketOwnerFullControl ACL に追加します。 詳しくは、「」を参照してください[Amazon S3 データフィードの BucketOwnerFullControl 設定とは何ですか。](df-faq.md#BucketOwnerFullControl)“

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

データフィードは Azure BLOB の宛先をサポートしています。コンテナ、アカウント、およびキーが必要です。Amazon は保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。詳細については、Microsoft Azure ドキュメント内の「[ストレージアカウントの作成](https://docs.microsoft.com/ja-jp/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)」を参照してください。

>[!NOTE]
>
>フィード宛先のディスク領域を管理するには、独自のプロセスを実装する必要があります。アドビはサーバーからデータを削除しません。
