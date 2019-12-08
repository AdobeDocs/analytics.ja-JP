---
description: products 変数は、製品と製品カテゴリ（および購入数量と購入価格）を追跡するために使用します。
keywords: Analytics Implementation;products variable;product view;success event
title: 詳細製品表示ページ
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 詳細製品表示ページ

products 変数は、製品と製品カテゴリ（および購入数量と購入価格）を追跡するために使用します。

成功イベントは、常に *`products`* と一緒に設定する必要があります。

```js
s.events="prodView"
```

> [!NOTE]*`prodView`* は実装ではイベントのように扱われますが、インターフェイスではイベントと同様の柔軟性はありません。`prodView` イベントは製品のインスタンスであり、*`products`* でのみ利用できます。アドビでは、*`prodView`* イベントに加えて、*`custom`* イベントも使用することをお勧めします。両方のイベントを使用して、他のコンバージョンレポート内にある他の指標と共に、製品表示指標を表示できます。

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE]製品文字列の構文はセミコロンで始める必要があります。これは、従来の構文上の要件です。セミコロンは以前に、カテゴリと製品を区切るために使用されていましたが、製品の分類方法を変更したい場合に、それがインターフェイス内での制限となります。レポートにおける柔軟性を最大限に高めるには、これを空のままにして、「分類」を使用してカテゴリを設定することが最善策です。

## 買い物かごページ（scOpen、scAdd、scRemove）{#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## 最初のチェックアウトページ {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## 確認ページ {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE]製品文字列で SKU を使用すると、*`products`* レポートが読みにくくなる場合がありますが、後で製品を分類する際の柔軟性が最大限に高まります。完了、製造元、カテゴリおよびサブカテゴリを示すカテゴリを SKU から作成できます。

When *`products`* 変数を&#x200B;*`purchase`* イベントと組み合わせて設定した場合、上記のように、購入数量と合計購入価格が products の値に含まれます。
