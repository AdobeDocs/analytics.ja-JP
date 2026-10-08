---
title: Web SDK アップグレードアシスタントでの移行の管理
description: Web SDK アップグレードアシスタントでマイグレーションを作成、表示および開きます。
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
source-wordcount: '397'
ht-degree: 0%
---
# 移行の管理

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="移行"
>abstract="各移行は、1つのタグプロパティのAdobe Analytics実装をWeb SDKにアップグレードします。 移行を開いて中断した場所から続行するか、「新規」を選択して移行を開始します。"

**[!UICONTROL Migrations]** ページは、Web SDK アップグレードアシスタントの出発点です。 組織内の移行が、各移行の進捗状況、ステータス、作成者など一覧表示されます。 このページを使用して、移行を作成するか、既存の移行を開きます。

## 移行の作成 {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="新しい移行"
>abstract="移行するタグプロパティとそのプロパティ内のライブラリを選択します。 アップグレード アシスタントは、移行の作成時にライブラリのスナップショットを取得します。 移行スナップショット後にライブラリに加えられた変更は含まれません。 移行が完了するまで、タグプロパティは変更されません。"

<!-- markdownlint-enable MD034 -->

移行を作成する前に、[前提条件](overview.md#prerequisites)を満たしていることを確認してください。

1. **[!UICONTROL 移行]** ページで、**[!UICONTROL 新規]**&#x200B;を選択します。
1. 移行の名前と、オプションで説明を入力します。
1. 移行するタグプロパティを選択します。
1. タグライブラリを選択します。 移行を作成すると、アップグレード アシスタントは、このライブラリに存在する実装のスナップショットを取ります。 その後にライブラリに加えた変更は、移行に反映されません。
1. 「**[!UICONTROL 作成]**」を選択します。

新しい移行がリストに表示されます。 開いて[&#x200B; コンポーネントの選択](component-selection.md)を開始します。

## 移行を開く {#open}

移行の名前を選択して開きます。 移行の手順は、左側のナビゲーションに表示されます。 完了したステップに戻って、必要な頻度でレビューまたは変更することができますが、まだ到達していないステップは利用できません。

アップグレード アシスタントは、手順を進むときに進行状況を保存するので、移行を終了してから後で移行に戻すことができます。 [移行を確定するまで、設定した内容は何も有効になりません](final-review.md#finalize)。 最終化後、移行は読み取り専用になります。 開いて何が作成されたかを確認することはできますが、変更することはできません。

## その他の移行アクション {#actions}

移行の行を選択して、利用可能なアクションを表示します。

* **[!UICONTROL 続行]**：移行を開きます。
* **[!UICONTROL 実行を複製]**：移行のコピーを作成します。
* **[!UICONTROL 名前を変更]**：移行の名前と説明を変更します。
* **[!UICONTROL アーカイブ]**：移行のステータスを&#x200B;**[!UICONTROL アーカイブ]**&#x200B;に変更します。
* **[!UICONTROL 移行を削除]**：移行を完全に削除します。 この操作は元に戻すことができません。
