---
description: s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。
title: 同じリンク ID および領域を参照する複数のリンクの区別
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 59%

---

# 同じリンク ID および領域を参照する複数のリンクの区別

s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。

例として、リンク ID と領域が同じで、Activity Map によって識別される &quot;Buy&quot; リンクが複数あるとします。

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> コードサンプル </th>
   <th colname="col2" class="entry"> リンク ID </th>
   <th colname="col3" class="entry"> 領域 </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

これらのリンクの値を区別するには、Web ページとタグをどのようにカスタマイズすればよいでしょうか。オプションは 3 つあります。リンク ID をカスタマイズするか、領域をカスタマイズするか、AppMeasurement Activity Map モジュールファイルをカスタマイズするかです。

## s_objectID を使用したリンク ID のカスタマイズ {#section_01B0D463397B4837B2D46F087A6E5937}

リンクまたはページ上のリンクの場所に対して一意のオブジェクトID `s_objectID`を作成することで、Activity Mapトラッキングの向上や、Activity Mapを使用して、リンクURLではなく、リンクタイプやリンクの場所に関するレポートを作成できます。  変数について詳しくは、[ここ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html)をクリックしてください。`s_objectID`

>[!IMPORTANT]
>
>Activity Mapで`s_objectID`を使用する場合は、末尾のセミコロン(`;`)が必要です。
<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> コードサンプル </th>
   <th colname="col2" class="entry"> リンク ID </th>
   <th colname="col3" class="entry"> 領域 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
    recommendationパネル<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## 領域のカスタマイズ {#section_6B1EF302573B445DBAF44176D0A12DB9}

各「購入」リンクに独自の地域が定義されていることを確認することで、地域をカスタマイズできます。 これをおこなうには、各「購入」アンカータグの親の1つに`"id"`パラメーターを追加します。

>[!NOTE]
>領域IDは、`"id"`パラメーターに厳密に制限されているわけではありません。 また、JavaScript変数`"s.ActivityMap.regionIDAttribute"`を使用して独自の識別子を設定することもできます。
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> コードサンプル </th>
   <th colname="col2" class="entry"> リンク ID </th>
   <th colname="col3" class="entry"> 領域 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
    購入<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    region a<br/>
     <br/>
     <br/>
    地域b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## AppMeasurement Activity Map モジュールファイルのカスタマイズ {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
必ず、変更したコードをテストして、適切に機能することを確認してください。変更後のコードの動作については、アドビでは一切責任を負いません。

AppMeasurement.js ファイルに（変更した形式で）含めることのできる&#x200B;**一般的な**&#x200B;リンク／領域関数の例を 2 つ示します。

```
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

`linkName`は、`s.tl()`への呼び出し中に渡されます。

```
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
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
