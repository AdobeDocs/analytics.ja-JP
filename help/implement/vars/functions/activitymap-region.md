---
title: ActivityMap.region
description: クリックされたリージョンをActivity Mapがどのように収集するかをカスタマイズします。
feature: Variables
role: Admin, Developer
source-git-commit: 1fb57590714ad2412323416289dee967eef07fad
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 12%

---

# ActivityMap.region

`ActivityMap.region` 変数を使用すると、Activity Mapがリージョン値の設定に使用するロジックを上書きできます。 この変数は、[`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) が提供するものよりも詳細に制御したい領域で役立ちます。

>[!CAUTION]
>この変数は、Activity Mapロジックを完全にオーバーライドします。 ここでオーバーライド関数を設定して誤った値を返すと、Activity MapディメンションとActivity Mapのオーバーレイでデータ収集の問題が発生する可能性があります。

## Web SDK を使用した地域値の上書き

コールバック [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) 使用して、Web SDK ペイロードを変更したり、データの送信を中止したりできます。

## Adobe Analytics拡張機能を使用した地域の上書き

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの ActivityMap.region と Analytics 拡張機能のカスタムコードエディター

この変数に関数を割り当てます。

* クリックされたHTML要素を受け取り、さらに
* 文字列値を返します。 この文字列値は、[Activity Map地域 ](/help/components/dimensions/activity-map-region.md) ディメンションに使用される最後の値です。

戻り値が [falsy](https://developer.mozilla.org/ja-JP/docs/Glossary/Falsy) の場合、すべてのActivity Mapコンテキストデータ変数がクリアされ、リンクデータは追跡されません。

## 例

小文字のタグ名を地域として使用：

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

特定のクラス名をリージョンとして使用します。

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
