---
title: ActivityMap.link
description: クリックされたリンクをActivity Mapが収集する方法をカスタマイズします。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 9%

---

# ActivityMap.link

`ActivityMap.link` 変数を使用すると、Activity Mapがリンク値の設定に使用するロジックを上書きできます。 この変数は、[`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) が提供するものよりも詳細に制御したい領域で役立ちます。

>[!CAUTION]
>この変数は、Activity Map ロジックを完全にオーバーライドします。 ここでオーバーライド関数を設定して誤った値を返すと、Activity MapのディメンションとActivity Mapのオーバーレイでデータ収集の問題が発生する可能性があります。

## Web SDKを使用したリンク値の上書き

コールバック [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) 使用して、Web SDKのペイロードを変更したり、データの送信を中止したりできます。

## Adobe Analytics拡張機能を使用したリンクのオーバーライド

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの ActivityMap.link と Analytics 拡張機能のカスタムコードエディター

この変数に関数を割り当てます。

* クリックされたHTML要素を受け取り、
* 文字列値を返します。 この文字列値は、[Activity Map リンク &#x200B;](/help/components/dimensions/activity-map-link.md) ディメンションに使用される最後の値です。

戻り値が [falsy](https://developer.mozilla.org/ja-JP/docs/Glossary/Falsy) の場合、Activity Mapのコンテキストデータ変数はすべてクリアされ、リンクデータはトラッキングされません。

## 例

タグの title 属性のみ `<a>` 使用します。 title 属性が存在しない場合、リンクはトラッキングされません。

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

手動で設定したリンク名を `s.tl` で返します（存在する場合）。それ以外の場合は、リンク URL を返します。

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

デフォルトのリンクロジックを完全に置き換える代わりに、条件によって変更することができます。

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

1. `linkName` が渡された場合、メソッドは `tl()` によって呼び出されました。 渡され `tl()` 値を `linkName` として返します。
2. Activity Mapによって呼び出される場合、`linkName` は渡されないので、link 要素を指定して `customFunction()` を呼び出します。 任意のカスタム関数を使用して、値を返すことができます。
3. 上記の戻り値がいずれも返されない場合は、通常フォールバックとして収集されるリンク名を使用します。
