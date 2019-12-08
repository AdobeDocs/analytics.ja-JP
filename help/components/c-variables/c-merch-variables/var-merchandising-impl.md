---
description: マーチャンダイジング変数を有効にして実装する方法を説明します。
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
title: マーチャンダイジング変数の実装
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# マーチャンダイジング変数の実装

マーチャンダイジング変数を有効にして実装する方法を説明します。

## マーチャンダイジング変数の有効化

マーチャンダイジングは、**[!UICONTROL 管理ツール]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL コンバージョン変数]**&#x200B;で、任意のカスタム eVar に対して有効にできます。

![](assets/merch-enable.png)

| 設定 | 説明 |
|--- |--- |
| 有効期限 | マーチャンダイジング値が有効である期間を指定します。 |
| マーチャンダイジング | **製品の構文**：`s.products` 内で設定されている値。<br>**コンバージョン変数の構文：**&#x200B;指定されたマーチャンダイジング eVar で設定された値。 |
| マーチャンダイジングバインディングイベント（コンバージョン変数の構文のみ） | 製品を現在のマーチャンダイジングカテゴリーに結び付けるときのイベントを示します。Ctrl キーを押しながらリストの複数の項目をクリックすることで、複数のイベントを選択できます。イベントを選択できるのは、「コンバージョン変数の構文」が選択されている場合のみです。 |

## 製品の構文を使用した導入

「製品の構文」が選択されている場合、マーチャンダイジングカテゴリーが products 変数に直接入力されるので、バインディングイベントを選択して設定する必要はありません。これが推奨される方法であり、成功イベントが発生したときにその値を `s.products` に設定できない場合を除いて、この方法を使用してください。

### 構文

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### 例

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

eVar1 の値「ゴーグル」が製品「スノーゴーグル」に割り当てられます。この製品に関連して以降に発生するすべての成功イベント（製品の追加、チェックアウト、購入など）のクレジットは「ゴーグル」に付与されます。

## コンバージョン変数の構文を使用した導入

eVar 変数を `s.products` に設定できない場合、コンバージョン変数の構文を使用する必要があります。一般的には、ページにマーチャンダイジングチャネルや検索方法のコンテキストがない場合です。そのような場合、製品ページに到達する前にマーチャンダイジング変数を設定し、その値がバインディングイベントの発生時まで保持されるようにする必要があります。

設定時にバインディングイベントが選択されると、保持された eVar の値が製品に関連付けられます。例えば、バインディングイベントとして prodView が指定されている場合、イベントの発生時にのみ現在の製品リストにマーチャンダイジングカテゴリーが結び付けられます。既に製品に割り当てられているマーチャンダイジング eVar を更新できるのは、以降のバインディングイベントのみです。

### 構文

バインディングイベントの前の同じページまたは直前のページに配置：

```js
s.eVar1="merchandising_category";
```

バインディングイベントが発生するページに配置：

```js
s.events="prodView";
s.products="category;product";
```

### 例

その訪問の 1 ページ目：

```js
s.eVar1="Outdoors"
```

その訪問の 2 ページ目：

```js
s.events="prodView";
s.products=";Snow Goggles";
```

eVar1 の値「アウトドア」が製品「スノーゴーグル」に割り当てられます。この製品に関連して以降に発生するすべての成功イベント（製品の追加、チェックアウト、購入など）のクレジットは「スノーゴーグル」に付与されます。さらに、以下のどちらかの条件が満たされるまで、マーチャンダイジング変数の現在の値が以後のすべての製品に結び付けられます。

* eVar の期限が切れる（「有効期限」の設定に基づきます）。
* マーチャンダイジング eVar が新しい値で上書きされる。

## 外部追加情報

[!DNL analyticsdemystified.com] の[高度なコンバージョン構文マーチャンダイジング](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/)
