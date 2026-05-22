---
title: ActivityMap.regionExclusions
description: 地域ごとにActivity Map データをフィルタリングします。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
TQID: 'https://experienceleague.adobe.com/YWC5bRG0JSZBk-iJbBLAv2HjjbtOC2IYkUPXid-EsTM'
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
source-wordcount: 198
ht-degree: 18%

---

# ActivityMap.regionExclusions

`ActivityMap.regionExclusions`変数を使用すると、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションで収集されたディメンション項目に基づいて、Activity Map データを選択的にフィルタリングまたは除外できます。

## Web SDK拡張機能のリージョンの除外

**[!UICONTROL クリックデータ収集を有効にする]**&#x200B;が有効になっている場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.linkRegion`の値を確認し、値を変更するか、リンクトラッキングデータの収集を放棄します。

## Web SDK JavaScript ライブラリのリージョンの除外

[`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)が有効になっている場合、`clickCollection` オブジェクトで`filterClickDetails` コールバックを使用します。 このコールバック内で、`linkRegion`の値を確認し、値を変更するか、リンク追跡データの収集を放棄します。

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

## Adobe Analytics拡張機能を使用したリージョンの除外

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementを使用したs.ActivityMap.regionExclusions

`s.ActivityMap.regionExclusions`変数は、Activity Map トラッキングから除外するコンマ区切りフレーズを含む文字列です。 いずれかのフレーズが[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションで収集された値と一致する場合、すべてのActivity Map データがヒットから削除されます。

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
