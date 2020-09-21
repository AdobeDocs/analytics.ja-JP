---
description: s_objectID 変数を使用したリンク ID のカスタマイズ、領域のカスタマイズ、AppMeasurement Activity Map モジュールファイルのカスタマイズによってリンクを区別できます。
title: 同じリンク ID および領域を参照する複数のリンクの区別
topic: Activity map
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: 370d81bafc523b00a38b0064ad4ca3e6bb655d9f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation パネル <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> </td> 
  </tr> 
 </tbody> 
</table>

これらのリンクの値を区別するには、Web ページとタグをどのようにカスタマイズすればよいでしょうか。オプションは 3 つあります。リンク ID をカスタマイズするか、領域をカスタマイズするか、AppMeasurement Activity Map モジュールファイルをカスタマイズするかです。

## s_objectID を使用したリンク ID のカスタマイズ {#section_01B0D463397B4837B2D46F087A6E5937}

リンクまたはページのリンクの場所に対して固有のオブジェクト ID を作成することにより、Activity Map のトラッキングを向上したり、Activity Map を使用して、リンク URL ではなく、リンクタイプやリンクの場所について報告します。s_objectID 変数について詳しくは、[ここ](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/page-variables.html)をクリックしてください。

>[!IMPORTANT]
>
>Activity Map で s_objectID を使用する場合、末尾のセミコロン（;）は必須です。

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product 1 <p> </p> <p> </p> <p>Product 2 </p> <p> </p> <p> </p> <p>Product 3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> <p> </p> <p>recommendation パネル </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 領域のカスタマイズ {#section_6B1EF302573B445DBAF44176D0A12DB9}

&quot;Buy&quot; リンクごとに独自の領域を定義することにより、領域をカスタマイズできます。これを行うには、&quot;Buy&quot; アンカータグごとに、親の 1 つに &quot;id&quot; パラメーターを追加します。

>[!NOTE]
>
>領域 ID は、&quot;id&quot; パラメーターに厳密に制限されているわけではありません。JavaScript の変数 &quot;s.ActivityMap.regionIDAttribute&quot; を使用して独自の ID を設定することもできます。

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>

## AppMeasurement Activity Map モジュールファイルのカスタマイズ {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>必ず、変更したコードをテストして、適切に機能することを確認してください。変更後のコードの動作については、アドビでは一切責任を負いません。

AppMeasurement.js ファイルに（変更した形式で）含めることのできる **一般的な** リンク／領域関数の例を 2 つ示します。

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

