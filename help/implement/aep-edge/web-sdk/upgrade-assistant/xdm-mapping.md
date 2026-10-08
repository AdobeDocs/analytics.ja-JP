---
title: Web SDK アップグレードアシスタントでのXDM マッピング
description: Web SDKへの移行の一環として、Adobe Analytics変数をXDM スキーマのフィールドにマッピングします。
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%
---
# XDM マッピング

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="XDM マッピング"
>abstract="選択したAnalytics変数をXDM スキーマのフィールドにマッピングします。 アップグレードアシスタントは、AIが提案したマッピングを使用して新しいスキーマを作成したり、既存のスキーマに変数をマッピングしたりできます。 続行する前に、すべてのマッピングを確認してください。"

<!-- markdownlint-enable MD034 -->

Web SDKは[Experience Data Model （XDM） ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home) フィールドを使用してデータを送信するので、[Mapper preparation](mapper-prep.md)から先に進む各Analytics変数には、XDM スキーマの一致するフィールドが必要です。 この手順では、スキーマを選択し、変数をそのフィールドにマッピングします。

## スキーマの選択 {#schema}

マッピングは、次の2つの方法のいずれかで構築できます。

* **新しいスキーマを作成**: アップグレードアシスタントがAnalytics変数を分析し、それぞれのXDM フィールドを提案し、それらの提案からスキーマを生成してレビューします。
* **既存のスキーマを使用**: Experience Platformに既に存在するスキーマを選択し、各変数を自分でフィールドにマッピングします。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="フィールドグループ参照"
>abstract="アップグレードアシスタントがスキーマを構築する際に好むフィールドグループのタイプを選択します。 標準フィールドグループは、Adobeで定義します。 カスタムフィールドグループは、組織で定義します。"

<!-- markdownlint-enable MD034 -->

新しいスキーマを作成する場合、アップグレードアシスタントで標準フィールドグループとカスタムフィールドグループのどちらを使用するかを選択することもできます。 標準フィールドグループはAdobeで定義され、カスタムフィールドグループは組織で定義されます。 XDM ドキュメントの[ フィールドグループ ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group)を参照してください。

## マッピングの確認 {#review}

マッピングでは、各Analytics変数とそのマッピング先のXDM フィールドが一覧表示され、その横に完全なスキーマのプレビューが表示されます。 スキーマの一部を選択して、スキーマにマッピングする変数にリストをフィルタリングします。 個々のマッピングとスキーマ自体の両方を調整できます。

アップグレードアシスタントはAIを活用してマッピングを提案しますが、その結果は正確でなかったり完全でなかったりします。 続行する前に、すべてのマッピングを確認してください。 アップグレード アシスタントは、[移行を完了するまでExperience Platformでスキーマを作成しません](final-review.md#finalize)。

完了したら、**[!UICONTROL 保存して続行]**&#x200B;を選択してマッピングを保存し、[Web SDKの実装](web-sdk-implementation.md)に移動します。 保存後にマッピングを変更するには、**[!UICONTROL 編集]**&#x200B;を選択して変更し、次に&#x200B;**[!UICONTROL 保存して続行]**&#x200B;を選択します。 この方法で保存しない変更は、移行の最終化時には含まれません。
