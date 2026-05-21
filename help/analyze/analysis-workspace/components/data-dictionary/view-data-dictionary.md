---
description: Analysis Workspace のデータ辞書を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ辞書の表示
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
TQID: https://experienceleague.adobe.com/N4hzk5uKr5Mh3FA6V1x8KqyCod6ZIK8TO7l2TZvzR4A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1137
ht-degree: 98%

---

# データ辞書でのコンポーネント情報の表示

データ辞書を使用すると、コンポーネントの説明、類似のコンポーネント、コンポーネントが頻繁に使用される他のコンポーネントなど、コンポーネントに関する情報を表示できます。

データ辞書でコンポーネントに関する情報を表示するには：

1. 表示するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「[!UICONTROL **データ辞書**]」アイコンを選択します （データディクショナリへのアクセス方法については、[ データディクショナリへのアクセス ](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary)で説明しています）。

   データ辞書ウィンドウが表示されます。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 表示するコンポーネントを含むレポートスイートがドロップダウンメニューで選択されます。 デフォルトでは、既に存在するレポートスイートが表示されます。

1. （オプション）検索フィールドに、表示するコンポーネントの名前の入力します。

   コンポーネントのタイプは、カラーとアイコンの両方で識別できます。 **ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。 Adobe アイコンは計算指標テンプレートまたはセグメントテンプレートのいずれか、電卓アイコン ![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は組織の Analytics 管理者によって作成された計算指標を示します。

1. （オプション）**フィルター**&#x200B;アイコン ![データ辞書のフィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択して、コンポーネントのリストをフィルタリングします。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | お気に入りのリストにあるコンポーネントのみを表示します。 お気に入りのリストにコンポーネントを追加する方法については、[コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)を参照してください。 |
   | [!UICONTROL **ディメンション**] | ディメンションであるコンポーネントのみを表示します （このオプションは、最初にデータ辞書にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **指標**] | 指標であるコンポーネントのみを表示します （このオプションは、最初にデータ辞書にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **セグメント**] | セグメントであるコンポーネントのみを表示します （このオプションは、最初にデータ辞書にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **日付範囲**] | 日付範囲であるコンポーネントのみを表示します （このオプションは、最初にデータ辞書にアクセスした際に「[!UICONTROL **クイックフィルター**]」タブでも使用できます）。 |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントの表示。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者が承認済みとしてまだマークしていないコンポーネントのみを表示します。 レビューと承認が必要なコンポーネントを管理者が識別する際に役立ちます。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **説明がありません**] | 「説明」フィールドにまだ説明がないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **重複の表示**] | <p>選択したレポートスイート内の別のコンポーネントと同じ名前や同じ定義があるコンポーネントのみを表示します。 重複として表示するには、名前または定義が完全に一致している必要があります。</p><p>このオプションは、管理者のみが使用できます。</p><p>**メモ：**&#x200B;定義には、ユーザー作成のコンポーネントとアドビ提供のコンポーネントが含まれます。 名前には、現在、ユーザー作成のコンポーネントのみが含まれ、アドビ提供のコンポーネントは含まれません。 アドビ提供のコンポーネントの重複した名前を表示する機能は、今後のリリースで追加される予定です。</p> |
   | [!UICONTROL **最近のデータがありません**] | 過去 90 日間にデータを収集していないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **作成者：Adobe**] <!-- I don't see this option--> | アドビが作成したコンポーネントのみを表示します。 組織内の管理者または別のユーザーが作成したコンポーネントは表示しません。 |

   {style="table-layout:auto"}

1. （オプション）「**並べ替え**」アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、表示するコンポーネントを選択します。

   コンポーネントに関する次の情報が表示されます。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | <p>コンポーネントが管理者にレビューおよび承認されたことを示します。</p><p>コンポーネントが承認されたら、管理者は「**承認済み**」ボタンを選択して承認を削除できます。</p> |
   | [!UICONTROL **承認が必要です**] | <p>コンポーネントがまだ管理者にレビューおよび承認されていないことを示します。</p><p>管理者には、「[!UICONTROL **承認**]」オプションが表示されます。 このオプションを選択すると、ユーザーに対してコンポーネントが「承認済み」としてマークされます。</p> |
   | [!UICONTROL **説明**] | コンポーネントの意図された機能について説明します （この情報は、[コンポーネントの説明の追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md)で説明しているように、Analytics 管理者が追加します）。 |
   | [!UICONTROL **次でよく使用される**] | <p>表示しているコンポーネントと最も一緒に使用されるコンポーネントを表示します。</p><p>指標、計算指標、ディメンション、セグメントおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>このリストは、過去 90 日間のデータに基づいています。 表示するアクセス権を持つコンポーネントのみを表示します。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。 ユーザーに表示されるコンポーネントをキュレートする前に、最初に&#x200B;**すべて表示**&#x200B;フィルターを適用して、共有されていないコンポーネントが表示されるようにします。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | [!UICONTROL **類似**] | <p>表示しているコンポーネントと同様の名前を持つコンポーネントを表示します。</p><p>指標、計算指標、ディメンション、セグメントおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>表示するアクセス権を持つコンポーネントのみを表示します。</p><p>レポートスイート内の重複するコンポーネントもすべてここに表示されます。 [データ辞書の正常性の監視](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)で説明しているように、Analytics 管理者はすべての重複するコンポーネントを特定して削除する必要があります。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。 ユーザーに表示されるコンポーネントをキュレートする前に、最初に&#x200B;**すべて表示**&#x200B;フィルターを適用して、共有されていないコンポーネントが表示されるようにします。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**メモ：**&#x200B;現在、「**類似**」セクションには、ユーザー作成のコンポーネントのみが含まれており、アドビ提供のコンポーネントは含まれていません。 アドビ提供のコンポーネントは、今後のリリースで追加される予定です。</p> |
   | [!UICONTROL **タグ**] | コンポーネントに適用されているすべてのタグを表示します。 管理者アクセス権を持つユーザーは、コンポーネントの編集時にタグを追加できます。 |
   | [!UICONTROL **コンポーネントの種類**] | ディメンション、指標、セグメント、または日付範囲のいずれかであるコンポーネントのタイプをリストします。 |
   | [!UICONTROL **作成者**] | コンポーネントを作成したユーザーの名前を表示します。 |
   | [!UICONTROL **プレビュー**] | Analysis Workspace でのコンポーネントの外観のプレビューを表示します。 |
   | [!UICONTROL **最終変更日**] | コンポーネントの最終変更日を表示します。 このセクションは、セグメント、計算指標および日付範囲を表示する際に表示されます。 |

   {style="table-layout:auto"}

1. （オプション）データ辞書から Analysis Workspace にコンポーネントをドラッグします。
