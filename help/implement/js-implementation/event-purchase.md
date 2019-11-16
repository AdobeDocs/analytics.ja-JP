---
description: 購入イベントでは、Analytics 変数を使用して特定の購入情報を取り込みます。s.purchaseID 変数を使用して、イベントをシリアル化（重複排除）します。
keywords: Analytics Implementation
solution: Analytics
title: 購入イベント
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 購入イベント

購入イベントでは、Analytics 変数を使用して特定の購入情報を取り込みます。`s.purchaseID` 変数を使用して、イベントをシリアル化（重複排除）します。

購入イベントを含むヒットが購入IDなしで渡された場合、Adobe Analyticsは、そのヒット（s.purchaseおよびs.events）の情報を使用して「一時的な購入ID」を作成します。 この一時的な購入IDは、ヒットの訪問者にのみ適用されます。 以前の5つの一時的な購入IDは、（レポートスイートごとに）各訪問者IDに対して保存されます。

訪問者が購入をおこなう際には、次のチェックが実施されます。

* は、 一時的な購入IDが、保存されている最近5つの一時的な購入IDのいずれかに一致するか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* が定義さ `s.purchaseID` れている場合、レポートスイートで既に収集されている値と一致しますか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。

サーバーサイドの特定のコードを使用して、HTML ソースに埋め込む一意の番号（英数字の値）を生成できます。通常は、注文 ID またはこれに類似した英数字の値が使用されます。ユーザーがページを更新する場合、この値を変更しないでください。

## 構文

```js
s.purchaseID="12345678";
```

## 例

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## 追加情報

* ページが読み込まれるたびに一意の数を生成する数値を生成する場合は、JavaScriptのランダム化関数を使用しないでください。 アドビでは、特定の購入IDを保存するためにデータレイヤーを使用することをお勧めします。
* 一意の識別子はすべてのセッションのすべてのユーザーに適用できます。すべての購入IDが完全に一意であることを確認します。
* 有効な値は、20文字以内の英数字の値です。
* `s.purchaseID``s.events` 変数は、  変数に渡されたすべてのイベントをシリアル化して、イベントのシリアル化値を上書きします。現在のページで変 [!UICONTROL 数が使用される場合は] 、イベントに対して `s.purchaseID` イベントシリアル化を使用しないでください。
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
