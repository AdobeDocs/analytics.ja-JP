---
description: s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。
seo-description: s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。
seo-title: 同じリンクIDと地域を参照するリンクの区別
solution: Analytics
title: 同じリンクIDと地域を参照するリンクの区別
topic: Activity Map
uuid: f2da0cda- a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# 同じリンクIDと地域を参照するリンクの区別

s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。

例として、リンク ID と領域が同じで、Activity Map によって識別される "Buy" リンクが複数あるとします。

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
    <code>&lt; div id="recommendation panel"&gt;
&lt; div&gt;
&lt; a href="product1.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a href="product2.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a href="product3.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation パネル <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> </td> 
  </tr> 
 </tbody> 
</table>

これらのリンクの値を区別するには、Web ページとタグをどのようにカスタマイズすればよいでしょうか。オプションは 3 つあります。リンク ID をカスタマイズするか、領域をカスタマイズするか、AppMeasurement Activity Map モジュールファイルをカスタマイズするかです。

## s_objectID を使用したリンク ID のカスタマイズ {#section_01B0D463397B4837B2D46F087A6E5937}

リンクまたはページのリンクの場所に対して固有のオブジェクト ID を作成することにより、Activity Map のトラッキングを向上したり、Activity Map を使用して、リンク URL ではなく、リンクタイプやリンクの場所について報告します。s_objectID 変数について詳しくは、[ここ](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html)をクリックしてください。

>[!IMPORTANT]
>
>Activity Mapでs_ objectIDを使用する場合は、末尾のセミコロン（;）が必要になります。

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
    <code>&lt; div id="recommendation panel"&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product1';"href=» product1.html
&lt;/div&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product2';"href=» product2.html
&lt;/div&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product3';"href=» product3.html
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product2 </p> <p> </p> <p> </p> <p>Product3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 領域のカスタマイズ {#section_6B1EF302573B445DBAF44176D0A12DB9}

"Buy" リンクごとに独自の領域を定義することにより、領域をカスタマイズできます。これを行うには、"Buy" アンカータグごとに、親の 1 つに "id" パラメーターを追加します。

>[!NOTE]
>
>領域識別子として"id"パラメーターに厳密に制限されるわけではありません。JavaScript変数"s. ActivityMap. RegionIDAttribute"を使用して独自の識別子を設定することもできます。

<table id="table_250DB52A869C466B942517BABA1C287B"> 
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
    <code>&lt; div id="recommendation panel"&gt;
&lt; div id="region a"&gt;
&lt; a href="product1.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt;
&lt; div id="region b"&gt;
&lt; a href="product2.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt;
&lt; div id="region c"&gt;
&lt; a href="product3.html"&gt; Buy&lt;/a&gt;
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>

## AppMeasurement Activity Map モジュールファイルのカスタマイズ {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>変更されたコードをテストして、正しく動作することを確認してください。変更後のコードの動作については、アドビでは一切責任を負いません。

以下に、AppMeasurement. jsファイル内に（変更されたフォーム内に）含めることができる**汎用**リンク/地域関数の例をいくつか示します。

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

linkName は、s.tl に対する呼び出し中に渡されます。

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```

