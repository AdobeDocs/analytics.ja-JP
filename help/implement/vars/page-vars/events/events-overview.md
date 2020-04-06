---
title: events
description: イベント変数を設定します。この変数は、サイト上のほとんどの指標を制御します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# events

ディメンションと指標は、レポートにとって重要な要素です。`events` 変数は、サイト上の多くの指標のデータ収集をおこないます。

## Adobe Experience Platform Launch のイベント

イベントは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Events] section.

次の機能が利用できます。

* ドロップダウンで、含めるイベントを選択できます。
* シリアル化用のオプションのテキストフィールドです。[イベントのシリアル化](event-serialization.md)を参照してください。
* イベント値のオプションのテキストフィールドです。通貨イベントには通貨を、通貨イベント以外のイベントには整数を含めて、通貨イベントを複数回増やすことができます。例えば、ドロップダウンで `event1` を選択し、このフィールドに `10` を含めると、レポートでは `event1` が 10 ずつ増えます。
* 別のイベントを追加するボタン。ヒットに含めることのできるイベント数には、妥当な制限はありません。

## AppMeasurement および Launch カスタムコードエディターの s.events

`s.events` 変数は、ヒットに含めるイベントのコンマ区切りリストを含む文字列です。この変数にはバイト制限がないので、切り捨てられません。有効な設定値は以下のとおりです。

* `event1`～`event1000`：カスタムイベントを設定します。組織の[ソリューションデザインドキュメント](../../../prepare/solution-design.md)に各イベントの使用方法を記録します。使用可能なイベントの数は、組織の Analytics 契約によって異なります。レガシー契約以外の組織のほとんどは、1,000 件のカスタムイベントを利用できます。利用可能なカスタムイベントの数が不明な場合は、貴社のアカウントマネージャーにお問い合わせください。
* `purchase`:「注文件数」指標を 1 増分し、`products` 変数に設定された値を使用して「数量」と「売上高」を計算します。詳しくは、[購入イベント](event-purchase.md)を参照してください。
* `prodView`：「製品表示回数」指標を増分します。
* `scOpen`：「買い物かご」指標を増分します。
* `scAdd`：「買い物かごへの追加件数」指標を増分します。
* `scRemove`：「買い物かごからの削除件数」指標を増分します。
* `scView`：「買い物かご表示回数」指標を増分します。
* `scCheckout`：「チェックアウト数」指標を増分します。

>[!NOTE] この変数では大文字と小文字が区別されます。正確なデータ収集を確実におこなうために、イベント値の誤った大文字化を避けます。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### カウンターイベントを複数回増分します

必要に応じて、カスタムイベントを複数回カウントできます。文字列内の目的のイベントに整数を割り当てます。レポートスイート設定で作成されたイベントは、デフォルトでカウンターイベントです。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE] カウンターイベントは、通貨や小数値をサポートしません。通貨イベントは通貨に、数値イベントは小数値に使用します。

### 通貨イベントの使用

カスタムイベントを変更して、整数の代わりに通貨を使用することができます。通貨イベントは、レポートスイートの通貨と `currencyCode` 変数が一致しない場合、レポートスイートの通貨に自動的に変換されます。配送費、割引、返金の計算に役立ちます。イベントをその製品のみに属性設定する場合は、`products` 変数に通貨イベントを設定できます。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE] `events` 変数と `products` 変数の両方に通貨値を設定した場合、`events` での通貨値が使用されます。`events` 変数と `products` 変数の両方で通貨値を設定しないでください。

### 数値イベントの使用

整数の代わりに小数値を受け入れるカスタムイベントを変更できます。数値イベントは通貨イベントと同様に動作しますが、通貨コンバージョンを使用しない点が異なります。イベントをその製品のみに属性設定する場合は、`products` 変数に数値イベントを設定できます。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE] `events` 変数と `products` 変数の両方に数値を設定した場合は、`events` の数値が使用されます。`events` 変数と `products` 変数の両方に数値を設定しないでください。
