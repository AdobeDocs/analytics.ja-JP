---
title: ActivityMap.regionIDAttribute
description: Activity Mapが検索する属性を変更して、リージョンを決定します。
feature: Variables
role: Admin, Developer
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 10%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute` 変数を使用すると、[Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンションを決定する際にActivity Mapが検索する属性を変更できます。 `id` 属性がActivity Mapリージョンに対して役に立たない構造になっているサイトの場合は、この変数を設定して別の属性を調べることができます。

## Web SDK 拡張機能の地域 ID 属性

**[!UICONTROL クリックデータ収集を有効にする]** が有効な場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.clickedElement` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

## Web SDK JavaScript ライブラリの地域 ID 属性

[`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) が有効な場合は、`clickCollection` オブジェクトで `filterClickDetails` コールバックを使用します。 このコールバック内で、`clickedElement` の値を確認し、収集した領域のロジックをカスタマイズできます。

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

`s.ActivityMap.regionIDAttribute` 変数は、[Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンションを特定する属性を表す文字列です。 この変数は、デフォルトで `id` に設定されます。 この変数を変更すると、Activity Mapは `id` 属性を検索しなくなり、領域を特定するための他の条件（セマンティック要素など）を検索します。

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
