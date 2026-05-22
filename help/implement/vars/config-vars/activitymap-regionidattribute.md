---
title: ActivityMap.regionIDAttribute
description: Activity Mapが検索する属性を変更して、リージョンを決定します。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: 'https://experienceleague.adobe.com/DJj1qmoYB0iMxDszdGKYTeczkjv0OvxXAYlg2irpKb0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 15%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute`変数を使用すると、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションを決定する際にActivity Mapが検索する属性を変更できます。 サイトが`id`属性をActivity Map リージョンに対して使いにくくする構造になっている場合は、この変数を設定して別の属性を見ることができます。

## Web SDK拡張機能のRegion ID属性

**[!UICONTROL クリックデータ収集を有効にする]**&#x200B;が有効になっている場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.clickedElement`の値を確認し、値を変更するか、リンクトラッキングデータの収集を放棄します。

## Web SDK JavaScript ライブラリのリージョン ID属性

[`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)が有効になっている場合、`clickCollection` オブジェクトで`filterClickDetails` コールバックを使用します。 このコールバック内で、`clickedElement`の値を確認し、収集した領域のロジックをカスタマイズできます。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Adobe Analytics拡張機能を使用したRegion ID属性

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementを使用したs.ActivityMap.regionIDAttribute

`s.ActivityMap.regionIDAttribute`変数は、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションを決定する属性を表す文字列です。 この変数は、デフォルトで`id`に設定されています。 この変数を変更すると、Activity Mapは`id`属性を検索しなくなり、リージョンを判断する他の条件（セマンティック要素など）を検索します。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
