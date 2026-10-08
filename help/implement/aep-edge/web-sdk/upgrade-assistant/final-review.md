---
title: Web SDK アップグレードアシスタントでの最終審査
description: Web SDKの移行を確認して最終決定し、その結果のタグライブラリを実稼動環境に公開します。
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
source-wordcount: '469'
ht-degree: 0%
---
# 最終審査

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="最終審査"
>abstract="使用するExperience Platform サンドボックスを選択し、この移行によって作成または変更されるすべての要素を確認します。 移行が完了するまで、何も変更されません。 最終処理を行うと、アップグレードアシスタントは一度にすべてを作成し、タグの変更を新しいライブラリに追加し、この移行を読み取り専用にします。 そのライブラリを自分で本番環境に公開します。"

<!-- markdownlint-enable MD034 -->

最終レビューは、移行の最後のステップです。 Experience Platformとタグプロパティで、マイグレーションによって作成または変更されたすべてのものが表示されます。

## 移行によって作成される内容を確認する {#review}

まず、移行がリソースを作成するExperience Platform サンドボックスを選択します。 サンドボックスを選択するまで、移行を確定することはできません。

次に、アップグレードアシスタントに、移行の最終処理によって作成または変更されるすべての項目が一覧表示されます。

* **[!UICONTROL XDM]**: XDM マッピングにちなんで名付けられた新しいスキーマと、それが必要とするカスタムフィールドグループ。 標準フィールドグループは既に存在するため、スキーマはそのまま使用します。 このセクションは、[XDM マッピング ](xdm-mapping.md#schema)で新しいスキーマを作成することを選択した場合にのみ表示されます。
* **[!UICONTROL データセット]**：開発用と実稼動用の2つのデータセット。 各の名前は、`My migration - Development`などの移行にちなんで付けられます。
* **[!UICONTROL データストリーム]**: データセットと同じ名前の2つのデータストリーム（開発用と実稼動用の1つ）。
* **[!UICONTROL Adobe タグ]**：移行後にという名前の新しいライブラリ（`Library - "My migration"`など）。 ライブラリには、マイグレーションが変更するルールとデータ要素、およびWeb SDK アクションに必要な拡張機能の設定が含まれています。

## 移行の最終版 {#finalize}

移行が完了するまで、アップグレードアシスタントはタグプロパティを変更したり、Experience Platformで何かを作成したりしません。

>[!IMPORTANT]
>
>移行を確定すると、その移行は読み取り専用になります。 **[!UICONTROL 移行]** ページから引き続きページを開いて、作成した内容を確認することはできますが、変更したり、もう一度確定したりすることはできません。 新しいライブラリはまだ開発中なので、ライブラリを公開する前に、タグ UIでタグの変更を編集または削除できます。

1. 「**[!UICONTROL アーティファクトを作成]**」を選択します。
1. **[!UICONTROL これらの推奨事項を確認]** ダイアログで、**[!UICONTROL 続行]**&#x200B;を選択します。
1. **[!UICONTROL この移行を最終化しますか？]** ダイアログが表示されたら、**[!UICONTROL 最終版]**&#x200B;を選択します。

アップグレードアシスタントは、すべてを一度に作成し、その進行状況を示します。 タグの変更は新しいライブラリに追加されますが、ライブラリは公開されません。

## 変更を公開する {#publish}

移行を完了したら、タグ公開フローを使用して新しいライブラリを移動します。

1. 開発環境でライブラリを構築してテストし、Web SDKの実装が期待するデータを送信することを確認します。
1. ライブラリを承認用に送信し、ステージング環境でテストします。
1. ライブラリを承認し、実稼動環境に公開します。

タグユーザーガイドの[公開フロー](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow)を参照してください。
