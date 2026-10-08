---
title: Web SDK アップグレードアシスタントでのWeb SDKの実装
description: アップグレードアシスタントが既存のタグルールに追加するWeb SDK アクションを確認します。
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
source-wordcount: '311'
ht-degree: 0%
---
# Web SDKの導入

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Web SDKの導入"
>abstract="アップグレードアシスタントがルールに追加するWeb SDK アクションを確認します。 Adobe Analyticsでのアクションも引き続きおこなわれます。 コンポーネントを選択して、現在の設定とWeb SDKの設定を並べて比較します。 キューに入れたコンポーネントのみが移行に追加されます。"

<!-- markdownlint-enable MD034 -->

選択したコンポーネントと[XDM マッピング &#x200B;](xdm-mapping.md)を使用して、アップグレードアシスタントは各Adobe Analytics アクションの直後にWeb SDK アクションをルールに追加します。 Analyticsのアクションは維持されるため、これらのルールはAdobe AnalyticsとWeb SDKの両方にデータを送信します。 ほとんどのデータ要素は変更されずに転送され、ルールは引き続き名前で参照されます。

**[!UICONTROL 種類を変更]**&#x200B;列には、移行の最終処理が各コンポーネントに対して行う処理が表示されます。

* **[!UICONTROL Web SDKのアクションが追加されました]**: アップグレードアシスタントは、Web SDKのアクションをルールに追加します。
* **[!UICONTROL 変更なし]**: コンポーネントの転送は変更されません。
* **[!UICONTROL ブロック済み]**: アップグレード アシスタントがWeb SDK アクションをコンポーネントに追加する前に、コンポーネントにレビューが必要です。 コンポーネントを選択して、何がブロックしているかを確認します。

コンポーネントを選択して、現在のコンフィギュレーションとWeb SDK コンフィギュレーションを並べて比較します。 さらにコンテキストが必要な場合は、アップグレードアシスタントがタグ UIのコンポーネントにリンクします。

キューに入れるコンポーネントが移行に追加されます。 コンポーネントをキューに追加するには、リストでコンポーネントを選択するか、詳細で&#x200B;**[!UICONTROL キュー]**&#x200B;を選択します。 取り消すには、**[!UICONTROL キューから削除]**&#x200B;を選択します。 アップグレード アシスタントは、[移行の最終版](final-review.md#finalize)になるまで、タグのプロパティを変更しません。

アップグレードアシスタントは、AIを使用してWeb SDKのアクションを生成しますが、結果が正確でない場合や、完全でない場合があります。 アクションを生成しても、サイトでの動作が検証されないので、ライブラリを公開する前にテストします。
