---
title: データレイヤーオブジェクトをデータ要素にマッピングする
description: データレイヤーから読み取るようにタグを設定します。
feature: Tags
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/MmwNCdmt9TwNojJEyzbfTukeh4sKITk06gY-EBzjZPw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 46%
---
# データレイヤーオブジェクトをデータ要素にマッピングする

組織がデータレイヤーを確立してサイトに実装したら、タグ内のデータ要素にデータレイヤーオブジェクトをマッピングできます。

## 前提条件

[データレイヤーを作成する](../prepare/data-layer.md)：サイトにデータレイヤーが存在することを確認します。 技術的には、任意の JavaScript オブジェクトをマッピングしたり、ページから CSS 要素を直接スクレイピングしたりできますが、アドビではこの方法は最後の手段としてのみ使用することを推奨します。 サイトのレイアウトが変更されると、タグで使用される CSS セレクターの動作が停止し、データが失われます。

## タグを使用したデータ要素の作成

[データ要素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=ja)は、ツール全体で使用できる Adobe Experience Platform データ収集のコンポーネントです。 データ要素を使用して、Adobe Analytics 拡張機能で変数の値を割り当てることができます。

次の手順では、タグプロパティにインストールする必要がある[Adobe Client Data Layer拡張機能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/overview)を使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティを選択します。
1. 「**[!UICONTROL データ要素]**」タブを選択し、「**[!UICONTROL データ要素を追加]**」を選択します。

   ![データ要素の作成](assets/createelement.png)

1. データ要素の名前（`Page name`など）を入力します。
1. **[!UICONTROL 拡張機能]** ドロップダウンリストで、**[!UICONTROL Adobe Client Data Layer]**&#x200B;を選択します。
1. 「**[!UICONTROL データ要素タイプ]**」ドロップダウンリストで、「**[!UICONTROL データレイヤー計算状態]**」を選択します。
1. **[!UICONTROL 戻り値]**&#x200B;で、**[!UICONTROL 特定のパス]**&#x200B;を選択し、データレイヤーの値（`page.name`など）へのパスを入力します。 パスを検証するには、ブラウザーのコンソールで`adobeDataLayer.getState("page.name")`を実行します。
1. 「**[!UICONTROL 保存]**」を選択します。

これらのデータ要素は、拡張機能の&#x200B;**[!UICONTROL データレイヤーのプッシュ]** イベントトリガーのルールで使用します。これにより、データレイヤーにプッシュからのデータが読み込まれ、含まれます。 [ データ要素タイプ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/client-data-layer/data-element-types#computed-state)を参照してください。

### オブジェクトベースのデータレイヤー {#object-based}

データ層がCEDDL `digitalData` オブジェクトなどのJavaScript オブジェクトである場合は、代わりに&#x200B;**[!UICONTROL Core]**&#x200B;拡張機能の&#x200B;**[!UICONTROL JavaScript Variable]** データ要素タイプを使用します。 値へのパス（`digitalData.page.pageInfo.pageName`など）を入力します。 この種類のデータ要素は、Adobe Client Data Layerを読み取ることができません。このレイヤーは、データをオブジェクトのプロパティではなく計算された状態で保存します。

## 次の手順

[Launch データ要素を Analytics 変数にマッピングする](elements-to-variable.md)：Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
