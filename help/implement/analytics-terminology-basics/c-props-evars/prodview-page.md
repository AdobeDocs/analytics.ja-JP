---
description: products 変数は、製品と製品カテゴリ（および購入数量と購入価格）を追跡するために使用します。
keywords: Analyticsの導入;products変数;製品表示;successイベント
seo-description: products 変数は、製品と製品カテゴリ（および購入数量と購入価格）を追跡するために使用します。
seo-title: 製品表示ページの詳細
solution: Analytics
title: 製品表示ページの詳細
topic: 開発者と導入
uuid: 464c9daf- b042-4fb8-8ca6- e104c0bexton45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 製品表示ページの詳細

products 変数は、製品と製品カテゴリ（および購入数量と購入価格）を追跡するために使用します。

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. 両方のイベントを使用して、他のコンバージョンレポート内にある他の指標と共に、製品表示指標を表示できます。

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>products文字列構文はセミコロンで始まる必要があります。これは、従来の構文上の要件です。セミコロンは以前に、カテゴリと製品を区切るために使用されていましたが、製品の分類方法を変更したい場合に、それがインターフェイス内での制限となります。レポートにおける柔軟性を最大限に高めるには、これを空のままにして、「分類」を使用してカテゴリを設定することが最善策です。

## Shopping Cart Page ( scOpen , scAdd , scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## 最初のチェックアウトページ {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## 確認ページ {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. 完了、製造元、カテゴリおよびサブカテゴリを示すカテゴリを SKU から作成できます。

"*`products`* 変数が *`purchase`* イベントと組み合わせて設定されている場合、上記のように購入数量と購入総額がproducts値に含まれます。
