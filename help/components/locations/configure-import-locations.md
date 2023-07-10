---
description: 分類データのアップロード先となるクラウドインポートアカウントを設定する
keywords: Analysis Workspace
title: クラウドの読み込み場所の設定
feature: Classifications
source-git-commit: 4efb0623d734419c376ca5f2bf2bbd94097ee4e4
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 8%

---

# クラウドの読み込み場所の設定

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

クラウドの宛先からAdobe Analytics分類データをインポートする前に、アカウントと、そのアカウント内で分類データを収集する場所を追加して設定する必要があります。

このプロセスは、アカウント (Amazon S3 の役割 ARN、Google Cloud Platform など ) とアカウント内の場所（アカウント内のフォルダーなど）の追加と設定で構成されます。

クラウドの読み込み先を設定するには：

1. 場所を追加する前に、アカウントを追加する必要があります。 まだアカウントを追加していない場合は、 [クラウドインポートアカウントの設定](/help/components/locations/configure-import-accounts.md).
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