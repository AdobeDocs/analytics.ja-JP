---
description: Adobe AnalyticsからCustomer Journey Analyticsにコンポーネントとプロジェクトを移行する方法について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: ec4475cdd8f0c3e89f528bd60155caa1ca3f0645
workflow-type: tm+mt
source-wordcount: '1641'
ht-degree: 4%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行

Adobe Analytics 管理者は、Adobe Analytics プロジェクトとその関連コンポーネントを Customer Journey Analytics に移行できます。

移行プロセスには、次が含まれます。

* Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。

* Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。

  ディメンションや指標には、自動的にマッピングされるものと、移行プロセスの一環として手動でマッピングする必要があるものがあります。 セグメントも移行されますが、移行プロセスの一環としてマッピングする必要はありません。

  移行が完了すると、移行されたすべてのコンポーネントが移行の概要に表示されます。

>[!NOTE]
>
>このページの情報では、ユーザーインターフェイスでプロジェクトとその関連コンポーネントを移行する方法について説明します。
>
>または、API を使用して移行を実行することもできます。 詳しくは、[Adobe Analytics API](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs) を参照してください。 すべての API 定義は、「**[!UICONTROL 定義を選択]**」ドロップダウンメニューで使用できます。


## 移行の準備

プロジェクトをAdobe Analyticsに移行する前に、プロジェクトの移行について詳しくは、[Customer Journey AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備 ](/help/admin/tools/component-migration/prepare-component-migration.md) を参照してください。

さらに、Analytics 管理者が使用できるツールを使用して [0&rbrace;Adobe Analytics インベントリを実行します。](/help/admin/tools/analytics-inventory.md)

## Adobe Analytics プロジェクトのCustomer Journey Analyticsへの移行

>[!NOTE]
>
>この節で説明しているように、Customer Journey Analyticsにプロジェクトを移行する前に、プロジェクトの移行について詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントやプロジェクトの移行の準備 ](/help/admin/tools/component-migration/prepare-component-migration.md) を参照してください。
>
>**マッピングしたディメンションまたは指標は、移行を実行しているユーザーに関係なく、このプロジェクトおよび IMS 組織全体の今後のすべてのプロジェクトに適用されます。 これらのマッピングは、今後のプロジェクトの移行時に更新できます。**

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. [!UICONTROL **データ設定と収集**] の下で [!UICONTROL **コンポーネントの移行**] を選択します。

