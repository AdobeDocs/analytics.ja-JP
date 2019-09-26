---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.currencyCode

 変数は、売上高に適用される換算レートを決定します。

すべての売上は、選択した通貨で保存されます。その通貨が  *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | cc | コンバージョン／購入／売上高 売上高または金額値を示すすべてのコンバージョンレポート | "USD" |

サイトで複数の通貨により購入できるようにしている場合は、*`currencyCode`* 変数を使用して、売上高を適切な通貨で保存する必要があります。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. データ収集がそのデータを受け取るとすぐに、その時点の換算レートを使用して、この 40 ユーロを USD に換算します。

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. アドビが使用するコンバージョン率ではなく、独自のコンバージョン率を使用する場合は、をレポートスイートのベ *`currencyCode`* ース通貨と同じに設定します。 その上で、すべての売上高を換算してから、[!DNL Analytics] に送信します。

通貨換算は、売上高と通貨イベントの両方に適用されます。通貨イベントとは、税金や送料など、売上高に類似した値を合計するために使用するイベントです。売上高および通貨イベントは、製品文字列内で指定します。products について詳しくは、 [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## 構文と可能な値

```js
s.currencyCode="currency_code"
```

## 例

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## 設定

Adobe [!DNL Customer Care] が、レポートスイートのデフォルトの通貨設定を変更いたします。レポートスイートのベース通貨を変更した場合、システム内の既存の売上高は変換されません。新しい売上高の値はすべて、新しい通貨設定に従って変換されます。

## 注意事項、質問、ヒント

* レポート内で非常に多額の売上高が表示される場合は、*`currencyCode`* 変数とレポートスイートのベース通貨が正しく設定されているかを確認してください。
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* 通貨イベントは、通貨以外の目的では使用しないでください。通貨ではない任意の値または動的な値をカウントする必要がある場合は、[!UICONTROL 数値]イベントタイプを使用してください。
* When the *`currencyCode`* 変数が空の場合は、換算は適用されません。

詳しくは、「通貨コード」を参 [照してください](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)。
