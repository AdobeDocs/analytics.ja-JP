---
title: sa
description: いつでも実装のレポートスイートを変更できます。
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

`sa()` メソッドを使用すると、ページ上のレポートスイートをいつでも動的に変更できます。ページをリロードせずに別のレポートスイートにデータを送信する場合は、このメソッドを使用できます。

## Web SDKを使用したレポートスイートの処理

Web SDKは、特定のデータストリームにデータを送信することで、目的の分析レポートスイートにデータを転送します。 1 つのデータストリームで複数のレポートスイートにデータを転送できます。 この節の内容は、Web SDK拡張機能と手動での Web SDKの実装の両方に適用されます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の **[!UICONTROL データストリーム]** をクリックします。
1. 目的のデータストリームをクリックするか、「**[!UICONTROL 新しいデータストリーム]**」をクリックします。
1. 「**[!UICONTROL サービスを追加]**」をクリックし、「**[!UICONTROL Adobe Analytics]**」を選択します。
1. 目的のレポートスイート ID を入力します。 同じデータを複数のレポートスイートに送信する場合は、「**[!UICONTROL レポートスイートを追加]**」をクリックします。
1. 必要なレポートスイートをすべて入力したら、「**[!UICONTROL 保存]**」をクリックします。

## Web SDK拡張機能を使用して目的のデータストリームを設定します

Web SDK拡張機能には、各環境の「データストリーム」ドロップダウンリストが用意されています。 または、データストリーム ID を手動で入力することもできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL  拡張機能 ]」タブに移動し、「{4 **[!UICONTROL Adobe Experience Platform Web SDK]」の下にある「設定]** ボタンをクリックします。[!UICONTROL 
1. [!UICONTROL  データストリーム ] の下で、各環境のドロップダウンリストから目的のデータストリームを選択します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## Web SDKを手動で実装する目的のデータストリームを設定します。

`datastreamId` 設定変数をデータストリーム ID に設定します。 Adobe Experience Platform Data Collection でデータストリームを表示すると、データストリーム ID が右側に見つかります。

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

詳しくは、Web SDK ドキュメントの [Web SDKの設定 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) を参照してください。

## Adobe Analytics拡張機能を使用したレポートスイートの変更

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。Adobe Analytics 拡張機能を設定する際に、「[!UICONTROL ライブラリ管理]」アコーディオンの下でレポートスイートを設定できます。ただし、ルールを使用してレポートスイートを変更または更新することはできません。設定後にレポートスイートの値を更新する場合は、AppMeasurement 構文に従ってカスタムコードエディターを使用します。

## AppMeasurementの s.sa （）と Analytics 拡張機能のカスタムコードエディター

`s.sa()` メソッドを呼び出して、送信先のレポートスイートを変更します。唯一の引数は、レポートスイート ID を含む文字列、またはコンマで区切られた複数のレポートスイート ID です。レポートスイート ID 引数は必須です。文字列引数にスペースを使用しないでください。

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
