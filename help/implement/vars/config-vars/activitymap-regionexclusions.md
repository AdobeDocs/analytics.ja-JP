---
title: ActivityMap.regionExclusions
description: Activity Mapデータを地域でフィルタリングします。
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 12%

---

# ActivityMap.regionExclusions

`ActivityMap.regionExclusions` 変数を使用すると、[Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンションで収集されたディメンション項目に基づいて、Activity Mapデータを選択的にフィルタリングまたは除外できます。

## Web SDK 拡張機能の地域除外

**[!UICONTROL クリックデータ収集を有効にする]** が有効な場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.linkRegion` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

## Web SDK JavaScript ライブラリの地域の除外

[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) が有効な場合は、`clickCollection` オブジェクトで `filterClickDetails` コールバックを使用します。 このコールバック内では、`linkRegion` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Adobe Analytics拡張機能を使用した地域の除外

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## s.ActivityMap.regionExclusions （AppMeasurementを使用）

`s.ActivityMap.regionExclusions` 変数は、Activity Mapトラッキングから除外するコンマ区切りのフレーズを含む文字列です。 いずれかのフレーズが [Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンションで収集された値と一致する場合、すべてのActivity Mapデータがヒットから削除されます。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
