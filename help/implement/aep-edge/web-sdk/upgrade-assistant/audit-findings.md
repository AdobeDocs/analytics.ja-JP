---
title: Web SDK アップグレードアシスタントでの監査結果
description: Web SDKに移行する前に、タグコンポーネントに関するオプションのクリーンアップの推奨事項を確認し、解決します。
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
source-wordcount: '335'
ht-degree: 2%
---
# 調査結果の監査

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="調査結果の監査"
>abstract="結果は、移行前にクリーンアップする可能性のあるルールやデータ要素（参照されないデータ要素など）を示します。 移行で推奨される変更を含める結果を受け入れるか、コンポーネントをそのまま残すように拒否します。 この手順はオプションです。"

<!-- markdownlint-enable MD034 -->

アップグレードアシスタントは、[&#x200B; コンポーネント選択](component-selection.md)で選択したルールとデータ要素を確認し、移行する前にクリーンアップする可能性のあるものをフラグ付けします。

* イベントや条件を共有するルールを複製して統合できます
* データの正確性に影響を与える可能性のあるルールアクションシーケンス
* 重複したデータ要素を作成し
* データ要素を使用しない可能性があります。無効にすることもできます

この手順はオプションです。 必要な数の調査結果を解決するか、直接[&#x200B; マッパーの準備](mapper-prep.md)に進むことができます。

## 結果の確認 {#review}

以下を含む詳細を表示する検索条件を選択します。

* 調査結果の説明
* コンポーネントの現在の設定
* コンポーネントが使用される場所（タグプロパティとAdobe Analyticsの両方）

各検索には、検索の種類に応じて推奨されるアクションが含まれます。 例えば、何も参照しないデータ要素に対する推奨アクションは、それを無効にすることです。

>[!IMPORTANT]
>
>未使用としてフラグ付けされたデータ要素は、動的に参照したり、タグの外部から参照したりできます。 検出を受け入れる前に、提案された変更、カスタムコード、アクションの順序、参照を確認して、目的の動作を維持していることを確認します。

## 調査結果を解決 {#resolve}

検索の推奨アクションを実行すると、その検索は受け入れられます。 アップグレード アシスタントは、移行に変更を追加し、[移行を完了](final-review.md#finalize)するときに適用します。 変更を加えたくない場合は、代わりに検索を辞退します。

気が変わった場合は、承認済み検索または拒否された検索を再度開くことができます。 複数の結果を一度に更新するには、リストでそれらを選択します。
