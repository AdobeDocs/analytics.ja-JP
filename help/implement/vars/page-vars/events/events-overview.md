---
title: events
description: イベント変数を設定します。この変数は、サイト上のほとんどの指標を制御します。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# events

ディメンションと指標は、レポートにとって重要な要素です。 この変 `events` 数は、サイト上の多くの指標のデータ収集を行います。

## Adobe Experience Platform Launchのイベント

イベントは、Analytics拡張の設定時（グローバル変数）またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. [イベント  ]セクションを見つけます。

次の機能が利用できます。

* ドロップダウンで、含めるイベントを選択できます
* シリアル化用のオプションのテキストフィールドです。 See [event serialization](event-serialization.md) for more information.
* イベント値のオプションのテキストフィールドです。 通貨イベントには通貨を、通貨イベント以外のイベントには整数を含めて、通貨イベントを複数回増やすことができます。 例えば、ドロップダウ `event1` ンの下で選択し、このフィールドに `10` 含めると、レポートでは10 `event1` ずつ増えます。
* 別のイベントを追加するボタン。 ヒットに含めることのできるイベント数には、妥当な制限はありません。

## AppMeasurementのs.eventsとカスタムコードエディターの起動

変数 `s.events` は、ヒットに含めるイベントのコンマ区切りリストを含む文字列です。 この変数にはバイト制限がないので、切り捨てられません。 有効な設定値は以下のとおりです。

* `event1` - `event1000`:カスタムイベントを設定します。 組織のソリューションデザインドキュメントでの各イベントの使 [用方法を記録します](../../../prepare/solution-design.md)。 使用可能なイベントの数は、組織のAnalytics契約によって異なります。 レガシー契約以外の組織のほとんどは、1,000件のカスタムイベントを利用できます。 利用可能なカスタムイベントの数が不明な場合は、貴社のアカウントマネージャーにお問い合わせください。
* `purchase`:「注文件数」指標を1増分し、変数に設定された値を使用 `products` して「数量」と「売上高」を計算します。 詳しくは [、purchaseイベント](event-purchase.md) を参照してください。
* `prodView`:「製品表示回数」指標を増分します。
* `scOpen`:「買い物かご」指標を増分します。
* `scAdd`:「買い物かごへの追加件数」指標を増分します。
* `scRemove`:「買い物かごからの削除件数」指標を増分します。
* `scView`:「買い物かご表示回数」指標を増分します。
* `scCheckout`:「チェックアウト数」指標を増分します。

> [!TIP] この変数では大文字と小文字が区別されます。 正確なデータ収集を確実に行うために、イベント値の誤った大文字化を避けます。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### カウンターイベントを複数回増分する

必要に応じて、カスタムイベントを複数回カウントできます。 文字列内の目的のイベントに整数を割り当てます。 レポートスイート設定で作成されたイベントは、デフォルトでカウンターイベントです。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] カウンターイベントは、通貨または10進数値をサポートしません。 通貨イベントは通貨に、数値イベントは小数値に使用します。

### 通貨イベントの使用

カスタムイベントを変更して、整数の代わりに通貨を使用することができます。 通貨イベントは、レポートスイートの通貨と変数が一致しない場合、レポートスイートの通貨に自 `currencyCode` 動的に変換されます。 配送費、割引、返金の計算に役立ちます。 イベントをその製品のみに属性 `products` 設定する場合は、変数に通貨イベントを設定できます。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] 変数と変数の両方に通貨値を設定 `events` した場合、 `products` での通貨値が使用さ `events` れます。 変数と変数の両方で通貨値を設定しな `events` いでく `products` ださい。

### 数値イベントの使用

整数の代わりに10進数値を受け入れるカスタムイベントを変更できます。 数値イベントは通貨イベントと同様に動作しますが、通貨コンバージョンを使用しない点が異なります。 イベントをその製品のみに属 `products` 性設定する場合は、変数に数値イベントを設定できます。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] 変数と変数の両方に数値を設 `events` 定した場 `products` 合は、の数値が使用さ `events` れます。 変数と変数の両方に数値を設定しな `events` いでく `products` ださい。
