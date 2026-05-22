---
title: visitorID
description: カスタム訪問者 ID を使用します。
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/2lfkJimoLDCqVNqTDE1bsN92ulwvtZftXF-x0990Udw'
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
source-wordcount: 510
ht-degree: 20%

---

# visitorID

Adobeでは、サイト上の訪問者を[識別](../../id/overview.md)するために、いくつかの異なる方法を使用しています。 **変数`visitorID`は、他のすべての訪問者識別方法を上書きします。**

>[!IMPORTANT]
>
>この変数の使用はお勧めしません。 代わりに、[Adobe Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してください。

## Analyticsでの`visitorID`の使用方法

この変数は、他のすべての形式の訪問者IDに代わる手動の訪問者IDの上書きです。 1人の訪問者としてカウントするには、ユーザーのすべてのヒットで同じ`visitorID`値を使用する必要があります。

* `visitorID`を省略したヒットは、別の訪問者識別方法にフォールバックし、別の訪問者として扱われます。
* 複数の`visitorID`値を使用するヒットは、個別の訪問者として扱われます。
* Adobeでは、異なる訪問者IDを使用するヒットをつなぎ合わせることはできません。

IDの優先順位と、IDを混在させることで訪問者数が増加する理由について詳しくは、[Adobe Analyticsでの訪問者特定](../../id/overview.md)を参照してください。

>[!WARNING]
>
>`visitorID`は、そのユーザーのすべてのヒットに設定され、値が変わらないことを保証できる場合にのみ設定します。 一部のヒットだけを設定したり、訪問を通じて部分的に紹介したり（認証時など）、ヒット間で変更したりすると、1人の訪問者のアクティビティが複数の訪問者に分割されます。

>[!CAUTION]
>
>カスタム訪問者IDの値が無効な場合、データが正しくなくなり、レポートのパフォーマンスが低下する可能性があります。 この変数にデフォルト値またはプレースホルダー値（`"0"`や`"NULL"`など）が含まれている場合、Adobeはこれらのヒットを同じ訪問者として扱います。 この場合、訪問者数が人為的に低く、訪問者レベルのセグメントが期待どおりに動作せず、誤ったデータが返されます。 カスタム訪問者IDが誤って実装されると、処理サーバーに大きな負荷がかかり、[遅延](/help/technotes/latency.md)が増加し、レポートのパフォーマンスが低下する可能性もあります。

## Adobe Analytics拡張機能を使用した訪問者ID

「[!UICONTROL 訪問者 ID]」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティを選択します。
3. 「[!UICONTROL Extensions]」タブに移動し、「**[!UICONTROL Configure]**」ボタンをAdobe Analyticsの下から選択します。
4. 「[!UICONTROL Cookies]」アコーディオンを展開し、「[!UICONTROL 訪問者 ID]」フィールドを表示します。

このフィールドを、カスタム訪問者 ID を含むデータ要素に割り当てます。 **すべての訪問者に対して、このフィールドを1つの静的値に設定しないでください。** 訪問者ごとに解決し、すべてのヒットで一定であるデータ要素を使用します。

## AppMeasurementのs.visitorIDとAnalytics拡張機能のカスタムコードエディター

`s.visitorID` 変数は、訪問者の一意のカスタム識別子を含む文字列です。 有効な値には、最大100 バイトの英数字が含まれます。 この変数では、ダッシュ、スペース、アンダースコアまたはシンボルの使用を避けます。

```js
s.visitorID = "abc123";
```

## Web SDKを使用した訪問者ID

Adobe Experience Platform Edge Networkでは、XDMの[ID マップ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=ja#using-identitymap)を使用して複数のIDを指定できます。 ID マップ内の各IDには、異なる名前空間があります。 [&#x200B; データストリーム設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja#analytics)の一部として、訪問者IDに使用する名前空間を指定できます。 このフィールドを設定すると、この名前空間に指定された値を持つイベントを送信すると、Analyticsで訪問者IDとして自動的に使用されます。
