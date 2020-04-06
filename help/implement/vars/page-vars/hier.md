---
title: hier
description: Adobe Analytics に階層変数を実装します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# hier

階層変数は、サイトの構造を確認できるカスタム変数です。

>[!TIP] この変数は、以前のバージョンのAdobe Analyticsでより一般的でした。 eVarと分類の代わりに [使用す](evar.md) ることをお勧めします。

この変数は、サイト構造に3つ以上のレベルがあるサイトで役立ちます。 例えば、メディアサイトのスポーツセクションに対するレベルを4つ設定できます。 `Sports`、 `Local Sports`、、 `Baseball`および `Team name`。 誰かが野球ページ、スポーツ、ローカルスポーツ、野球の各ページを訪問した場合、すべてのレベルにその訪問が反映されます。

アドビでは、実装で最大5つの階層変数をサポートしています。 階層を有効にする際に、変数の区切り文字と階層の最大レベル数を決定します。 例えば、区切り文字がコンマの場合、階層は次のようになります。

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

区切り文字を含むセクション名がないことを確認します。 例えば、セクションの1つを呼び出す場合は、 `Coach Griffin, Jim`コンマ以外の区切り文字を選択します。 変数の制限の合計は255バイトです。 区切り文字は、やなど複数の文字で構成でき `||` ますが、 `/|\`変数値に表示される可能性は低くなります。

## 例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
