---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# products

 変数は、製品と製品カテゴリ、および購入数量と購入価格を追跡するために使用します。一般に、products は、買い物かごイベントや イベントと共に設定されます。


<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>2016 年 1 月、*`prodView`* イベントを自動的に設定するロジックを変更しました（*`product`* があって *`event`* がない場合に発生します）。この更新により、*`prodView`イベントが増加することがあります。**`prodViews`* は、次の場合にのみ増加します。
>
>1. イベント変数に、*`shoppingCart`* や *`cart`* などの認識されていないイベントのみが含まれる（これらは有効なイベントではありません）。
   >
   >
1. *`products`* 変数が空ではない。
>
>
考えられる副作用として、*`prodView`* イベントによってトリガーされるマーチャンダイジング eVar は、空の *`product`* と関連付けられることがありますが、これは、*`product list`* に無効な product のみが含まれる（product がリストされていないセミコロンなど）場合にのみ発生します。

*`products`* 変数は、サイトでユーザーが製品に対してどのような操作をするかを追跡します。例えば、products 変数を使用して、製品の表示、買い物かごへの追加、チェックアウトおよび購入の各回数を追跡できます。サイトでのマーチャンダイジングカテゴリの相対的効果を追跡することもできます。products 変数を使用する場合は、次のようなシナリオが一般的です。

Folio Builder *`products`* 変数は、必ず成功イベントと組み合わせて設定する必要があります。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>「<span class="wintitle">products</span>」文字列の最大サイズは 64k です。 </p> </td> 
   <td> products </td> 
   <td> 製品 <p>カテゴリ（オプション） </p> <p>売上高（オプション） </p> <p>購入点数（オプション） </p> <p>カスタムイベント（オプション） </p> <p>eVar（オプション） </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**構文**

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| フィールド | 定義 |
|---|---|
| カテゴリ | 関連付けられている製品カテゴリを含みます。バージョン 15 では、products を複数のカテゴリに関連付けることができるようになり、バージョン 14 に存在した制限を修正しています。これまでに製品カテゴリを記録していなかった場合、これからは、バージョン 15 のレポートスイート用に、このフィールドに値を設定してください。 |
| 製品      | （必須）製品を追跡するために使用される識別子。この識別子は、製品レポートのデータを設定するために使用されます。チェックアウトプロセス全体で同じ識別子を必ず使用してください。 |
| Quantity | 購入した数量。このフィールドは、記録される購入イベントと共に設定する必要があります。 |
| Price | 個々の価格ではなく、購入総量の連結コスト（数量 x 単価）を表します。このフィールドは、記録される購入イベントと共に設定する必要があります。 |
| イベント | 指定された製品に関連付けられる通貨イベント。詳しくは、[製品固有の通貨イベント](https://helpx.adobe.com/analytics/kb/comparing-event-types.html)および[注文全体にわたる通貨イベント](https://helpx.adobe.com/analytics/kb/comparing-event-types.html)を参照してください。 |
| eVar | 特定の製品に関連付けられるマーチャンダイジング eVar 値[マーチャンダイジング変数](/help/components/c-variables/c-merch-variables/var-merchandising.md)を参照してください。 |

変数に含まれる値は、 *`products`* 記録するイベントのタイプに基づきます。 Category を省略するときは、プレースホルダーとしてカテゴリと製品の区切り文字（;）が必要です。含めるパラメーターを区別する必要がある場合に限り、他の区切り文字が必要です。

**購入以外のイベントによる products 変数の設定**

*`products`* 変数は、成功イベントと組み合わせて設定する必要があります。

**購入イベントによる products 変数の設定**

*`purchase`* イベントは、注文プロセスの最終確認（「ご購入ありがとうございました」）ページに設定する必要があります。製品名、カテゴリ、数量および価格はすべて  *`products`* 変数にも取り込まれます。*`purchaseID`* 変数は必須ではありませんが、注文の重複を防ぐために設定することを強く推奨します。

**製品固有／通貨イベント**

通貨イベントがイベント変数ではなく *`products`* 変数内の値を受け取った場合は、その値にのみ適用されます。これは、製品固有の割引額や送料などの値を追跡するのに役立ちます。例えば、製品送料を追跡するように event1 を設定した場合、送料が「4.50」の製品は、次のように表示されます。

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

この例では、値 4.50 は、製品「Running Shoes」に直接関連付けられます。event1 を製品レポートに追加すると、「4.50」は、行項目「Running Shoes」に表示されます。Price と同様、この値は表示される数量の合計を反映する必要があります。2 つの製品があり、それぞれの送料が 4.50 の場合、event1 は「9.00」になる必要があります。

**注文全体にわたる通貨イベント**

通貨イベントが *`products`* 変数ではなくイベントリストの値を受け取った場合、その通貨イベントは *`products`* 変数内のすべての製品に適用されます。これは、個別の製品に対してセットする価格に影響を与えることなく、または製品リスト内の製品価格を別に追跡することによって、注文全体にわたる割引額や送料などの値を追跡するのに役立ちます。

例えば、event10 に注文全体にわたる割引額を設定した場合、10 ％割引のある購入は以下のようになります。

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

通貨イベントのレポートでのレポートの合計は、重複を排除したイベントの合計（この例では、レポート期間中の割引の総量）を表し、各製品に対するイベントの値の合計ではありません。例えば、「Running Shoes」と「Running Socks」の両方に「9.95」と表示され、合計も「9.95」になります。

> [!NOTE]同じ数値／通貨イベントの値が *`products`* 変数と *`events`* 変数で指定されている場合、*`events`* の値が使用されます。

**注意事項、質問、ヒント**

* *`products`* 変数は、必ず成功イベント（複数可）と組み合わせて設定する必要があります。成功イベントが指定されない場合、デフォルトのイベントは prodView になります。

* 製品名およびカテゴリ名を products 変数に入力する前に、これらの名前からコンマとセミコロンをすべて取り除きます。
* HTML 文字（登録商標記号、商標など）をすべて取り除きます。
* 価格から通貨記号を取り除きます。

**例**

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

