---
title: ActivityMap.link
description: Activity Mapがクリックされたリンクを収集する方法をカスタマイズします。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
TQID: 'https://experienceleague.adobe.com/5NCARDGth07l5vixudVzLrE7FVrh82PS4xNrJ61gnow'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 308
ht-degree: 10%

---

# ActivityMap.link

`ActivityMap.link`変数を使用すると、Activity Mapがリンク値の設定に使用するロジックを上書きできます。 この変数は、[`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md)が提供するものよりも詳細に制御したい領域で便利です。

>[!CAUTION]
>この変数は、Activity Map ロジックを完全に上書きします。 ここでオーバーライド関数を設定して誤った値を返すと、Activity Map ディメンションとActivity Map オーバーレイでデータ収集の問題が発生する可能性があります。

## Web SDKを使用したリンク値の上書き

[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) コールバックを使用して、Web SDK ペイロードを変更したり、データの送信を中止したりできます。

## Adobe Analytics拡張機能を使用したリンクオーバーライド

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのActivityMap.linkとAnalytics拡張機能のカスタムコードエディター

この変数に次の関数を割り当てます。

* クリックされたHTML要素を受け取ります。
* 文字列値を返します。 この文字列値は、[Activity Map リンク ](/help/components/dimensions/activity-map-link.md) ディメンションで使用される最終的な値です。

戻り値が[falsy](https://developer.mozilla.org/ja-JP/docs/Glossary/Falsy)の場合、すべてのActivity Map コンテキストデータ変数がクリアされ、リンクデータは追跡されません。

## 例

`<a>` タグのtitle属性のみを使用してください。 title属性が存在しない場合、リンクは追跡されません。

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

`s.tl`に手動で設定したリンク名が存在する場合は返し、そうでない場合はリンク URLを返します。

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

デフォルトのリンクロジックを完全に置き換える代わりに、条件付きで変更することができます。

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. `linkName`が渡された場合、メソッドは`tl()`によって呼び出されました。 `tl()`さんが`linkName`として渡したものを返します。
2. Activity Mapによって呼び出されると、`linkName`は渡されないので、`customFunction()`をlink要素で呼び出します。 値を返すカスタム関数を使用できます。
3. 上記のいずれの戻り値も返さない場合は、通常フォールバックとして収集されるリンク名を使用します。
