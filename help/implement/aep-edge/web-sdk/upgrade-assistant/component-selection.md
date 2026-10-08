---
title: Web SDK アップグレードアシスタントでのコンポーネントの選択
description: Web SDKの移行に含めるタグルール、データ要素、拡張機能を選択します。
feature: Implementation Basics
role: Admin, Developer, Leader
badge: ベータ版
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%
---
# コンポーネントの選択

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="コンポーネントの選択"
>abstract="この移行に含めるルール、データ要素、拡張機能を選択します。 Adobe Analyticsの実装に積極的に貢献するコンポーネントは、デフォルトで選択されます。 以降の手順は、ここで選択したコンポーネントでのみ機能します。"

コンポーネントの選択は、移行の最初の手順です。 これを使用して、移行に含めるルール、データ要素、および拡張機能をタグプロパティから選択します。

アップグレードアシスタントは、タグプロパティのコンポーネントを&#x200B;**[!UICONTROL ルール]**、**[!UICONTROL データ要素]**、**[!UICONTROL 拡張機能]**&#x200B;のタブに整理します。 各タブには、[移行を作成したときにアップグレードアシスタントが取ったライブラリのスナップショットに基づいて、そのタイプのプロパティのすべてのコンポーネントが一覧表示されます](manager.md#create)。 デフォルトでは、Adobe Analyticsの実装に積極的に関与するコンポーネントのみが選択されます。 任意のコンポーネントを選択またはクリアできます。

**[!UICONTROL Published]**&#x200B;列には、各コンポーネントが選択したライブラリの一部であるかどうかが表示されます。 ライブラリに含まれていないコンポーネントは、タグプロパティ内に存在しますが、そのライブラリ内には存在しません。 この条件でリストを絞り込むには、**[!UICONTROL Source]** フィルターを使用します。

Adobe Target、Adobe Audience Manager、サードパーティの拡張機能など、Adobe Analyticsに関連しないコンポーネントを含めることができますが、アップグレードアシスタントはWeb SDKに変換しません。

選択したコンポーネントによって、後の手順で使用する手順が決まります。 例えば、何も参照しないデータ要素を含めることができるため、[監査結果](audit-findings.md)がクリーンアップのためにフラグを立てることができます。

## コンポーネントの詳細を表示 {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="タグの使用"
>abstract="このコンポーネントを使用するルール、データ要素、拡張機能。 拡張機能の使用では、拡張機能の設定設定のみを対象としています。 ルール内の使用状況は、「ルールの使用状況」に表示されます。"

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Analyticsの利用状況"
>abstract="このコンポーネントが割り当てられているAdobe Analytics変数を、変数タイプ別にグループ化します。"

<!-- markdownlint-enable MD034 -->

コンポーネントの名前を選択して、その設定と使用場所を示すパネルを開きます。

* **[!UICONTROL タグの使用状況]**: コンポーネントを使用するルール、データ要素、拡張機能。 **[!UICONTROL 拡張機能の使用状況]**&#x200B;では、拡張機能の構成設定のみを対象としています。 ルール内の使用状況は、**[!UICONTROL ルール使用状況]**&#x200B;の下に表示されます。
* **[!UICONTROL Analyticsの使用状況]**: コンポーネントが割り当てられているAdobe Analytics変数を、変数タイプ別にグループ化します。

タグ UIでコンポーネントを表示するには、パネルの上部にある名前を選択します。

完了したら、**[!UICONTROL 保存して続行]**&#x200B;を選択し、[調査結果の監査](audit-findings.md)に移動します。