---
description: Adobe AnalyticsからCustomer Journey Analyticsにコンポーネントとプロジェクトを移行する方法について説明します。
title: Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: b8d47e8802198365b348f94efc3f71ff424e83d1
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 5%

---

# Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行

Adobe Analytics 管理者は、Adobe Analytics プロジェクトとその関連コンポーネントを Customer Journey Analytics に移行できます。

移行プロセスには、次が含まれます。

* Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。

* Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。

  ディメンションや指標には、自動的にマッピングされるものと、移行プロセスの一環として手動でマッピングする必要があるものがあります。 セグメントも移行されますが、移行プロセスの一環としてマッピングする必要はありません。

  移行が完了すると、移行されたすべてのコンポーネントが移行の概要に表示されます。

## 移行の準備

プロジェクトをCustomer Journey Analyticsに移行する前に、 [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備](/help/admin/admin/component-migration/prepare-component-migration.md).

## Adobe Analytics プロジェクトのCustomer Journey Analyticsへの移行

>[!IMPORTANT]
>
>この節の説明に従ってプロジェクトをCustomer Journey Analyticsに移行する前に、 [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**マッピングするディメンションや指標は、このプロジェクトと、IMS 組織全体で移行される今後のすべてのプロジェクトの両方で、移行を実行しているユーザーに関係なく、永続的です。 これらのマッピングは、カスタマーケアに連絡しない限り、変更または取り消しできません。**

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. 次の下 [!UICONTROL **データの設定と収集**]&#x200B;を選択 [!UICONTROL **コンポーネントの移行**].

1. 移行するプロジェクトを見つけます。 プロジェクトリストのフィルタリング、並べ替え、検索を行うことができます。

   デフォルトでは、自分と共有されているプロジェクトのみが表示されます。 組織内のすべてのプロジェクトを表示するには、 **フィルター** アイコン、展開 [!UICONTROL **その他のフィルター**] を選択して、 [!UICONTROL **すべてを表示**]. （プロジェクト リストのフィルタ、並べ替え、および検索の詳細については、を参照してください。 [プロジェクトのリストのフィルタリング、並べ替え、検索](#filter-sort-and-search-the-list-of-projects).）

1. 移行するプロジェクトの上にマウスポインターを置いてから、 **移行** アイコン ![プロジェクトを移行](assets/migrate.svg).

   または

   移行するプロジェクトを選択し、 [!UICONTROL **Customer Journey Analyticsに移行**].

   一度に選択できるプロジェクトは 1 つだけです。

   この [!UICONTROL **project_name をCustomer Journey Analyticsに移行**] ダイアログ・ボックスが表示されます。

   <!-- add screenshot -->

1. が含まれる [!UICONTROL **プロジェクト所有者**] フィールドに、Customer Journey Analyticsでプロジェクトのオーナーとして設定するユーザーの名前を入力し始め、ドロップダウンメニューでユーザーの名前を選択します。

   指定した所有者には、プロジェクトに対する完全な管理権限があります。

1. が含まれる [!UICONTROL **レポートスイートのスキーマのマッピング**] セクションで、レポートスイートを選択します。

1. が含まれる [!UICONTROL **データビュー**] ドロップダウンメニューで、プロジェクトとコンポーネントを移行するCustomer Journey Analyticsデータビューを選択します。

1. を選択 [!UICONTROL **スキーマをマッピング**].

1. が含まれる [!UICONTROL **スキーマをマッピング**] セクションで、 [!UICONTROL **Dimension**] および [!UICONTROL **指標**] セクション。

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsでディメンションまたは指標に自動的にマッピングされます。 その他は手動でマッピングする必要があります。

   **ディメンションと指標の自動的なマッピング**

   >[!NOTE]
   >
   >   WebSDK を使用してデータをAdobe Experience Platformに取り込んだ場合、ディメンションと指標は自動的にマッピングできません。 詳しくは、を参照してください [前提条件](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) 。対象： [Adobe AnalyticsからCustomer Journey Analyticsへのコンポーネントおよびプロジェクトの移行の準備](/help/admin/admin/component-migration/prepare-component-migration.md).

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsでディメンションまたは指標に自動的にマッピングされます。 これらのディメンションおよび指標には、マッピングに関する決定を行えません。

   例： **訪問回数** Adobe Analyticsの指標は、 **セッション** Customer Journey Analyticsの指標。

   任意のディメンションまたは指標を選択して、関連する ID を表示できます。

   <!-- update screenshot after I can see the Status column -->

   ![プロジェクト移行スキーマ](assets/project-migration-schema.png)

   **ディメンションと指標の手動マッピング**

   Adobe Analyticsの一部のディメンションおよび指標は、Customer Journey Analyticsのディメンションまたは指標に自動的にマッピングできません。

   ディメンションまたは指標を自動的にマッピングできない場合は、オレンジ色のカウンターがの横に表示されます [!UICONTROL **Dimension**] または [!UICONTROL **指標**] 手動でマッピングする必要があるディメンションまたは指標の数を示すセクションヘッダー。 テーブル内に、警告アイコン ![警告アイコン](assets/schema-warning.png) 手動でマッピングする必要がある各ディメンションまたは指標の横にが表示されます。

   さらに、 [!UICONTROL **ステータス**] 列のメッセージ [!UICONTROL **マッピングなし**].

   <!-- update screenshot after I can see the Status column -->

   ![移行スキーマの手動マップ](assets/schema-manual-map.png)

1. ディメンションと指標を手動でマッピングするには、警告アイコンが含まれるディメンションまたは指標を選択します ![警告アイコン](assets/schema-warning.png)を選択し、次に [!UICONTROL **マッピングされたCustomer Journey Analytics指標**] フィールド（または [!UICONTROL **マッピングされたCustomer Journey Analyticsディメンション**] フィールド （ディメンションをマッピングする場合）を選択したディメンションまたは指標にマッピングするCustomer Journey Analyticsのディメンションまたは指標を選択します。

   ![ディメンションと指標のマッピング](assets/schema-manual-map-drop-down.png)

   ディメンションまたは指標がマッピングされると、警告アイコンが表示されなくなり、 [!UICONTROL **ステータス**] 列の変更先 [!UICONTROL **マップ済み**] 緑のドット。 （ステータス [!UICONTROL **マップ済み**] グレーのドットは、以前の移行時にディメンションまたは指標がマッピングされたことを示します。以前のマッピングは更新できません。）

   警告アイコンを含む各ディメンションまたは指標に対して、このプロセスを繰り返します。

   Adobe Analytics レポートスイート内のすべてのディメンションと指標がCustomer Journey Analyticsデータビューのディメンションまたは指標にマッピングされると、緑色のチェックマークが付きます ![チェックマーク](assets/report-suite-check.png) は、レポートスイート名の横に表示されます。 [!UICONTROL **レポートスイートのスキーマのマッピング**] セクション。

1. （条件付き）移行中のプロジェクトに複数のレポートスイートが含まれている場合、 [!UICONTROL **レポートスイートのスキーマのマッピング**] セクションを開き、手順 6 ～ 10 を繰り返します。 <!-- double-check that the step numbers are still correct -->

1. を選択 [!UICONTROL **移行**].

   >[!WARNING]
   >
   >   を選択すると、画面上に警告メッセージが表示されます [!UICONTROL **移行**]. 続行する前に、マッピングしたディメンションや指標は、このプロジェクトと、組織全体を通じて移行される今後のプロジェクトの両方で永続的なものであることを理解してください。 続行した場合、作成したマッピングは変更できません。

   移行が完了したら、 [!UICONTROL **移行ステータス**] ページには、移行内容の概要が表示されます。

   移行に失敗した場合は、 [失敗した移行の再試行](#retry-a-failed-migration) 詳しくは、以下の節を参照してください。

## 失敗した移行の再試行

移行が失敗した場合は、移行を再試行できます。

失敗した移行を再試行する前に、必ず削除してください [サポートされていない要素](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors) をプロジェクトから削除します。

>[!NOTE]
>
>再試行後も移行が引き続き失敗する場合は、カスタマーケアにプロジェクト ID をお問い合わせください。 プロジェクト ID は、移行ステータス ページにあります。 <!-- when does this page display? How can they get there -->

失敗した移行を再試行するには：

1. Adobe Analytics で、「[!UICONTROL **管理者**]」タブを選択し、「[!UICONTROL **すべての管理者**]」を選択します。

1. 次の下 [!UICONTROL **データの設定と収集**]&#x200B;を選択 [!UICONTROL **コンポーネントの移行**].

1. を選択 [!UICONTROL **失敗**] が含まれる [!UICONTROL **移行ステータス**] 再試行するプロジェクトの横にある列。

   ![移行ステータス列が失敗しました](assets/migration-failed.png)

   この [!UICONTROL **移行ステータス**] ページが表示されます。

   このページは、セクションで説明した移行手順が完了した直後にも表示されます [Adobe Analytics プロジェクトのCustomer Journey Analyticsへの移行](#migrate-adobe-analytics-projects-to-customer-journey-analytics) 上。

1. を選択 [!UICONTROL **移行を再試行**].

## プロジェクトのリストのフィルタリング、並べ替え、検索

コンポーネント移行ページでプロジェクトのリストのフィルタリング、並べ替えおよび検索ができます。

### プロジェクトのリストのフィルタリング

次の条件でフィルタリングできます。

| フィルター | 説明 |
|---------|----------|
| [!UICONTROL **ステータス**] | 移行のステータス： <ul><li>[!UICONTROL **開始されていません**]</li><li>[!UICONTROL **開始日時**]</li><li>[!UICONTROL **Completed**]</li><li>[!UICONTROL **失敗**]</li></ul>。 |
| [!UICONTROL **タグ**] | タグのリストで任意のタグを選択します。 選択したタグが適用されているプロジェクトのみが表示されます。 |
| [!UICONTROL **レポートスイート**] | レポートスイートのリストで任意のレポートスイートを選択します。 選択したレポートスイートを使用するプロジェクトのみが表示されます。 |
| [!UICONTROL **所有者**] | 所有者のリストで任意の所有者を選択します。 選択したユーザーが所有するプロジェクトのみが表示されます。 |
| [!UICONTROL **その他のフィルター**] | 次の追加フィルターを使用できます。 <ul><li>[!UICONTROL **鉱山**]：所有者として設定したプロジェクトのみを表示します。</li><li>[!UICONTROL **自分と共有**]：自分と共有されているプロジェクトのみを表示します。</li><li>[!UICONTROL **お気に入り**]：お気に入りとしてマークされたプロジェクトのみを表示します。 （プロジェクトをお気に入りとしてマークするには、 [プロジェクトのランディングページ](/help/analyze/landing.md).）</li><li>[!UICONTROL **毎月**]</li><li>[!UICONTROL **毎年**]</li></ul> |

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
