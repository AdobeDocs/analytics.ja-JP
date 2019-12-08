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


# channel

 変数は、サイトのセクションを特定するためにもっともよく使用されます。


<!-- 

channel.xml

 -->

例えば、EC サイトなら、エレクトロニクス、玩具、アパレルなどのセクションが考えられます。メディアサイトなら、ニュース、スポーツ、ビジネスなどのセクションが考えられます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | ch | サイトコンテンツ／サイトセクション | "" |

すべてのページで channel 変数を設定することをお勧めします。また、*`channel`* 変数と[!UICONTROL ページ名]変数の間でクロス集計を有効にすることもできます。

セクションに 1 つ以上のサブセクションがある場合、それらのセクションを *`channel`* 変数に表示したり、別の変数を使用して当該レベルを特定したりできます。

**構文と可能な値**

```js
s.channel="value"
```

*`channel`* 変数の値には特別な制限はありません。

**例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**注意事項、質問、ヒント** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

サイトに複数のレベルが含まれている場合は、*`hierarchy`* または他の変数を使用してそれらのレベルを指定します。*`channel`* の値は永続的ではありませんが、同じページで発生した成功イベントは、*`channel`* 値に関連付けられます。
