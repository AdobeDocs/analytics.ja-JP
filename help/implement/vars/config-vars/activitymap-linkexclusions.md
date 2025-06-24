---
title: ActivityMap.linkExclusions
description: リンク名でActivity Map データをフィルタリングします。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 12%

---

# ActivityMap.linkExclusions

`ActivityMap.linkExclusions` 変数を使用すると、[Activity Map リンク ](/help/components/dimensions/activity-map-link.md) ディメンション内のテキストに基づいて、Activity Map データを選択的にフィルタリングまたは除外できます。

## Web SDK拡張機能でのリンクの除外

**[!UICONTROL クリックデータ収集を有効にする]** が有効な場合、**[!UICONTROL フィルタークリックプロパティ]** コールバックコードブロックを使用します。 このコードブロック内で、`content.linkName` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

## Web SDK JavaScript ライブラリのリンクの除外

[`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) が有効な場合は、`clickCollection` オブジェクトで `filterClickDetails` コールバックを使用します。 このコールバック内では、`linkName` の値を確認し、値を変更するか、リンクトラッキングデータの収集を破棄できます。

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

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementを使用した s.ActivityMap.linkExclusions

`s.ActivityMap.linkExclusions` 変数は、Activity Mapのトラッキングから除外するフレーズのコンマ区切り値を含む文字列です。 いずれかのフレーズが [Activity Map リンク ](/help/components/dimensions/activity-map-link.md) ディメンションで収集された値と一致する場合、すべてのActivity Map データがヒットから削除されます。 この変数は、`linkUrl` ではなく `linkName` を参照することに注意してください。

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
