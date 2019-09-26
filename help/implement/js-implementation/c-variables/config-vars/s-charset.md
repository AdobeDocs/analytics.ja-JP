---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

The charSet property, which is normally set in the JavaScript file, is used by Analytics to convert incoming data into UTF-8 for storage and reporting by Analytics.

>[!N] 注意：charSetプロパティは、データをマルチバイトのレポートスイートに送信する場合に必要です。標準のレポートスイートでは絶対に使用しないでください。 charSet プロパティを標準の ISO レポートスイートに設定すると、変数の切り捨てや予想外の文字変換が発生することがあります。

charSet プロパティの値は、たとえ構文がわずかに異なっていたとしても、META タグまたは http ヘッダーでの Web ページエンコーディングに一致する必要があります。META タグはエンコーディングにエイリアスを使用できますが、charSet の値は通称（または公式）のエンコーディング名を使用する必要があります。

次の表は、よく使用されるエンコーディングのいくつかをその通称とエイリアスで一覧表示したものです。

| 通称 | エイリアス |
|--- |--- |
| ISO-8859-1 | ISO_8859-1、CP819、latin1 |
| ISO-8859-2 | ISO_8859-2、latin2 |
| ISO-8859-5 | ISO_8859-5、cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

エンコーディングやエイリアスが多数存在するので、charSetが上の表に表示されない場合は、導入コンサルタントまたはアドビカスタマーケアに問い合わせて、適切な値を確認してください。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

charSet パラメーターの空白でない値により、データは UTF-8 に変換されて保存されます。128～255 の範囲の文字は、適切な UTF-8 の 2 バイトシーケンスに変換されて保存されます。これらの文字は標準レポートスイートでは正しく表示されません。したがって、charSet プロパティは標準レポートスイートには絶対に使用しないでください。

同様に、charSet パラメーターの空白の値はデータ変換プロセスがスキップされ、128～255 の範囲の文字は 1 バイトとして保存されます。これらの文字の 1 バイトコードは有効な UTF-8 ではないので、これらの文字はマルチバイトレポートスイートでは正しく表示されません。したがって、charSet パラメーターは必ずマルチバイトレポートスイートで使用する必要があります。また、Web ページのエンコーディングに関しては適切な値を使用することが必要です。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

## パラメーター

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | CE | 該当なし | "" |

## 構文と可能な値

```js
s.charSet="character_set"
```

## 例

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
