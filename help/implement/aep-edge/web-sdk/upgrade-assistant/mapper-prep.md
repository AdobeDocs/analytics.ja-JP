---
title: Web SDK アップグレードアシスタントでのマッパーの準備
description: レポートスイートのAnalytics変数を確認し、XDM マッピングに進める変数を選択します。
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
source-wordcount: '507'
ht-degree: 0%
---
# マッパーの準備

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep"
>title="マッパーの準備"
>abstract="タグプロパティが各レポートスイートに送信するAnalytics変数を確認します。 ここで選択した変数は、XDM マッピングに進みます。 タブを使用して、最近のデータの確認、重複する変数の検索、レポートスイート間の設定の比較を行います。"

<!-- markdownlint-enable MD034 -->

アップグレードアシスタントは、タグプロパティがデータを送信するレポートスイートを特定し、実装のAnalytics変数を各レポートスイートの設定と最近のデータと比較します。 この手順を使用して、どの変数が[XDM マッピング &#x200B;](xdm-mapping.md)に進むかを決定します。

アップグレードアシスタントは、レポートスイートを使用して、実装が設定する変数とその設定方法を把握します。 過去90日間のアクティビティデータ。

## バリアブルアクティビティ {#variable-activity}

「**[!UICONTROL 変数アクティビティ]**」タブには、[変数分析](#variable-analysis)でマッピングするように選択したレポートスイートのAnalytics変数が一覧表示され、各変数が過去90日間にデータを収集したかどうかが表示されます。

選択した変数はXDM マッピングに転送されます。 Web SDKの実装において、データを収集しなくなった変数や不要になった変数のクリアを検討します。 最近のアクティビティがない変数は、季節的な変数やトラフィックの少ない変数など、まだ使用されている可能性があるので、消去する前に不要であることを確認してください。

リスト変数とリスト propのそれぞれについて、その値を区切る区切り文字を入力します。 アップグレードアシスタントはAdobe Analyticsから区切り文字を取得できず、各区切り文字が含まれるまで続行できません。

## 変数分析 {#variable-analysis}

タグプロパティが複数のレポートスイートにデータを送信する場合は、まずマッピングするレポートスイートを選択します。 次に、**[!UICONTROL 変数分析]** タブは、決定が必要な可能性のある変数をマッピングする前にフラグを立てます。

* 同じデータを収集するように見える変数。 同じ情報を収集していることを確認し、それらを単一の変数にマージするか、別の場所に保存するかを決定します。
* 最近データを収集していない変数。
* 値がすべて「未指定」の変数。

## レポートスイートの比較 {#compare}

タグプロパティが複数のレポートスイートにデータを送信する場合、「**[!UICONTROL レポートスイートを比較]**」タブは、各変数の設定をそれらのレポートスイートの3つまで比較します。 スキーマにマッピングする前に、レポートスイート間で異なる設定の変数を検索する場合に使用します。

## レポートスイートデータの更新 {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep_refresh"
>title="レポートスイートデータの更新"
>abstract="このタグプロパティにリンクされたレポートスイートを、変数設定と最近のデータを含めて再度チェックし、変数分析を再実行します。 アップグレードアシスタントがまだレポートスイートを見つけていない場合は、最初にタグプロパティでそれらを探します。 選択と決定は保持されます。"

<!-- markdownlint-enable MD034 -->

この手順で、アップグレードアシスタントが分析するレポートスイートを変更できます。 移行中にレポートスイートの設定が変更された場合は、**[!UICONTROL レポートスイートデータの更新]**&#x200B;を選択して分析を再実行します。 アップグレードアシスタントは、既存の選択と決定を保持します。

完了したら、**[!UICONTROL 保存して]**&#x200B;を選択し、[XDM マッピング &#x200B;](xdm-mapping.md)に移動します。
