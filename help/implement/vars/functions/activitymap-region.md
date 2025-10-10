---
title: ActivityMap.region
description: クリックされたリージョンのActivity Mapによる収集方法をカスタマイズします。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---

# ActivityMap.region

`ActivityMap.region` 変数を使用すると、Activity Mapがリージョン値の設定に使用するロジックを上書きできます。 この変数は、[`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) が提供するものよりも詳細に制御したい領域で役立ちます。

>[!CAUTION]
>この変数は、Activity Map ロジックを完全にオーバーライドします。 ここでオーバーライド関数を設定して誤った値を返すと、Activity MapのディメンションとActivity Mapのオーバーレイでデータ収集の問題が発生する可能性があります。

## Web SDKを使用した地域値の上書き

コールバック [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) 使用して、Web SDKのペイロードを変更したり、データの送信を中止したりできます。

## Adobe Analytics拡張機能を使用した地域の上書き

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの ActivityMap.region と Analytics 拡張機能のカスタムコードエディター

この変数に関数を割り当てます。

* クリックされたHTML要素を受け取り、
* 文字列値を返します。 この文字列値は、[Activity Map地域 &#x200B;](/help/components/dimensions/activity-map-region.md) ディメンションで使用される最後の値です。

戻り値が [falsy](https://developer.mozilla.org/ja-JP/docs/Glossary/Falsy) の場合、Activity Mapのコンテキストデータ変数はすべてクリアされ、リンクデータはトラッキングされません。

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
