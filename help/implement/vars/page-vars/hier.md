---
title: hier
description: Adobe Analytics に階層変数を実装します。
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---


# hier

階層変数は、サイトの構造を確認できるカスタム変数です。

>[!TIP]
>
> この変数は、以前のバージョンの Adobe Analytics ではより一般的に使用されていました。アドビでは、[eVar](evar.md) と分類の使用をお勧めします。

この変数は、サイト構造に 3 つ以上のレベルを持つサイトの場合に有効です。例えば、メディアサイトにスポーツセクションへの 4 つのレベル（`Sports`、`Local Sports`、`Baseball` および `Team name`）があるとします。誰かが野球ページを訪問すると、スポーツ、ローカルスポーツおよび野球のすべてのレベルにその訪問が反映されます。

アドビでは、実装で最大 5 つの階層変数をサポートします。階層を有効化するときに、変数の区切り文字と、階層の最大レベル数を決定する必要があります。例えば、区切り文字がコンマの場合、階層は次のようになります。

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

セクション名には区切り文字を使用しないようにしてください。例えば、セクションの 1 つで `Coach Griffin, Jim` を呼び出す場合は、コンマ以外の区切り文字を選択します。変数の制限の合計は 255 バイトです。区切り文字は、`||` や `/|\` のように複数の文字で構成することもできます（複数の文字で構成すると、変数値で使用される可能性が低くなります）。

## 例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
