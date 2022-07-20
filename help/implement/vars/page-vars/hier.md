---
title: hier
description: Adobe Analytics に階層変数を実装します。
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 93%

---

# hier

階層変数は、サイトの構造を確認できるカスタム変数です。

>[!TIP]
>
> この変数は、以前のバージョンの Adobe Analytics ではより一般的に使用されていました。アドビでは、[eVar](evar.md) と分類の使用をお勧めします。

>[!IMPORTANT]
>
>階層は、Experience Edge に XDM を使用したデータ収集ではサポートされていません。

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
