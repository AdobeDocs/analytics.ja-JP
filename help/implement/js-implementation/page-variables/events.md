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



# イベント

 変数は、一般的な買い物かご成功イベントやカスタム成功イベントを記録するために使用します。


<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
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
   <td> 無制限 </td> 
   <td> events </td> 
   <td> <p>買い物かごイベント </p> <p>カスタムイベント </p> </td> 
   <td> 該当なし </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL イベント]は、サイト内のマイルストーンと見なされます。成功イベントは、会員登録やニュースレターの購読など、プロセスの最終的な完了ページで設定されることが最も一般的です。カスタムイベントは、以下の可能な値で定義されているリテラル値を使用して events 変数を設定することで定義されます。

デフォルトでは、成功イベントは&#x200B;*カウンター*&#x200B;イベントとして設定されます。カウンターイベントは、成功イベントが設定された回数をカウントします（x+1）。また、イベントは&#x200B;*数値*&#x200B;イベントとしても設定できます。数値イベントを使用すると、数値の増分を指定できます（サイト内検索によって返される結果の数など、動的な値や任意の値をカウントする場合に必要となることがあります）。

*通貨*&#x200B;イベントタイプは、数値イベントと同様に追加する数量を定義するために使用できますが、レポート内では通貨として表示され、s.*`currencyCode`* の値およびレポートスイートのデフォルトの通貨設定に基づいて通貨換算が実行されます。数値イベントと通貨イベントの使用について詳しくは、「[製品](/help/implement/js-implementation/page-variables/page-variables.md)」を参照してください。

**変数の設定**

`s.events` 変数は、すべての導入に対してデフォルトで有効化されます。事前設定済みの 7 つのコンバージョンイベントは、新しいレポートスイートで自動的に有効化されます。新しいカスタムイベント（event1 ～  [event100 または event1000](/help/implement/js-implementation/page-variables/page-variables.md)）は、管理者レベルのユーザーが Admin Console を使用して有効にする必要があります。

**可能な値**

以下に、events 変数で使用できる値の一覧を示します。

| イベント | 説明 | 入力されるレポート |
|---|---|---|
| prodView | 商品ビュー | 製品 |
| scOpen | 新しい買い物かごを開くまたは初期化 | 買い物かご |
| scAdd | 買い物かごへの品目の追加 | 買い物かごへの追加 |
| scRemove | 買い物かごからの品目の削除 | 買い物かごからの削除 |
| scView | 買い物かごの表示 | 買い物かご表示 |
| scCheckout | チェックアウトプロセスの開始 | チェックアウト |
| purchase | 購入（注文）の完了 | 購入回数 |
| event1 ～ event1000（ポイント製品の場合は event100） | カスタムイベント | カスタムイベント |

**構文と例**

カウンターイベントを設定するには、`s.events` 変数に任意のイベントを配置します（複数のイベントを設定する場合はコンマ区切りのリストを使用します）。

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

H23 コード以降の場合、カウンターイベントには 1 より大きい整数を割り当てることができます。

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

整数値を割り当てたカウンターイベントを導入すると、そのイベントはイメージリクエスト内で複数回呼び出されたものとして扱われます。カウンターイベントでは小数は使用できません。小数の機能が必要な場合は、代わりに数値イベントを使用することをお勧めします。数値イベントと通貨イベントは、通常は [!UICONTROL s.products] 変数で数値（24.99 など）を受け取りますが、[!UICONTROL s.events] 変数に含める必要があります。こうすることで、特定の数値および通貨の値を個々の製品エントリに関連付けることができます。

**イベントのシリアル化**

デフォルトでは、サイトでイベントが設定されるたびにそのイベントがカウントされますが、重複判定による除外もできます。

「[イベントのシリアル化](/help/implement/js-implementation/event-serialization.md)」を参照してください。

**構文**

```js
s.events="event1:3167fhjkah"
```

**例**

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
