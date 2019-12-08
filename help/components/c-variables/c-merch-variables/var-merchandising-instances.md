---
description: マーチャンダイジング変数でインスタンスをカウントする方法を説明します。
keywords: Analytics Implementation
title: マーチャンダイジング変数とインスタンス
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# マーチャンダイジング変数とインスタンス

マーチャンダイジング変数でインスタンスをカウントする方法を説明します。

インスタンスは、マーチャンダイジング変数では、現在サポートされていません。マーチャンダイジング変数を含むレポートにインスタンスがあることに気づいた場合、製品文字列の外部のある場所に eVar が設定されていることを示しており、選択したマーチャンダイジング変数のインスタンスを正しくカウントしていると考えるべきではありません。

コンバージョン変数の構文を使用している場合、変数が設定されるたびにインスタンスがカウントされます。ただし、変数が設定されるときに以下の条件が満たされなければ、インスタンスは「なし」に割り当てられます。

* バインディングイベントが設定される。
* products 変数が設定される。
* マーチャンダイジング eVar に値がある。

例えば、以下の eVar1 インスタンスは「Outdoors:Ski Goggles」に割り当てられます。

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

ただし、次の例では、eVar が設定されるときに一部の条件が満たされていないため（バインディングイベントがなく、products 変数が設定されていません）、eVar インスタンスは「なし」に割り当てられます。

その訪問の 1 ページ目

```js
s.eVar1="Outdoors:Ski Goggles"
```

その訪問の 2 ページ目

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

バインディングイベントが発生しないページで eVar の値を設定する場合、またはバインディングイベントがない products 文字列に eVar 値を設定する場合、「なし」への割り当てが発生します。

> [!NOTE]マーチャンダイジング変数でのインスタンスのカウントに関する現在の機能は見直しが進められており、将来のリリースでの変更が予定されています。

