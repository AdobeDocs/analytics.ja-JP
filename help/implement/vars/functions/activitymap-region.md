---
title: ActivityMap.region
description: Activity Mapがクリックした地域を収集する方法をカスタマイズします。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
TQID: 'https://experienceleague.adobe.com/EVVto7LRuTewu9y9AHLAPGn7sbqhJU3QSjlNtjKE5bQ'
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
source-wordcount: 218
ht-degree: 15%

---

# ActivityMap.region

`ActivityMap.region`変数を使用すると、Activity Mapがリージョン値の設定に使用するロジックを上書きできます。 この変数は、[`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md)が提供するものよりも詳細に制御したい領域で便利です。

>[!CAUTION]
>この変数は、Activity Map ロジックを完全に上書きします。 ここでオーバーライド関数を設定して誤った値を返すと、Activity Map ディメンションとActivity Map オーバーレイでデータ収集の問題が発生する可能性があります。

## Web SDKを使用したリージョン値の上書き

[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) コールバックを使用して、Web SDK ペイロードを変更したり、データの送信を中止したりできます。

## Adobe Analytics拡張機能を使用したリージョンオーバーライド

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのActivityMap.regionとAnalytics拡張機能のカスタムコードエディター

この変数に次の関数を割り当てます。

* クリックされたHTML要素を受け取ります。
* 文字列値を返します。 この文字列値は、[Activity Map Region](/help/components/dimensions/activity-map-region.md) ディメンションで使用される最終的な値です。

戻り値が[falsy](https://developer.mozilla.org/ja-JP/docs/Glossary/Falsy)の場合、すべてのActivity Map コンテキストデータ変数がクリアされ、リンクデータは追跡されません。

## 例

小文字のタグ名を地域として使用します。

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

特定の目的のクラス名を地域として使用します。

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
