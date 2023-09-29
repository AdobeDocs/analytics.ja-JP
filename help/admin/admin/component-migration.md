---
description: コンポーネントとプロジェクトをAdobe AnalyticsからCustomer Journey Analyticsに移行する方法について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 792b2171c5535fcd3920b5cbb100b2fb7c642db8
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 8%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントとプロジェクトの移行

Adobe Analytics管理者は、Adobe Analyticsプロジェクトとそれに関連するコンポーネントをCustomer Journey Analyticsに移行できます。

移行プロセスには、以下が含まれます。

* Customer Journey AnalyticsでのAdobe Analyticsプロジェクトの再作成

* ディメンションと指標をAdobe Analyticsレポートスイートから指標データビューのディメンションとCustomer Journey Analyticsにマッピングする。

  一部のディメンションと指標は自動的にマッピングされます。それ以外のディメンションと指標は、移行プロセスの一環として手動でマッピングする必要があります。 また、セグメントも移行されますが、移行プロセスの一環としてマッピングする必要はありません。

  移行が完了すると、移行されたすべてのコンポーネントが移行概要に表示されます。

## 移行の準備

組織内の誰かがプロジェクトの移行を開始する前に、次の節を完了してください。

### 前提条件

プロジェクトと関連コンポーネントを移行する準備が整う前に、まず次の手順を実行する必要があります。

