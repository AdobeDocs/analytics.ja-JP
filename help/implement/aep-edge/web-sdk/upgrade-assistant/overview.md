---
title: Web SDK アップグレードアシスタント
description: Adobe Analytics タグ拡張機能のAdobe Experience Platform Web SDKへの移行を計画して実行します。
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
source-wordcount: '535'
ht-degree: 3%
---
# Web SDK アップグレードアシスタント

Web SDK アップグレードアシスタントは、Adobe Analytics tags拡張機能のAdobe Experience Platform Web SDKへの移行を計画および実行するのに役立ちます。 移行を単一のガイド付きワークスペースに集約することで、既存のタグ実装からWeb SDKに、構造化された追跡可能な方法で移行できます。

## アップグレードアシスタントの仕組み {#how-it-works}

各マイグレーションは、1つのタグプロパティでAdobe Analytics実装で動作します。 アップグレードアシスタントは、Adobe Analyticsのアクションを削除せずにWeb SDKのアクションを既存のルールに追加するため、実装は引き続きWeb SDKと一緒にAdobe Analyticsにデータを送信します。

アップグレードアシスタントは、Adobe Analytics コンポーネントのみを変換します。 Adobe Target、Adobe Audience Manager、サードパーティの拡張機能など、他の拡張機能のコンポーネントを含めることができますが、アップグレードアシスタントはWeb SDKに変換しません。

アップグレードアシスタントは次の手順をガイドし、各ステップは前の手順で行った決定に基づいて構築されます。

1. **[コンポーネントの選択](component-selection.md)**：移行に含めるルール、データ要素、拡張機能を選択します。
1. **[監査結果](audit-findings.md)**：選択したコンポーネントに対するオプションのクリーンアップの推奨事項を確認します。
1. **[レポートスイートの検証](rs-verification.md)**: レポートスイート内のAnalytics変数を確認し、今後使用する変数を選択します。
1. **[XDM マッピング](xdm-mapping.md)**:Analytics変数をXDM スキーマのフィールドにマッピングします。
1. **[Web SDKの実装](web-sdk-implementation.md)**: アップグレードアシスタントがルールに追加するWeb SDKのアクションを確認します。
1. **[最終レビュー](final-review.md)**: Experience Platform サンドボックスを選択し、移行によって作成される内容を確認して、移行を確定します。

各ステップは移行の一部を設定し、完了したステップに戻って必要な頻度で確認または変更できます。 アップグレード アシスタントは、移行が完了するまで、タグのプロパティを変更したり、Experience Platformで何かを作成したりすることはありません。 最終処理を行うと、アップグレードアシスタントが一度にすべてを作成し、タグの変更を新しいライブラリに追加します。 その後、そのライブラリをテストし、タグ公開フローを使用して実稼動環境に公開します。

>[!IMPORTANT]
>
>アップグレードアシスタントは、AI （人工知能）を使用して、XDM フィールドマッピングやWeb SDK ルール設定などのレコメンデーションを生成します。 これらの推奨事項は、正確または完全ではない可能性があります。 本番環境に変更を公開する前に、変更を確認します。

## 前提条件 {#prerequisites}

移行を作成する前に、次のことを確認してください。

* アップグレード アシスタントに必要な[権限](#permissions)です。
* Adobe Analytics拡張機能を使用するtags プロパティ。
* 移行する実装を含むそのプロパティ内のライブラリ。 ライブラリは、公開済みも含め、任意の状態にできます。 タグユーザーガイドの「[&#x200B; ライブラリ &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries)」を参照してください。

### 権限 {#permissions}

アップグレードアシスタントには、次のアクセス権が必要です。 組織のExperience Platform製品管理者と協力して、不足している権限を取得します。

| アクセスタイプ | 必須 |
| --- | --- |
| [Experience Platform の権限](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL スキーマの表示]</li><li>[!UICONTROL スキーマの管理]</li><li>[!UICONTROL データセットの表示]</li><li>[!UICONTROL &#x200B; データセットの管理]</li><li>[!UICONTROL ID 名前空間の表示]</li></ul> |
| 製品アクセス | <ul><li>データ収集（タグ）</li><li>Adobe Analytics</li></ul> |
| [&#x200B; タグ権限](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL プロパティの管理] |

準備ができたら、[移行を作成します](manager.md#create)。
