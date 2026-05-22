---
title: sa
description: いつでも実装のレポートスイートを変更できます。
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/xA02rmiZkiSsFwmACdN-YUlwKVGgeprnySEKEO0w3l8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 447
ht-degree: 44%

---

# sa

`sa()` メソッドを使用すると、ページ上のレポートスイートをいつでも動的に変更できます。 ページをリロードせずに別のレポートスイートにデータを送信する場合は、このメソッドを使用できます。

## Web SDKを使用したレポートスイートの処理

Web SDKは、特定のデータストリームにデータを送信し、目的のAnalytics レポートスイートにデータを転送することで動作します。 単一のデータストリームは、複数のレポートスイートにデータを転送できます。 このセクションは、Web SDK拡張機能とWeb SDKを手動で実装する場合の両方に適用されます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の&#x200B;**[!UICONTROL データストリーム]**&#x200B;をクリックします。
1. 目的のデータストリームをクリックするか、**[!UICONTROL 新規データストリーム]**&#x200B;をクリックします。
1. 「**[!UICONTROL サービスを追加]**」をクリックし、**[!UICONTROL Adobe Analytics]**&#x200B;を選択します。
1. 必要なレポートスイート IDを入力します。 同じデータを複数のレポートスイートに送信する場合は、**[!UICONTROL レポートスイートを追加]**&#x200B;をクリックします。
1. 必要なすべてのレポートスイートを入力したら、**[!UICONTROL 保存]**&#x200B;をクリックします。

## Web SDK拡張機能を使用して、目的のデータストリームを設定します

Web SDK拡張機能には、各環境のデータストリームドロップダウンリストが表示されます。 または、データストリーム IDを手動で入力することもできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL &#x200B; データストリーム &#x200B;]で、各環境のドロップダウンリストから目的のデータストリームを選択します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## Web SDKを手動で実装する目的のデータストリームを設定します

`datastreamId`設定変数をデータストリーム IDに設定します。 データストリーム IDは、Adobe Experience Platform Data Collectionでデータストリームを表示する際の右側にあります。

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

詳しくは、Web SDKのドキュメントの「[Web SDKの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)」を参照してください。

## Adobe Analytics拡張機能を使用したレポートスイートの変更

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。 Adobe Analytics 拡張機能を設定する際に、「[!UICONTROL ライブラリ管理]」アコーディオンの下でレポートスイートを設定できます。 ただし、ルールを使用してレポートスイートを変更または更新することはできません。 設定後にレポートスイートの値を更新する場合は、AppMeasurement 構文に従ってカスタムコードエディターを使用します。

## AppMeasurementのs.sa （）とAnalytics拡張機能のカスタムコードエディター

`s.sa()` メソッドを呼び出して、送信先のレポートスイートを変更します。 唯一の引数は、レポートスイート ID を含む文字列、またはコンマで区切られた複数のレポートスイート ID です。 レポートスイート ID 引数は必須です。 文字列引数にスペースを使用しないでください。

```js
s.sa("examplersid");
```

例えば、ユーザーがサイトで特定のアクションを実行した場合、レポートスイートを変更できます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
