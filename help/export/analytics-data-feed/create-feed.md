---
title: データフィードの作成
description: データフィードの作成方法を説明します。
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '3160'
ht-degree: 20%

---

# データフィードの作成

データフィードを作成する際には、次の情報をAdobeに提供します。

* 生データファイルの送信先に関する情報

* 各ファイルに含めるデータ

>[!NOTE]
>
>データフィードを作成する前に、データフィードに関する基本的な知識を持ち、必要な前提条件をすべて満たすことが重要です。 詳しくは、 [データフィードの概要](data-feed-overview.md).

## データフィードの作成と設定

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
1. 右上の 9 つの四角形のアイコンを選択し、「 [!UICONTROL **Analytics**].
1. 上部ナビゲーションバーで、に移動します。 [!UICONTROL **管理者**] > [!UICONTROL **データフィード**].
1. 選択 [!UICONTROL **追加**].

   ![データフィードを追加](assets/datafeed-add.png)

   ページが 3 つの主なカテゴリと共に表示されます。 [!UICONTROL **フィード情報**], [!UICONTROL **宛先**]、および [!UICONTROL **データ列の定義**].
1. 内 [!UICONTROL **フィード情報**] 「 」セクションで、次のフィールドに入力します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **名前**] | データフィードの名前。選択したレポートスイート内で一意である必要があり、最大 255 文字まで設定できます。 |
   | [!UICONTROL **レポートスイート**] | データフィードの基になるレポートスイート。 同じレポートスイートに対して複数のデータフィードを作成する場合は、異なる列定義を持つ必要があります。データフィードをサポートするのはソースレポートスイートのみです。仮想レポートスイートはサポートされていません。 |
   | [!UICONTROL **完了時に電子メールを送信**] | フィードの処理が終了したときに通知される電子メールアドレス。 電子メールアドレスは正しい形式にする必要があります。 |
   | [!UICONTROL **フィード間隔**] | 選択 **毎日** ：バックフィルまたは履歴データ用。 毎日のフィードには、レポートスイートのタイムゾーンの午前 0 時から午前 0 時までの 1 日分のデータが含まれます。  選択 **毎時** 継続データ用（希望する場合は、継続フィードでも Daily を使用できます） 時間別フィードには、1 時間分のデータが含まれます。 |
   | [!UICONTROL **遅延処理**] | データフィードファイルを処理する前に、所定の時間待ちます。 遅延は、モバイル実装に、オフラインデバイスがオンラインになり、データを送信する機会を与えるのに役立ちます。また、以前に処理されたファイルを管理する際に、組織のサーバー側のプロセスに対応するためにも使用できます。ほとんどの場合、遅延は必要ありません。フィードは、最大 120 分遅れる可能性があります。 |
   | [!UICONTROL **開始日と終了日**] | 開始日は、データフィードが必要な最初の日付を示します。 過去の日付を設定すると、履歴データのデータフィードの処理が直ちに開始されます。フィードは終了日に達するまで処理を続けます。開始日と終了日は、レポートスイートのタイムゾーンに基づきます。 |
   | [!UICONTROL **連続フィード**] | このチェックボックスを選択すると、終了日が削除され、フィードが無期限に実行されます。 フィードが履歴データの処理を完了すると、フィードはデータが特定の時間または日に収集を完了するのを待ちます。現在の時間または日が終わると、指定した遅延の後に処理が開始されます。 |

