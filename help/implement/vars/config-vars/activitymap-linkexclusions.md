---
title: ActivityMap.linkExclusions
description: リンク名でActivity Map データをフィルタリングします。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
TQID: 'https://experienceleague.adobe.com/m4ovqFSZBZ88KFm8lnKRI7z5wbbTNZygEj8koL6HC6E'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 17%

---

# ActivityMap.linkExclusions

`ActivityMap.linkExclusions`変数を使用すると、[Activity Map Link](/help/components/dimensions/activity-map-link.md) ディメンションのテキストに基づいて、Activity Map データを選択的にフィルタリングまたは除外できます。

## Web SDK拡張機能のリンク除外

**[!UICONTROL クリックデータ収集を有効にする]**&#x200B;が有効になっている場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.linkName`の値を確認し、値を変更するか、リンクトラッキングデータの収集を放棄します。

## Web SDK JavaScript ライブラリのリンク除外

[`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)が有効になっている場合、`clickCollection` オブジェクトで`filterClickDetails` コールバックを使用します。 このコールバック内で、`linkName`の値を確認し、値を変更するか、リンク追跡データの収集を放棄します。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Adobe Analytics拡張機能を使用した除外のリンク

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementを使用したs.ActivityMap.linkExclusions

`s.ActivityMap.linkExclusions`変数は、Activity Map トラッキングから除外するフレーズのコンマ区切り値を含む文字列です。 いずれかのフレーズが[Activity Map Link](/help/components/dimensions/activity-map-link.md) ディメンションで収集された値と一致する場合、すべてのActivity Map データがヒットから削除されます。 この変数は`linkUrl`ではなく`linkName`を参照することに注意してください。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
