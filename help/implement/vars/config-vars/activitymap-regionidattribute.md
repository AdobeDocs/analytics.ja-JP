---
title: ActivityMap.regionIDAttribute
description: リージョンを決定するためにActivity Mapが検索する属性を変更します。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 11%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute` 変数を使用すると、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションを決定する際にActivity Mapが検索する属性を変更できます。 Activity Map リージョンで `id` 属性があまり役に立たない構造になっているサイトの場合は、この変数を設定して別の属性を調べることができます。

## Web SDK拡張機能の地域 ID 属性

**[!UICONTROL クリックデータ収集を有効にする]** が有効な場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.clickedElement` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

## Web SDK JavaScript ライブラリの地域 ID 属性

[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) が有効な場合は、`filterClickDetails` オブジェクトで `clickCollection` コールバックを使用します。 このコールバック内で、`clickedElement` の値を確認し、収集した領域のロジックをカスタマイズできます。

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

## Adobe Analytics拡張機能を使用した地域 ID 属性

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementを使用した s.ActivityMap.regionIDAttribute

`s.ActivityMap.regionIDAttribute` 変数は、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションを決定する属性を表す文字列です。 この変数は、デフォルトで `id` に設定されます。 この変数を変更すると、Activity Mapでは `id` 属性は検索されなくなりますが、リージョンを特定するための他の条件（セマンティック要素など）は検索されます。

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
