---
description: コンポーネントとプロジェクトをAdobe AnalyticsからCustomer Journey Analyticsに移行する方法について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 5%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行

Adobe Analytics管理者は、Adobe AnalyticsのコンポーネントとプロジェクトをCustomer Journey Analyticsに移行できます。

移行プロセスには、以下が含まれます。

* Customer Journey AnalyticsでのAdobe Analyticsプロジェクトの再作成

* Adobe Analyticsレポートスイートのディメンションと指標を、Customer Journey Analyticsのデータビューのディメンションと指標に一致させます。

  一部のディメンションと指標は自動的に一致します。それ以外のディメンションと指標は、移行プロセスの一環として手動で一致させる必要があります。

## 前提条件

プロジェクトと関連するディメンションおよび指標を移行する準備が整う前に、まず次の手順を実行する必要があります。

* Analytics ソースコネクタを使用して、Adobe AnalyticsレポートスイートデータをCustomer Journey Analyticsで表示します。 それには、次の手順を実行します。

   * [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むためのレポートスイートの設定](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [データの取り込みと使用](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ja)

* データが一致するデータビューにCustomer Journey Analytics内のユーザーがプロビジョニングされていることを確認します。

  詳しくは、 [Customer Journey AnalyticsのAdmin Console権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analyticsアクセス制御](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  「権限」タブは、Admin Console の各製品プロファイルの一部です。特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。

## 組織としての移行プランの作成

特定のプロジェクトの移行に対して一致するコンポーネントは、組織全体の将来のプロジェクトの移行に適用されるので、事前にすべてのプロジェクトの移行を計画しておくことが重要です。

プロジェクトの移行時にサイロで個々の管理者が決定を下すのを避けるために、どのディメンションと指標が何と一致するかを組織として決定する必要があります。

## Adobe AnalyticsプロジェクトのCustomer Journey Analyticsへの移行

>[!IMPORTANT]
>
>この節で説明するように、プロジェクトをCustomer Journey Analyticsに移行する前に、 [移行の計画](#plan-the-migration) 」の節を参照してください。
>
>一致するディメンションまたは指標は、このプロジェクトに対しても、組織全体で移行される今後のすべてのプロジェクトに対しても、永続的です。 続行すると、行った一致は変更できません。



1. Adobe Analyticsで、 [!UICONTROL **管理者**] 「 」タブで、「 [!UICONTROL **すべての管理者**].

1. の下 [!UICONTROL **データの設定と収集**]&#x200B;を選択します。 [!UICONTROL **コンポーネントの移行**].

1. （条件付き）移行するプロジェクトをすばやく見つけるには、次のいずれかを実行します。

   * フィルターアイコンを選択して、プロジェクトのリストをフィルターします。

     次の条件でフィルタリングできます。

      * ステータス

      * タグ

      * レポートスイート

      * 所有者

      * その他のフィルター

   * 検索フィールドを使用して、移行するプロジェクトを検索します。

1. 移行するプロジェクトにマウスを移動して、 **移行** アイコン ![プロジェクトを移行](assets/migrate.svg).

   または

   移行するプロジェクトを選択し、「 」を選択します。 [!UICONTROL **移行先Customer Journey Analytics**].

   一度に 1 つのプロジェクトのみを選択して移行できます。

   The [!UICONTROL **project_name をCustomer Journey Analyticsに移行**] ダイアログボックスが表示されます。

   <!-- add screenshot -->

1. Adobe Analytics の [!UICONTROL **プロジェクト所有者**] 「 」フィールドに、「Customer Journey Analytics」でプロジェクトの所有者に設定するユーザーの名前を入力し、ドロップダウンメニューでユーザーの名前を選択します。

   指定した所有者は、プロジェクトに対する完全な管理権限を持ちます。

1. Adobe Analytics の [!UICONTROL **レポートスイートのマッチスキーマ**] セクションで、レポートスイートを選択します。

1. Adobe Analytics の [!UICONTROL **データビュー**] ドロップダウンメニューから、プロジェクトとコンポーネントをCustomer Journey Analyticsする移行データビューを選択します。

1. 選択 [!UICONTROL **スキーマを一致**].

1. Adobe Analytics の [!UICONTROL **スキーマを一致**] セクションで、 [!UICONTROL **Dimension**] および [!UICONTROL **指標**] セクション。

   Adobe Analyticsの一部のディメンションと指標は、Customer Journey Analytics内のディメンションまたは指標に自動的に一致します。 その他のユーザーは、手動で照合する必要があります。

   **自動的に一致したディメンションと指標**

   Adobe Analyticsの一部のディメンションと指標は、Customer Journey Analytics内のディメンションまたは指標に自動的に一致します。 これらのディメンションおよび指標に対して一致する決定をおこなうことはできません。

   例えば、 **訪問回数** Adobe Analyticsの指標は、 **セッション** Customer Journey Analyticsの指標。

   任意のディメンションまたは指標を選択して、関連する ID を表示できます。

   <!-- update screenshot after I can see the Status column -->

   ![プロジェクト移行スキーマ](assets/project-migration-schema.png)

   **ディメンションと指標の手動一致**

   Adobe Analyticsの他のディメンションや指標は、Customer Journey Analytics内のディメンションや指標に自動的に一致させることはできません。

   ディメンションや指標が自動的に一致しない場合は、 [!UICONTROL **Dimension**] または [!UICONTROL **指標**] セクションヘッダー。手動で照合する必要があるディメンションまたは指標の数を示します。 テーブルには、警告アイコンが表示されます。 ![警告アイコン](assets/schema-warning.png) は、手動で照合する必要がある各ディメンションまたは指標の横に表示されます。

   <!-- update screenshot after I can see the Status column -->

   ![移行スキーマの手動一致](assets/schema-manual-map.png)

1. ディメンションと指標を手動で一致させるには、警告アイコンを含むディメンションまたは指標を選択します ![警告アイコン](assets/schema-warning.png)を選択し、 [!UICONTROL **一致するCustomer Journey Analytics指標**] フィールド ( または [!UICONTROL **一致するCustomer Journey Analyticsディメンション**] 「 」フィールド（ディメンションに一致する場合）、選択したディメンションまたは指標と一致させるCustomer Journey Analyticsのディメンションまたは指標を選択します。

   ![ディメンションと指標を一致させる](assets/schema-manual-map-drop-down.png)

   警告アイコンが表示されているディメンションまたは指標ごとに、この手順を繰り返します。

   Adobe Analyticsレポートスイートのすべてのディメンションと指標がCustomer Journey Analyticsデータビューのディメンションまたは指標と一致すると、緑色のチェックマークが付きます ![チェックマーク](assets/report-suite-check.png) は、 [!UICONTROL **レポートスイートのマッチスキーマ**] 」セクションに入力します。

1. （条件付き）移行するプロジェクトに複数のレポートスイートが含まれている場合、 [!UICONTROL **レポートスイートのマッチスキーマ**] セクションで、手順 6 ～ 10 を繰り返します。 <!-- double-check that the step numbers are still correct -->

1. 選択 [!UICONTROL **移行**].

   >[!WARNING]
   >
   >   「 」を選択すると、画面に表示される警告メッセージが表示されます [!UICONTROL **移行**]. 続行する前に、一致するディメンションまたは指標が、このプロジェクトと、組織全体で移行される今後のすべてのプロジェクトの両方に対して永続的であることを理解しておきます。 続行すると、行った一致は変更できません。