1. 移行する各プロジェクトを見つけます。 プロジェクトリストのフィルタリング、並べ替え、検索を行うことができます。

   デフォルトでは、自分と共有されているプロジェクトのみが表示されます。 組織内のすべてのプロジェクトを表示するには、「**フィルター**」アイコンを選択し、「[!UICONTROL **その他のフィルター**]」を展開して、「[!UICONTROL **すべて表示**]」を選択します。 （プロジェクトリストのフィルタリング、並べ替え、検索について詳しくは、「[ プロジェクトのリストのフィルタリング、並べ替え、検索 ](#filter-sort-and-search-the-list-of-projects)」を参照してください。

1. （条件付き）複数のプロジェクトを一度に移行するには、移行する各プロジェクトの左側にあるチェックボックスをオンにし、「[!UICONTROL **Customer Journey Analyticsに移行**]」を選択します。

   複数のプロジェクトを移行する際は、次の点を考慮してください。

   * 一度に移行するプロジェクトを最大 20 個選択できます。

   * 移行ステータスは、移行中のすべてのプロジェクトで同じである必要があります。

     例えば、移行ステータスが **[!UICONTROL 開始されていません]** の移行するプロジェクトを 1 つ選択した場合、移行ステータスが **[!UICONTROL 失敗]** の別のプロジェクトを選択することはできません。

   * 移行中のすべてのプロジェクトに同じプロジェクト所有者を指定する必要があります。

   * ディメンションと指標は、移行中のすべてのプロジェクトで同じデータビューにマッピングする必要があります。

   [!UICONTROL **project_name をCustomer Journey Analyticsに移行**] ダイアログボックスが表示されます。

   <!-- add screenshot -->

1. （条件付き） 1 つのプロジェクトを移行するには、移行するプロジェクトの上にマウスポインターを置き、**移行** アイコン ![ プロジェクトを移行 ](assets/migrate.svg) を選択します。

   [!UICONTROL **project_name をCustomer Journey Analyticsに移行**] ダイアログボックスが表示されます。

   <!-- add screenshot -->

1. 「[!UICONTROL **プロジェクト所有者**]」フィールドに、Customer Journey Analyticsで移行されるプロジェクトの所有者として設定するユーザーの名前を入力し始め、ドロップダウンメニューでユーザーの名前を選択します。

   指定した所有者には、移行されたプロジェクトに対する完全な管理権限があります。 所有者は、Customer Journey Analyticsの管理者である必要があります。 後の手順でプロジェクトの所有権を変更できます。

1. 「[!UICONTROL **レポートスイートのスキーマのマッピング**]」セクションで、レポートスイートを選択します。

1. [!UICONTROL **データビュー**] ドロップダウンメニューで、プロジェクトとコンポーネントを移行するCustomer Journey Analytics データビューを選択します。

   複数のプロジェクトを移行する場合、移行中のすべてのプロジェクトは、単一のデータビューマッピングに結合されます。

1. [!UICONTROL **スキーマをマッピング**] を選択します。

1. 「[!UICONTROL **スキーマをマッピング**]」セクションで、「[!UICONTROL **ディメンション**]」および「[!UICONTROL **指標**]」セクションを展開します。

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングされます。 その他は手動でマッピングする必要があります。

   **ディメンションと指標の自動的なマッピング**

   >[!NOTE]
   >
   >   WebSDK を使用してデータをAdobe Experience Platformに取り込んだ場合、ディメンションと指標は自動的にマッピングできません。 詳しくは、[Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備 ](/help/admin/tools/component-migration/prepare-component-migration.md#prerequisites) の [ 前提条件 ](/help/admin/tools/component-migration/prepare-component-migration.md) を参照してください。

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングされます。 これらのディメンションおよび指標には、マッピングに関する決定を行えません。

   例えば、Adobe Analyticsの **訪問回数** 指標は、Customer Journey Analyticsの **セッション数** 指標と自動的にマッピングされます。

   任意のディメンションまたは指標を選択して、関連する ID を表示できます。

   <!-- update screenshot after I can see the Status column -->

   ![ プロジェクト移行スキーマ ](assets/project-migration-schema.png)

   **ディメンションと指標の手動マッピング**

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングできません。

   ディメンションまたは指標を自動的にマッピングできない場合は、[!UICONTROL **ディメンション**] または [!UICONTROL **指標**] セクションヘッダーの横にオレンジ色のカウンターが表示され、手動でマッピングする必要があるディメンションまたは指標の数が示されます。 テーブルで、手動でマッピングする必要がある各ディメンションまたは指標の横に警告アイコン ![ 警告アイコン ](assets/schema-warning.png) 警告アイコン）が表示されます。

   また、「[!UICONTROL **ステータス**]」列には [!UICONTROL **マッピングされていません**] と表示されます。

   <!-- update screenshot after I can see the Status column -->

   ![ 移行スキーマの手動マップ ](assets/schema-manual-map.png)

1. ディメンションと指標を手動でマッピングするには、警告アイコン ![warning icon](assets/schema-warning.png) を含むディメンションまたは指標を選択し、「[!UICONTROL **マッピングされたCustomer Journey Analytics指標**]」フィールド（またはディメンションをマッピングしている場合は「[!UICONTROL **マッピングされたCustomer Journey Analyticsディメンション**]」フィールド）で、選択したディメンションまたは指標にマッピングするCustomer Journey Analyticsのディメンションまたは指標を選択します。

   ![ ディメンションと指標のマッピング ](assets/schema-manual-map-drop-down.png)

   ディメンションまたは指標がマッピングされると、警告アイコンが消え、[!UICONTROL **ステータス**] 列が緑のドットで [!UICONTROL **マッピング済み**] に変わります。 （グレーのドットの付いた [!UICONTROL **マッピング済**] ステータスは、ディメンションまたは指標が以前の移行中にマッピングされたことを示します。以前のマッピングは更新できません。）

   警告アイコンを含む各ディメンションまたは指標に対して、このプロセスを繰り返します。

   Adobe Analytics レポートスイート内のすべてのディメンションと指標がCustomer Journey Analytics レポートスイート内のディメンションまたは指標にマッピングされると、「![ レポートスイートのスキーマをマッピング ](assets/report-suite-check.png)」セクションで、レポートスイート名の横に緑色のチェックマーク [!UICONTROL **チェックマーク**] が表示されます。

1. （条件付き）移行中のプロジェクトに複数のレポートスイートが含まれている場合、「レポートスイートのスキーマのマッピング [!UICONTROL **セクションで別のレポートスイートを選択してから、手順 6**] ら手順 10 を繰り返します。<!-- double-check that the step numbers are still correct -->

1. 「[!UICONTROL **移行**]」を選択します。

   >[!WARNING]
   >
   >「[!UICONTROL **移行**]」を選択すると、画面に警告メッセージが表示されます。 続行する前に、マッピングしたディメンションまたは指標は、移行を実行しているユーザーに関係なく、このプロジェクトおよび IMS 組織全体の今後のすべてのプロジェクトに適用されることを理解してください。 これらのマッピングは、今後のプロジェクトの移行時に更新できます。

   移行が完了すると、[!UICONTROL **移行ステータス**] ページに移行内容の概要が表示されます。

   移行が失敗した場合、詳しくは、以下の [ 失敗した移行の再試行 ](#retry-a-failed-migration) の節を参照してください。

1. （任意）プロジェクトが移行されたら、そのプロジェクトの所有権をCustomer Journey Analytics内の任意のユーザーに譲渡できます。 詳しくは、『Customer Journey Analytics ガイド』の [ アセットの転送 ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) を参照してください。

## 失敗した移行の再試行

移行が失敗した場合は、移行を再試行できます。

失敗した移行を再試行する前に、[ サポートされていない要素 ](/help/admin/tools/component-migration/prepare-component-migration.md#understand-unsupported-elements-that-cause-errors) をプロジェクトから削除してください。

>[!NOTE]
>
>再試行後も移行が引き続き失敗する場合は、カスタマーケアにプロジェクト ID をお問い合わせください。 プロジェクト ID は、移行ステータス ページにあります。<!-- when does this page display? How can they get there -->

失敗した移行を再試行するには：

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. [!UICONTROL **データ設定と収集**] の下で [!UICONTROL **コンポーネントの移行**] を選択します。

1. 再試行するプロジェクトの横にある [!UICONTROL **移行ステータス**] 列の「[!UICONTROL **失敗**]」を選択します。

   ![ 移行ステータス列が失敗しました ](assets/migration-failed.png)

   [!UICONTROL **移行ステータス**] ページが表示されます。

   このページは、前述の [Adobe Analytics プロジェクトのCustomer Journey Analyticsへの移行 ](#migrate-adobe-analytics-projects-to-customer-journey-analytics) の節で説明した移行手順を完了した直後にも表示されます。

1. 「[!UICONTROL **移行を再試行**]」を選択します。

## プロジェクトのリストのフィルタリング、並べ替え、検索

コンポーネント移行ページでプロジェクトのリストのフィルタリング、並べ替えおよび検索ができます。

### プロジェクトのリストのフィルタリング

次の条件でフィルタリングできます。

| フィルター | 説明 |
|---------|----------|
| [!UICONTROL **ステータス**] | 移行のステータス： <ul><li>[!UICONTROL **開始されていません**]</li><li>[!UICONTROL **開始**]</li><li>[!UICONTROL **Completed**]</li><li>[!UICONTROL **失敗**]</li></ul>. |
| [!UICONTROL **タグ**] | タグのリストで任意のタグを選択します。 選択したタグが適用されているプロジェクトのみが表示されます。 |
| [!UICONTROL **レポートスイート**] | レポートスイートのリストで任意のレポートスイートを選択します。 選択したレポートスイートを使用するプロジェクトのみが表示されます。 |
| [!UICONTROL **所有者**] | 所有者のリストで任意の所有者を選択します。 選択したユーザーが所有するプロジェクトのみが表示されます。 |
| [!UICONTROL **その他のフィルター**] | 次の追加フィルターを使用できます。 <ul><li>[!UICONTROL **自分**]：自分が所有者として設定されているプロジェクトのみを表示します。</li><li>[!UICONTROL **自分と共有**]：自分と共有されているプロジェクトのみを表示します。</li><li>[!UICONTROL **お気に入り**]：お気に入りとしてマークされたプロジェクトのみを表示します。 （プロジェクトをお気に入りとしてマークするには、[ プロジェクトランディングページ ](/help/analyze/landing.md) を使用します）。</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **毎年**]</li></ul> |

{style="table-layout:auto"}

### プロジェクトのリストの並べ替え

プロジェクトのリストは、任意の列で並べ替えることができます。

プロジェクトのリストを並べ替えるには：

1. 並べ替えの基準にする列の列見出しを選択します。

1. （オプション）同じ列ヘッダーを再度選択して、並べ替え順を逆にします。

### プロジェクトの検索

コンポーネントの移行ページでプロジェクトのリストを検索し、移行するプロジェクトを見つけることができます。

1. コンポーネント移行ページの上部にある検索フィールドで、移行するプロジェクトの名前の入力を開始します。

1. ドロップダウンメニューに表示されたら、プロジェクトを選択します。

<!-- is there going to be a way to customize the columns that are displayed? -->