* Analytics ソースコネクタを使用して、Adobe AnalyticsレポートスイートデータをCustomer Journey Analyticsで表示します。 それには、次の手順を実行します。

   * [Adobe Experience PlatformとCustomer Journey Analyticsに取り込むためのレポートスイートの設定](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [データの取り込みと使用](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ja)

* データがマッピングされるデータビューにCustomer Journey Analytics内のユーザーがプロビジョニングされていることを確認します。

  詳しくは、 [Customer Journey AnalyticsのAdmin Console権限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Customer Journey Analyticsアクセス制御](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  「権限」タブは、Admin Console の各製品プロファイルの一部です。特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。

* 移行計画を作成します（以下の節を参照）。 [組織としての移行プランの作成](#create-a-migration-plan-as-an-organization).

### 移行に含まれる機能の理解

移行に含まれるプロジェクト要素とコンポーネントの概要を次の表に示します。

#### 移行されるコンポーネント要素

|  | 移行済み |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[共有](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | × |
| **[説明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | ? |
| **[タグ](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | × |
| **[アトリビューション（ディメンションに対する）](/help/analyze/analysis-workspace/attribution/overview.md)** | ? |

{style="table-layout:auto"}

#### 移行されるプロジェクト要素

|  | 移行済み |
|---------|----------|
| **[日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[セグメント](/help/components/segmentation/seg-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[ディメンション](/help/components/dimensions/overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[指標](/help/components/metrics/overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 自動または手動でマッピング |
| **[パネル](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) 移行を実行するユーザーによって定義 |
| **[キュレーション](/help/analyze/analysis-workspace/curate-share/curate.md)** | × |
| **[共有（プロジェクトの役割）](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | × |
| **[共有（他のユーザーと共有）](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | ? <!-- if no, combine with the above and just call it sharing? What about sharing links?--> |
| **[注釈](/help/analyze/analysis-workspace/components/annotations/overview.md)** | × |
| **[フォルダー構造](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | × |
| **[説明](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![チェックマーク](assets/Smock_Checkmark_18_N.svg) |
| **[タグ](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | × |
| **[スケジュール](/help/components/scheduled-projects-manager.md)** | × |
| **[異常値検出](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)** | ? |
| **[お気に入り](/help/analyze/landing.md)** | ? |

{style="table-layout:auto"}

### エラーの原因となる、サポートされていない要素を理解する

次のビジュアライゼーション、パネルおよび機能は、Customer Journey Analyticsではサポートされていません。 これらの要素が移行前にプロジェクトに含まれている場合、移行が失敗するか、プロジェクトの移行後にエラーが発生する可能性があります。

プロジェクトをCustomer Journey Analyticsに移行する前に、これらの要素をAdobe Analyticsプロジェクトから削除します。 移行が失敗した場合は、移行を再試行する前にこれらの要素を削除します。

#### サポートされないビジュアライゼーション

* [マップ](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

#### サポートされていないパネル

* [Analytics for Target（A4T）](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [メディア分平均オーディエンス](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [次または前の項目](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [ページの概要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

#### サポートされない機能

* [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [アラート](/help/components/c-alerts/intellligent-alerts.md)

### 組織としての移行プランの作成

特定のプロジェクトの移行に対してマッピングされるコンポーネントは、組織全体の今後のプロジェクトの移行に適用されるので、事前にすべてのプロジェクトの移行を計画しておくことが重要です。

ディメンションと指標のマッピング方法は、組織として決定する必要があります。 これにより、1 つのプロジェクトのみを考慮する場合に、個々の管理者がサイロで意思決定を行うのを防ぐことができます。

## Adobe AnalyticsプロジェクトのCustomer Journey Analyticsへの移行

>[!IMPORTANT]
>
>この節で説明するように、プロジェクトをCustomer Journey Analyticsに移行する前に、 [移行の計画](#plan-the-migration) 」の節を参照してください。
>
>マッピングしたディメンションまたは指標は、このプロジェクトに対しても、組織全体で移行される今後のすべてのプロジェクトに対しても、永続的です。 マッピングを行った後は、移行の完了後は変更できません。

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. の下 [!UICONTROL **データの設定と収集**]&#x200B;を選択します。 [!UICONTROL **コンポーネントの移行**].

1. 移行するプロジェクトを見つけます。 プロジェクトリストのフィルター、並べ替え、検索を行うことができます。

   デフォルトでは、自分と共有されているプロジェクトのみが表示されます。 組織内のすべてのプロジェクトを表示するには、 **フィルター** アイコン、展開 [!UICONTROL **その他のフィルター**] を選択し、 [!UICONTROL **すべて表示**]. ( プロジェクトリストのフィルタ、並べ替え、検索の詳細については、 [プロジェクトのリストのフィルター、並べ替え、検索](#filter-sort-and-search-the-list-of-projects).)

1. 移行するプロジェクトにマウスを移動して、 **移行** アイコン ![プロジェクトを移行](assets/migrate.svg).

   または

   移行するプロジェクトを選択し、「 」を選択します。 [!UICONTROL **移行先Customer Journey Analytics**].

   一度に 1 つのプロジェクトのみを選択して移行できます。

   The [!UICONTROL **project_name をCustomer Journey Analyticsに移行**] ダイアログボックスが表示されます。

   <!-- add screenshot -->

1. Adobe Analytics の [!UICONTROL **プロジェクト所有者**] 「 」フィールドに、「Customer Journey Analytics」でプロジェクトの所有者に設定するユーザーの名前を入力し、ドロップダウンメニューでユーザーの名前を選択します。

   指定した所有者には、プロジェクトに対する完全な管理権限があります.

1. Adobe Analytics の [!UICONTROL **レポートスイートのスキーマをマッピング**] セクションで、レポートスイートを選択します。

1. Adobe Analytics の [!UICONTROL **データビュー**] ドロップダウンメニューから、プロジェクトとコンポーネントをCustomer Journey Analyticsする移行データビューを選択します。

1. 選択 [!UICONTROL **マップスキーマ**].

1. Adobe Analytics の [!UICONTROL **マップスキーマ**] セクションで、 [!UICONTROL **Dimension**] および [!UICONTROL **指標**] セクション。

   Adobe Analyticsの一部のディメンションと指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングされます。 その他は、手動でマッピングする必要があります。

   **ディメンションと指標を自動的にマッピングする**

   Adobe Analyticsの一部のディメンションと指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングされます。 これらのディメンションおよび指標に対してマッピングの決定をおこなうことはできません。

   例えば、 **訪問回数** Adobe Analyticsの指標は、 **セッション** Customer Journey Analyticsの指標。

   任意のディメンションまたは指標を選択して、関連する ID を表示できます。

   <!-- update screenshot after I can see the Status column -->

   ![プロジェクト移行スキーマ](assets/project-migration-schema.png)

   **ディメンションと指標の手動マッピング**

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングできません。

   ディメンションや指標を自動的にマッピングできない場合は、 [!UICONTROL **Dimension**] または [!UICONTROL **指標**] セクションヘッダー。手動でマッピングする必要があるディメンションまたは指標の数を示します。 テーブルには、警告アイコンが表示されます。 ![警告アイコン](assets/schema-warning.png) 手動でマッピングする必要がある各ディメンションまたは指標の横にが表示されます。

   また、 [!UICONTROL **ステータス**] 列の表示 [!UICONTROL **マッピングされていません**].

   <!-- update screenshot after I can see the Status column -->

   ![移行スキーマの手動マップ](assets/schema-manual-map.png)

1. ディメンションと指標を手動でマッピングするには、警告アイコンを含むディメンションまたは指標を選択します ![警告アイコン](assets/schema-warning.png)を選択し、 [!UICONTROL **マッピングされたCustomer Journey Analytics指標**] フィールド ( または [!UICONTROL **マッピングされたCustomer Journey Analyticsディメンション**] 「 」フィールド（ディメンションをマッピングする場合）、選択したディメンションまたは指標にマッピングするCustomer Journey Analyticsのディメンションまたは指標を選択します。

   ![ディメンションと指標のマッピング](assets/schema-manual-map-drop-down.png)

   ディメンションまたは指標がマッピングされると、警告アイコンが消え、 [!UICONTROL **ステータス**] 列の変更 [!UICONTROL **マッピング済み**] 緑の点が付いています。 ( [!UICONTROL **マッピング済み**] 灰色の点は、以前の移行中にディメンションまたは指標がマッピングされたことを示します。以前のマッピングは更新できません。)

   警告アイコンが表示されているディメンションまたは指標ごとに、この手順を繰り返します。

   Adobe Analyticsレポートスイートのすべてのディメンションと指標がCustomer Journey Analyticsデータビューのディメンションまたは指標にマッピングされると、緑色のチェックマークが付きます ![チェックマーク](assets/report-suite-check.png) は、 [!UICONTROL **レポートスイートのスキーマをマッピング**] 」セクションに入力します。

1. （条件付き）移行するプロジェクトに複数のレポートスイートが含まれている場合、 [!UICONTROL **レポートスイートのスキーマをマッピング**] セクションで、手順 6 ～ 10 を繰り返します。 <!-- double-check that the step numbers are still correct -->

1. 選択 [!UICONTROL **移行**].

   >[!WARNING]
   >
   >   「 」を選択すると、画面に表示される警告メッセージが表示されます [!UICONTROL **移行**]. 続行する前に、このプロジェクトと、組織全体で移行される今後のすべてのプロジェクトの両方に対して、マッピングするディメンションや指標が永続的であることを理解しておきます。 続行すると、行ったマッピングは変更できません。

   移行が完了した後、 [!UICONTROL **移行ステータス**] ページには、移行された項目の概要が表示されます。

   移行に失敗した場合は、 [失敗した移行を再試行](#retry-a-failed-migration) 詳しくは、以下の節を参照してください。

## 失敗した移行を再試行

移行に失敗した場合は、移行を再試行できます。

失敗した移行は、次のいずれかの方法で再試行できます。

>[!NOTE]
>
>再試行後も移行が失敗し続ける場合は、プロジェクト ID をカスタマーケアにお問い合わせください。 プロジェクト ID は、移行ステータスページで確認できます。 <!-- when does this page display? How can they get there -->

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. の下 [!UICONTROL **データの設定と収集**]&#x200B;を選択します。 [!UICONTROL **コンポーネントの移行**].

1. 選択 [!UICONTROL **失敗**] （内） [!UICONTROL **移行ステータス**] 再試行するプロジェクトの横の列。

   ![移行ステータス列が失敗しました](assets/migration-failed.png)

   The [!UICONTROL **移行ステータス**] ページが表示されます。

   このページは、「 」セクションで説明した移行手順が完了するとすぐに表示されます。 [Adobe AnalyticsプロジェクトのCustomer Journey Analyticsへの移行](#migrate-adobe-analytics-projects-to-customer-journey-analytics) 上記の

1. 選択 [!UICONTROL **移行を再試行**].

## プロジェクトのリストのフィルター、並べ替え、検索

コンポーネントの移行ページで、プロジェクトのリストのフィルタリング、並べ替え、検索をおこなうことができます。

### プロジェクトのリストのフィルター

次の条件でフィルタリングできます。

| フィルター | 説明 |
|---------|----------|
| [!UICONTROL **ステータス**] | 移行のステータス： <ul><li>[!UICONTROL **未開始**]</li><li>[!UICONTROL **Started**]</li><li>[!UICONTROL **完了**]</li><li>[!UICONTROL **失敗**]</li></ul>。 |
| [!UICONTROL **タグ**] | タグのリストから任意のタグを選択します。 選択したタグが適用されたプロジェクトのみが表示されます。 |
| [!UICONTROL **レポートスイート**] | レポートスイートのリストから任意のレポートスイートを選択します。 選択したレポートスイートを使用するプロジェクトのみが表示されます。 |
| [!UICONTROL **所有者**] | 所有者のリストから任意の所有者を選択します。 選択したユーザーが所有するプロジェクトのみが表示されます。 |
| [!UICONTROL **その他のフィルター**] | 次の追加のフィルターを使用できます。 <ul><li>[!UICONTROL **自分が所有**]：所有者として設定されているプロジェクトのみを表示します。</li><li>[!UICONTROL **自分と共有済み**]：自分と共有されているプロジェクトのみを表示します。</li><li>[!UICONTROL **お気に入力**]：お気に入りとしてマークされたプロジェクトのみを表示します。 ( プロジェクトをお気に入りに登録するには、 [プロジェクトランディングページ](/help/analyze/landing.md).)</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **毎年**]</li></ul> |

{style="table-layout:auto"}

### プロジェクトのリストの並べ替え

任意の列でプロジェクトのリストを並べ替えることができます。

プロジェクトのリストを並べ替えるには、次の手順に従います。

1. 並べ替える列の列見出しを選択します。

1. （オプション）並べ替え順を逆にするには、同じ列ヘッダーを再度選択します。

### プロジェクトの検索

コンポーネントの移行ページでプロジェクトのリストを検索し、移行するプロジェクトを見つけることができます。

1. コンポーネントの移行ページ上部の検索フィールドに、移行するプロジェクトの名前を入力します。

1. プロジェクトがドロップダウンメニューに表示されたら、そのプロジェクトを選択します。

<!-- is there going to be a way to customize the columns that are displayed? -->
