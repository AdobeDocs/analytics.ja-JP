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



# リスト prop

リスト prop は、変数に渡され、レポートの個別行項目としてレポートされる値の区切りリストです。リスト prop は、一般的に、チェックボックスやラジオボタンのリスト項目などの、ユーザーが複数選択できる項目を計測するために導入されます。リスト prop は、複数のイメージリクエストを送信せずに 1 つの変数で複数の値を定義する場合に役立ちます。


<!-- 

list_props.xml

 -->

**注意点**

* リスト prop はトラフィック変数（[prop](/help/implement/js-implementation/page-variables/propn.md)）のオプションです。
* パスおよびクロス集計は、リスト prop では有効にできません。
* リスト prop レポートを含む、ほとんどすべてのレポートに訪問数および個別訪問者数を追加できます。
* リスト prop では分類がサポートされています。
* カスタムトラフィック変数はどれもリスト props として使用できます（例外：[pageName](/help/implement/js-implementation/page-variables/pagename.md)、[channel](/help/implement/js-implementation/page-variables/channel.md)、および [server](/help/implement/js-implementation/page-variables/server.md)）

* 同じイメージリクエストに重複した値が定義される場合、インスタンスの重複は除外されません。

prop は、管理ツール／レポートスイート／トラフィック変数ページでリストのサポートを有効にして、区切り文字を選択することで、リスト prop に変更できます。一般的な区切り文字はコロン、セミコロン、コンマ、またはパイプです。技術的には、ASCII 文字の最初の 127 文字のいずれもでも可能です。

**実装例**

リスト prop の有効化をリクエストする場合、使用する区切りを指定します。希望する *`s.prop`* が有効にされると、次の例に示されるように、変数に複数の値を設定できます。

パイプで区切られたリスト prop で、2 つの値を受け渡す：

```js
s.prop1="Banner ad impression|Sidebar impression"
```

コンマで区切られたリスト prop で、複数の値を受け渡す：

```js
s.prop2="cerulean,vermilion,saffron"
```

リスト prop では 1 つの値を受け渡すことも可能：

```js
s.prop3="Single value"
```

区切りはいつでも変更できます。ただし、実装では新しい区切りと一致する必要があります。正しい区切りを使わなかった場合、リスト prop の値は連結された単一の行項目としてレポートで扱われます。

リスト prop はトラフィック変数でもあるので、トラフィック変数の制限を受けることにもなります。リスト prop のデータは 100 バイトに制限され、大文字と小文字の区別に関する設定の影響を受けます。