1. 内 [!UICONTROL **宛先**] セクション内の [!UICONTROL **タイプ**] ドロップダウンメニューで、データを送信する宛先を選択します。

   ![データフィードの宛先ドロップダウンメニュー](assets/datafeed-destinations-dropdown.png)

   データフィードの作成時に、次のいずれかのタイプの宛先を使用します。 設定手順については、宛先のタイプを展開します。 ( 追加 [レガシー宛先](#legacy-destinations) はまた使用できますが、お勧めしません )。

   +++Amazon S3

   フィードは Amazon S3 バケットに直接送信できます。この宛先タイプには、Amazon S3 アカウントと場所（バケット）のみが必要です。

   Adobe Analyticsは、クロスアカウント認証を使用して、Adobe AnalyticsからAmazon S3 インスタンスの指定した場所にファイルをアップロードします。

   Amazon S3 バケットをデータフィードの宛先として設定するには：

   1. Adobe Analytics Admin Console で、 [!UICONTROL **宛先**] セクション、選択 [!UICONTROL **Amazon S3**].

      ![Amazon S3 の宛先](assets/datafeed-destination-amazons3.png)

   1. 選択 [!UICONTROL **場所を選択**].

      Amazon S3 の書き出し場所ページが表示されます。

   1. （条件付き）以前にAmazon S3 アカウントと場所を追加している場合：

      1. 次からアカウントを選択： [!UICONTROL **アカウントを選択**] ドロップダウンメニュー。

      1. 場所を [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. 選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、宛先は、指定したAmazon S3 の場所にデータを送信するように設定されました。

   1. （条件付き）Amazon S3 アカウントをまだ追加していない場合：

      1. 選択 [!UICONTROL **アカウントを追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | アカウントの名前。 任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | アカウントの説明。 |
         | [!UICONTROL **役割 ARN**] | AdobeがAmazon S3 アカウントへのアクセス権を取得するために使用できる役割 ARN(Amazon Resource Name) を指定する必要があります。 これを行うには、ソースアカウントの IAM アクセス許可ポリシーを作成し、そのポリシーをユーザーに関連付けて、宛先アカウントのロールを作成します。 詳しくは、 [このAWSドキュメント](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **ユーザーARN**] | ユーザー ARN(Amazon Resource Name) は、Adobeが提供します。 作成したポリシーにこのユーザーを添付する必要があります。 |

         {style="table-layout:auto"}

         1. 選択 [!UICONTROL **場所を追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | アカウントの名前。 |
         | [!UICONTROL **説明**] | アカウントの説明。 |
         | [!UICONTROL **グループ**] | Adobe Analyticsデータを送信するAmazon S3 アカウント内のバケット。 Adobeが提供したユーザー ARN が、このバケットにファイルをアップロードするためのアクセス権を持っていることを確認します。 |
         | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、宛先は、指定したAmazon S3 の場所にデータを送信するように設定されました。

+++

   +++Azure RBAC

   RBAC 認証を使用して、Azure コンテナに直接フィードを送信できます。 この宛先タイプには、バケット名、アプリケーション ID、テナント ID、秘密鍵が必要です。

   Azure RBAC バケットをデータフィードの宛先として設定するには：

   1. まだ認証にAdobe Analyticsが使用できる Azure アプリケーションを作成していない場合は、アクセス制御 (IAM) のアクセス権限を付与します。

      詳しくは、 [Azure Active Directory アプリケーションの作成方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Adobe Analytics Admin Console で、 [!UICONTROL **宛先**] セクション、選択 [!UICONTROL **Azure RBAC**].

      ![Azure RBAC の宛先](assets/datafeed-destination-azurerbac.png)

   1. 選択 [!UICONTROL **場所を選択**].

      Azure RBAC の書き出し場所ページが表示されます。

   1. （条件付き）以前に Azure RBAC アカウントと場所を追加している場合：

      1. 次からアカウントを選択： [!UICONTROL **アカウントを選択**] ドロップダウンメニュー。

      1. 場所を [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. 選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、宛先は、指定した Azure RBAC の場所にデータを送信するように設定されました。

   1. （条件付き）以前に Azure RBAC アカウントを追加していない場合は、次の手順に従います。

      1. 選択 [!UICONTROL **アカウントを追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | Azure RBAC アカウントの名前。 この名前は、 [!UICONTROL **アカウントを選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | Azure RBAC アカウントの説明。 この説明は、 [!UICONTROL **アカウントを選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **場所を追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | 場所の名前。 この名前は、 [!UICONTROL **場所を選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **説明**] | 場所の説明。 この説明は、 [!UICONTROL **場所を選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **アカウント**] | Azure ストレージアカウント。 |
         | [!UICONTROL **コンテナ**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 前に作成した Azure アプリケーションにファイルをアップロードする権限を付与してください。 |
         | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、宛先は、指定した Azure RBAC の場所にデータを送信するように設定されました。

+++

   +++Azure SAS

   SAS 認証を使用して、Azure コンテナに直接フィードを送信できます。 この宛先の種類には、バケット名、アプリケーション ID、テナント ID、キー Vault URI、キー Vault 秘密鍵名、および秘密鍵が必要です。

   Azure SAS バケットをデータフィードの宛先として設定するには：

   1. Adobe Analyticsが認証に使用できる Azure アプリケーションをまだ作成していない場合は、作成します。

      詳しくは、 [Azure Active Directory アプリケーションの作成方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. Adobe Analytics Admin Console で、 [!UICONTROL **宛先**] セクション、選択 [!UICONTROL **Azure SAS**].

      ![Azure SAS の宛先](assets/datafeed-destination-azuresas.png)

   1. 選択 [!UICONTROL **場所を選択**].

      「Azure SAS の書き出し場所」ページが表示されます。

   1. （条件付き）以前に Azure SAS アカウントと場所を追加した場合：

      1. 次からアカウントを選択： [!UICONTROL **アカウントを選択**] ドロップダウンメニュー。

      1. 場所を [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. 選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、宛先は、指定した Azure SAS の場所にデータを送信するように設定されました。

   1. （条件付き）Azure SAS アカウントをまだ追加していない場合は、次の手順に従います。

      1. 選択 [!UICONTROL **アカウントを追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | Azure SAS アカウントの名前。 この名前は、 [!UICONTROL **アカウントを選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | Azure SAS アカウントの説明。 この説明は、 [!UICONTROL **アカウントを選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **アプリケーション ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **テナント ID**] | 作成した Azure アプリケーションからこの ID をコピーします。 Microsoft Azure では、この情報は **概要** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **Key Vault URI**] | <p>Azure Key Vault の SAS トークンへのパス。  Azure SAS を構成するには、Azure Key Vault を使用して SAS トークンを秘密鍵として保存する必要があります。 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>キー Vault URI を作成したら、作成した Azure アプリケーションに権限を付与するために、Key Vault にアクセスポリシーを追加します。 詳しくは、 [Key Vault アクセスポリシーの割り当て方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **Key Vault シークレットの名前**] | Azure Key Vault に秘密鍵を追加する際に作成した秘密鍵の名前。 Microsoft Azure では、この情報は、次の場所で作成した Key Vault の **Key Vault** 設定ページ 詳しくは、 [Azure Key Vault からシークレットを設定および取得する方法に関するMicrosoft Azure ドキュメント](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **秘密鍵**] | 作成した Azure アプリケーションからシークレットをコピーします。 Microsoft Azure では、この情報は **証明書と秘密鍵** 」タブをクリックします。 詳しくは、 [Microsoft Azure ドキュメント：Microsoft identity platform へのアプリケーションの登録方法に関する](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **場所を追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **名前**] | 場所の名前。 この名前は、 [!UICONTROL **場所を選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **説明**] | 場所の説明。 この説明は、 [!UICONTROL **場所を選択**] ドロップダウンフィールドに含めることができます。任意の名前を指定できます。 |
         | [!UICONTROL **コンテナ**] | Adobe Analyticsデータを送信するアカウント内のコンテナです。 |
         | [!UICONTROL **プレフィックス**] | データを配置するコンテナ内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、宛先は、指定した Azure SAS の場所にデータを送信するように設定されました。

+++

   +++Google Cloud Platform

   フィードは、Google Cloud Platform(GCP) バケットに直接送信できます。 この宛先タイプには、GCP アカウント名と場所（バケット）名のみが必要です。

   Adobe Analyticsは、クロスアカウント認証を使用して、Adobe Analyticsから GCP インスタンスの指定した場所にファイルをアップロードします。

   GCP バケットをデータフィードの宛先として設定するには：

   1. Adobe Analytics Admin Console で、 [!UICONTROL **宛先**] セクション、選択 [!UICONTROL **Google Cloud Platform**].

      ![Google Cloud Platform の宛先](assets/datafeed-destination-gcp.png)

   1. 選択 [!UICONTROL **場所を選択**].

      「 GCP Export Locations 」ページが表示されます。

   1. （条件付き）以前に GCP アカウントと場所を追加した場合：

      1. 次からアカウントを選択： [!UICONTROL **アカウントを選択**] ドロップダウンメニュー。

      1. 場所を [!UICONTROL **場所を選択**] ドロップダウンメニュー。

      1. 選択 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         これで、指定した GCP の場所にデータを送信するように宛先が設定されました。

   1. （条件付き）GCP アカウントをまだ追加していない場合：

      1. 選択 [!UICONTROL **アカウントを追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **アカウント名**] | アカウントの名前。 任意の名前を指定できます。 |
         | [!UICONTROL **アカウントの説明**] | アカウントの説明。 |
         | [!UICONTROL **プロジェクト ID**] | Google Cloud プロジェクト ID。 詳しくは、 [プロジェクト ID の取得に関するGoogle Cloud ドキュメント](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
         | [!UICONTROL **プリンシパル**] | プリンシパルはAdobeで提供されます。 フィードを受け取るには、このプリンシパルに権限を付与する必要があります。 詳しくは、 [Google Cloud ポリシーへのプリンシパルの追加に関するドキュメント](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-iam). |

         {style="table-layout:auto"}

         1. 選択 [!UICONTROL **場所を追加**]&#x200B;次の情報を指定します。

         | フィールド | 関数 |
         |---------|----------|
         | [!UICONTROL **プリンシパル**] | プリンシパルはAdobeで提供されます。 このプリンシパルにフィードを受け取る権限を付与する必要があります。 |
         | [!UICONTROL **名前**] | アカウントの名前。 |
         | [!UICONTROL **説明**] | アカウントの説明。 |
         | [!UICONTROL **グループ**] | Adobe Analyticsデータを送信する GCP アカウント内のバケット。 ファイルをこのバケットにアップロードするための権限が、Adobeから提供されるプリンシパルに対して付与されていることを確認します。 |
         | [!UICONTROL **プレフィックス**] | データを配置するバケット内のフォルダーです。 フォルダー名を指定し、名前の後にバックスラッシュを追加してフォルダーを作成します。 例：`folder_name/` |

         {style="table-layout:auto"}

      1. 選択 [!UICONTROL **作成**] > [!UICONTROL **保存**].

         これで、指定した GCP の場所にデータを送信するように宛先が設定されました。

+++

1. 内  [!UICONTROL **データ列の定義**] セクションで、最新の [!UICONTROL **すべてのAdobe Columns**] ドロップダウンのテンプレートを選択し、次のフィールドに入力します。

   | フィールド | 関数 |
   |---------|----------|
   | [!UICONTROL **エスケープ文字を削除**] | データを収集する際に、一部の文字（改行など）が問題の原因となる場合があります。 フィードファイルからこれらの文字を削除する場合は、このチェックボックスをオンにします。 |
   | [!UICONTROL **圧縮形式**] | 使用する圧縮のタイプ。 **** Gzip はファイルを `.tar.gz` 形式で出力します。**** Zip はファイルを `.zip` 形式で出力します。 |
   | [!UICONTROL **パッケージタイプ**] | 選択 **複数のファイル** ほとんどのデータフィードで使用できます。 このオプションは、非圧縮の 2GB チャンクにデータをページ分けします。 （複数のファイルを選択し、レポートウィンドウの非圧縮データが 2GB 未満の場合、1 つのファイルが送信されます）。 選択 **単一ファイル** は `hit_data.tsv` ファイルを 1 つの、潜在的に大規模なファイルに格納します。 |
   | [!UICONTROL **マニフェスト**] | Adobeが [マニフェストファイル](c-df-contents/datafeeds-contents.md#feed-manifest) を宛先に送信する必要があります（フィード間隔でデータが収集されない場合）。 次を選択した場合、 **マニフェストファイル**&#x200B;に値を指定すると、データが収集されない場合に、次のようなマニフェストファイルを受け取ります。<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **列テンプレート**] | 多数のデータフィードを作成する場合、Adobeでは列テンプレートを作成することをお勧めします。 列テンプレートを選択すると、指定した列が自動的にテンプレートに含まれます。また、アドビでは、デフォルトで複数のテンプレートを提供しています。 |
   | [!UICONTROL **使用可能な列**] | Adobe Analyticsで使用可能なすべてのデータ列。 「[!UICONTROL すべて追加]」をクリックして、データフィードにすべての列を含めます。 |
   | [!UICONTROL **含まれる列**] | データフィードに含める列。 データフィードからすべての列を削除するには、[!UICONTROL すべて削除]をクリックします。 |
   | [!UICONTROL **CSV をダウンロード**] | 含まれるすべての列を含む CSV ファイルをダウンロードします。 |

1. 選択 [!UICONTROL **保存**] をクリックします。

   履歴データの処理は直ちに開始されます。 データが 1 日分の処理を終了すると、ファイルは設定した宛先に送信されます。

   データフィードにアクセスする方法とその内容をより深く理解するには、 [データフィードの内容 — 概要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## 従来の宛先

>[!IMPORTANT]
>
>この節で説明する宛先は従来のもので、お勧めしません。 データフィードを作成する際は、代わりに、次のいずれかの宛先を使用します。Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS のいずれかです。 詳しくは、 [データフィードの作成と設定](#create-and-configure-a-data-feed) を参照してください。


次の情報は、レガシーの各宛先の設定情報を示します。

### FTP

データフィードのデータは、Adobeまたは顧客がホストする FTP の場所に配信できます。 FTP ホスト、ユーザー名、パスワードが必要です。パスフィールドを使用して、フィードファイルをフォルダーに配置します。フォルダーが既に存在する必要があります。指定されたパスが存在しない場合、フィードはエラーをスローします。

使用可能フィールドに入力する際は、次の情報を参照してください。
* [!UICONTROL **ホスト**]:目的の FTP の宛先 URL を入力します。 例：`ftp://ftp.omniture.com`。
* [!UICONTROL **パス**]:空白のままにできます
* [!UICONTROL **ユーザー名**]:FTP サイトにログインするユーザー名を入力します。
* [!UICONTROL **パスワードとパスワードの確認**]:FTP サイトにログインするためのパスワードを入力します。

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
  >Amazon S3 バケットにアップロードするたびに、[!DNL Analytics] は、バケットの所有者を BucketOwnerFullControl ACL に追加します。この ACL は、バケットに必要なポリシーがあるかどうかに関係なく追加されます。詳しくは、[Amazon S3 データフィードの BucketOwnerFullControl 設定とは何ですか？](df-faq.md#BucketOwnerFullControl)&quot;

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
