---
title: sa
description: いつでも実装のレポートスイートを変更できます。
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 38%

---

# sa

`sa()` メソッドを使用すると、ページ上のレポートスイートをいつでも動的に変更できます。ページをリロードせずに別のレポートスイートにデータを送信する場合は、このメソッドを使用できます。

## Web SDK を使用したレポートスイートの処理

Web SDK は、特定のデータストリームにデータを送信することで動作し、特定のデータストリームは、目的の Analytics レポートスイートにデータを転送します。 単一のデータストリームは、データを複数のレポートスイートに転送できます。 この節の内容は、Web SDK 拡張機能と、Web SDK の手動実装の両方に当てはまります。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. クリック **[!UICONTROL データストリーム]** 左側に
1. 目的のデータストリームをクリックするか、 **[!UICONTROL 新規データストリーム]**.
1. クリック **[!UICONTROL サービスを追加]**&#x200B;を選択し、「 **[!UICONTROL Adobe Analytics]**.
1. 目的のレポートスイート ID を入力します。 同じデータを複数のレポートスイートに送信する場合は、 **[!UICONTROL レポートスイートの追加]**.
1. 目的のレポートスイートをすべて入力したら、 **[!UICONTROL 保存]**.

## Web SDK 拡張機能を使用した目的の Datastream の設定

Web SDK 拡張機能には、各環境用の Datastream ドロップダウンが用意されています。 または、データストリーム ID を手動で入力することもできます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データストリーム]」で、各環境のドロップダウンから目的の Datastream を選択します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## Web SDK を手動で実装する目的の Datastream の設定

を `edgeConfigId` 設定変数から Datastream ID への変換。 Adobe Experience Platformデータ収集でデータストリームを表示すると、右側にデータストリーム ID が表示されます。

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

詳しくは、 [Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したレポートスイートの変更

インターフェイス内のレポートスイートを柔軟に変更する方法はありません。Adobe Analytics 拡張機能を設定する際に、「[!UICONTROL ライブラリ管理]」アコーディオンの下でレポートスイートを設定できます。ただし、ルールを使用してレポートスイートを変更または更新することはできません。設定後にレポートスイートの値を更新する場合は、AppMeasurement 構文に従ってカスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.sa()

`s.sa()` メソッドを呼び出して、送信先のレポートスイートを変更します。唯一の引数は、レポートスイート ID を含む文字列、またはコンマで区切られた複数のレポートスイート ID です。レポートスイート ID 引数は必須です。文字列引数にスペースを使用しないでください。

```js
s.sa("examplersid");
```

例えば、ユーザーがサイト上で特定のアクションを実行した場合にレポートスイートを変更できます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
