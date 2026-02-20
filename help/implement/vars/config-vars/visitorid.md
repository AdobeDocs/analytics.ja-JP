---
title: visitorID
description: カスタム訪問者 ID を使用します。
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 19%

---

# visitorID

Adobeでは、複数の異なる方法を使用して、サイト上の [&#x200B; 訪問者を識別 &#x200B;](../../id/overview.md) します。 **`visitorID` 変数は、訪問者識別のその他すべての方法を上書きします。**

>[!IMPORTANT]
>
> この変数の使用はお勧めしません。代わりに、[Adobe Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を使用してください。

## Analytics での `visitorID` の使用方法

この変数は、他のすべてのフォームの訪問者識別に代わる手動の訪問者 ID 上書きです。 1 人の訪問者としてカウントされるには、1 人のユーザーに対するすべてのヒットが、同じ `visitorID` 値を使用する必要があります。

* `visitorID` を省略したヒットは、別の訪問者識別方法にフォールバックし、別の訪問者として扱われます。
* 複数の `visitorID` 値を使用するヒットは、個別の訪問者として扱われます。
* Adobeでは、異なる訪問者 ID を一緒に使用するヒットをステッチしません。

ID の優先順位と ID を混在させて訪問者数を増やす理由について詳しくは、[Adobe Analyticsでの訪問者の ID](../../id/overview.md) を参照してください。

>[!WARNING]
>
>そのユーザーのすべてのヒットに設定され、値が変更されないことが保証できる場合にのみ、`visitorID` を設定します。 一部のヒットのみに設定する、訪問の途中（認証時など）に導入する、またはヒット間で変更することで、1 人の訪問者のアクティビティを複数の訪問者に分割します。

>[!CAUTION]
>
>カスタム訪問者 ID の値が無効な場合、データが正しくなくなり、レポートのパフォーマンスが低下する可能性があります。 この変数にデフォルトまたはプレースホルダー値（`"0"` や `"NULL"` など）が含まれている場合、Adobeはこれらのヒットを同じ訪問者であるかのように処理します。 この状況では、誤ったデータが発生し、人為的に訪問者の数が少なくなり、訪問者レベルのセグメントが期待どおりに機能しません。 また、カスタム訪問者 ID の実装が誤っていると、処理サーバーに大きな負荷がかかり、[&#x200B; 待ち時間 &#x200B;](/help/technotes/latency.md) が増え、レポートのパフォーマンスが低下する可能性があります。

## Adobe Analytics拡張機能を使用した訪問者 ID

「[!UICONTROL 訪問者 ID]」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティを選択します。
3. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「Adobe Analytics」の下にある **[!UICONTROL 設定]** ボタンを選択します。
4. 「[!UICONTROL Cookies]」アコーディオンを展開し、「[!UICONTROL 訪問者 ID]」フィールドを表示します。

このフィールドを、カスタム訪問者 ID を含むデータ要素に割り当てます。**すべての訪問者に対して、このフィールドを単一の静的な値に設定しないでください。** 訪問者ごとに解決され、すべてのヒットにわたって一定であるデータ要素を使用します。

## AppMeasurementの s.visitorID と Analytics 拡張機能のカスタムコードエディター

`s.visitorID` 変数は、訪問者の一意のカスタム識別子を含む文字列です。有効な値は、100 バイトまでの英数字です。 この変数では、ダッシュ、スペース、アンダースコアまたはシンボルの使用を避けます。

```js
s.visitorID = "abc123";
```

## Web SDKを使用した訪問者 ID

Adobe Experience Platform Edge Networkでは、XDM の [ID マップ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=ja#using-identitymap) を使用して複数の識別子を指定できます。 ID マップ内の各 ID は、異なる名前空間を持ちます。 [&#x200B; データストリーム設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja#analytics) の一部として、訪問者 ID に使用する名前空間を指定できます。 このフィールドを設定すると、この名前空間に指定された値でイベントを送信した場合、Analytics で訪問者 ID として自動的に使用されます。
