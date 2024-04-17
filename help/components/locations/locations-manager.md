---
description: 分類データをアップロードできるクラウドインポートアカウントおよび場所を設定します
keywords: Analysis Workspace
title: 場所マネージャー
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 7b293c962428c7b8fac62a9f70ce62a0fe8f0cea
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# 場所マネージャー

場所マネージャーを使用すると、アカウントと場所を表示、作成、編集または削除できます。 これらは、次のいずれかの目的で使用できます。

* を使用したファイルのエクスポート [データフィード](/help/export/analytics-data-feed/create-feed.md)
* を使用したレポートのエクスポート [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* を使用したスキーマのインポート [分類セット](/help/components/classifications/sets/overview.md)

## 場所の表示、フィルター、検索

場所マネージャーを使用すると、作成した場所を表示できます。 システム管理者は、すべてのユーザーが作成した場所を表示できます。

1. Adobe Analyticsのロケーションマネージャーにアクセスするには、 **[!UICONTROL Components]** > **[!UICONTROL 場所]**.

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーの場所を表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。 <!-- Maybe add a screenshot? This is new functionality -->

1. 場所のリストをフィルタリングまたは検索：

   * **フィルター：** 場所のリストをフィルターするには、フィルターアイコンを選択します。

     場所は、次の項目でフィルタリングできます **[!UICONTROL 場所タイプ]**, **[!UICONTROL アカウント]**、または **[!UICONTROL 作成者]**.

     ![場所フィルター](assets/locations-filters.png)

   * **検索：** 検索フィールドに、表示する場所の名前を入力します。 入力した結果がフィルタリングされます。 次の列が検索されます。 **場所名**, **場所タイプ**, **アカウント**、および **作成者**.

1. （オプション） 1,000 個を超える場所がある場合は、最初の 1,000 個の場所のみが表示されます。 を選択 [!UICONTROL **さらに読み込む**] を選択して、さらに 1,000 個の場所を読み込みます。

## 場所マネージャーで列を設定

場所マネージャーでは、次の列を使用できます。 テーブルに表示される列をカスタマイズするには、 **テーブルをカスタマイズ** アイコン ![テーブルアイコンのカスタマイズ](assets/customize-table-icon.png).

* **[!UICONTROL 場所名]**：場所の名前。 場所名の横にある「。..」メニューを選択すると、次のいずれかを実行できます [場所を編集](/help/components/locations/configure-import-locations.md) または削除します。
* **[!UICONTROL 場所タイプ]**：場所に関連付けられたアカウントのタイプ。
* **[!UICONTROL アカウント]**：場所に関連付けられた特定のアカウント。
* **用途**：場所を使用できるアプリケーションのタイプ（データフィード、Data Warehouse、分類セットなど）。
* **[!UICONTROL 前回の使用]**：場所が最後に使用された日付。
* **[!UICONTROL 作成者]**：場所を作成したユーザー。
* **[!UICONTROL 作成日]**：場所が作成された日付。

## ロケーションの作成と管理

場所を作成、編集、削除できます。

### 場所の作成

場所の作成方法については、を参照してください。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### 場所の編集

場所の編集方法については、を参照してください。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

### 場所の削除

>[!IMPORTANT]
>
>場所が削除された場合、その削除された場所に関連付けられているデータフィードファイル、Data Warehouseレポートまたは分類セットスキーマは、次回使用される際に失敗します。
>
>場所を削除する場合、次の操作を行う必要があります [データフィードの編集](/help/export/analytics-data-feed/create-feed.md), [Data Warehouseレポート](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)、および [分類セットスキーマ](/help/components/classifications/sets/manage/schema.md) 機能する場所を使用する。

場所を削除するには：

1. で 3 ドットメニューを選択します。 [!UICONTROL **場所名**] 削除する場所の列。

1. 「[!UICONTROL **削除**]」を選択します。

## アカウントの編集

1. Adobe Analyticsのロケーションマネージャーでアカウントを編集するには、次を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所アカウント**] タブ。

1. （条件付き）システム管理者は、次を有効にできます [!UICONTROL **すべてのユーザーのアカウントの表示**] 組織内のすべてのユーザーが作成した事業所を表示するオプション。 <!-- Maybe add a screenshot? This is new functionality -->


1. を選択 [!UICONTROL **詳細を表示**] 編集するアカウント上で。

1. 必要な変更を加え、選択します。 [!UICONTROL **保存**].

## アカウントキーの表示

アカウントを作成すると、そのアカウントに関連付けられているアカウントキーを表示できます。 次の場合に、クラウドプロバイダーでアカウントの設定を完了していない場合は、この情報を表示する必要があります [最初にアカウントを設定した](/help/components/locations/configure-import-accounts.md).

エクスポートアカウントに関連付けられているキーを表示するには：

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所アカウント**] タブ。

1. 編集するアカウント上の「。..」アイコンを選択し、次に選択します [!UICONTROL **アカウントキー**].

## アカウントの削除

1. Adobe Analyticsで、を選択します。 **[!UICONTROL Components]** > **[!UICONTROL 場所]**&#x200B;を選択してから、 [!UICONTROL **場所アカウント**] タブ。

1. 編集するアカウント上の「。..」アイコンを選択し、次に選択します [!UICONTROL **アカウントを削除**]
