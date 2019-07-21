---
description: コンテンツ階層の一般的な使用方法は、訪問者が特定のページ、レベルなどから辿った様々なパスを示すことです。
keywords: Analyticsの導入;content階層;hier
seo-description: コンテンツ階層の一般的な使用方法は、訪問者が特定のページ、レベルなどから辿った様々なパスを示すことです。
seo-title: コンテンツ階層のカウント
solution: Analytics
title: コンテンツ階層のカウント
topic: 開発者と導入
uuid: d41df92d-65fb-44de- ff46-8fac24303abc
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# コンテンツ階層のカウント

コンテンツ階層の一般的な使用方法は、訪問者が特定のページ、レベルなどから辿った様々なパスを示すことです。

**[!UICONTROL コンテンツ階層]はどのように追跡すればよいでしょうか。**

まず、[!UICONTROL コンテンツ階層]を追跡するためのレポート要件を理解する必要があります。階層を追跡するための要件が非常に細かい場合には、多くの場合、階層（*`hier`*) 変数を使用することをお勧めします。通常、階層には、同じ子ノードが複数の親ノードの下に位置することがほとんどない、厳密な事前定義された分類が必要です。以下の例について考えてみましょう。

[!UICONTROL グローバル階層]

すべてのサイト／地域／国／言語／カテゴリ

この例では、言語のレベルで階層の分類がおこなわれる場合があります。全体的な「英語」のトラフィックをレポートすることが要件である場合、「USA」、「イングランド」、「オーストラリア」などの下に「英語」があると問題になります。階層では下位のレベルに掘り下げていくことしかできません。複数の階層を横並びで分析する場合のベストプラクティスは、[!UICONTROL カスタムトラフィック変数]（prop）を使用することです。

ユーザーが（サイトを閲覧する方法と同じように）サイトを掘り下げて、階層の各レベルで[!UICONTROL 個別訪問者数]に関するレポートを表示できるようにする場合は、階層変数を使用することをお勧めします。

prop および *`hier`*&#x200B;の両方の変数を使用するのが効果的な場合もあります。以下に、各変数タイプでサポートされる prop を示します。

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> prop </th> 
   <th class="entry"> 階層 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> クロス集計 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> パス </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ページビュー </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 実訪問者数 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 分類 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

