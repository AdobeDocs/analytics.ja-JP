---
description: マーチャンダイジング変数でインスタンスをカウントする方法を説明します。
keywords: Analytics Implementation
title: マーチャンダイジング変数とインスタンス
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# マーチャンダイジング変数とインスタンス

マーチャンダイジング変数でインスタンスをカウントする方法を説明します。

インスタンスは、現在、マーチャンダイジング変数に対してはサポートされていません。 マーチャンダイジング変数を含むレポート内のインスタンスが見つかった場合、eVarが製品文字列の外側の一部の場所に設定されており、選択したマーチャンダイジング変数のインスタンスの実際の数と見なされないことを示します。

コンバージョン変数の構文を使用している場合、変数が設定されるたびにインスタンスがカウントされます。 ただし、変数が設定されるたびに次の処理が行われない限り、インスタンスは「なし」に関連付けられます。

* 連結イベントが設定される。
* products変数が設定されます。
* マーチャンダイジングeVarに値がある。

例えば、次のeVar1のインスタンスは「Outdoors:Ski Goggles」に割り当てられます。

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

ただし、次の例では、eVarが設定されるとき(バインディングイベントがなく、products変数が設定されていない場合)、すべての条件が満たされないので、eVar1のインスタンスが「なし」に割り当てられます。

訪問の1ページ目：

```js
s.eVar1="Outdoors:Ski Goggles"
```

訪問の2ページ目：

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

バインディングイベントが発生しないページのeVarに値を設定した場合、またはバインディングイベントがない商品文字列にeVar値を設定した場合、「なし」への配分が発生します。

>[!NOTE]マーチャンダイジング変数でのインスタンスのカウントに関する現在の機能は見直しが進められており、将来のリリースでの変更が予定されています。

