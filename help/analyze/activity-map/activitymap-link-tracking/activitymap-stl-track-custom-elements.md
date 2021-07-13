---
title: tl()メソッドとActivity Map
description: tl()メソッドを使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 43%

---

# `tl()`メソッドとActivity Map

`tl()` メソッドを使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。

## カスタム要素の追跡

[`tl()` メソッド](/help/implement/vars/functions/tl-method.md)を Activity Map AppMeasurement モジュールの一部として使用すると、アンカータグや画像要素以外のオブジェクトも含めて、クリックされたすべてのオブジェクトを追跡できます。`tl()`を使用して、ページ読み込みにつながらないカスタム要素を追跡できます。

`tl()` メソッドでは、現在離脱リンクやカスタムリンクなどを識別するために使用されている `linkName` パラメーターを使用して、Activity Map 変数のリンク ID を識別できるようになりました。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

つまり、`tl()`を使用してカスタム要素を追跡した場合、リンクIDは、`tl()`メソッドの3番目のパラメーター（リンク名）として渡された値から引き出されます。 Activity Map の[デフォルトの追跡](activitymap-link-tracking-methodology.md)に使用される標準のリンクトラッキングアルゴリズムから引き出されるのではありません。

## 動的コンテンツのオーバーレイレンダリング

`tl()`メソッドをHTML要素のオンクリックイベントから直接呼び出すと、Webページの読み込み時に、Activity Mapでその要素のオーバーレイを表示できます。 例：

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

最初のページ読み込み後に何らかの Web ページコンテンツが追加されるたびに、`tl()` メソッドは間接的に呼び出されるので、明示的に有効化またはクリックしない限りは、新しいコンテンツのオーバーレイは表示できません。その後、Activity Map から新しいリンク収集プロセスがトリガーされます。

`tl()` メソッドが HTML 要素のオンクリックイベントから直接呼び出されていない場合、Activity Map では、ユーザーが要素をクリックした場合にのみオーバーレイを表示できます。`tl()` 関数が間接的に呼び出される場合の例を以下に示します。

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Activity Mapが動的コンテンツリンクをオーバーレイする最善の方法は、カスタマイズした`ActivityMap.link`関数を設定して、戻り値が`tl()`に渡される同じ関数を呼び出すことです。 次に例を示します。

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

ここでは、`ActivityMap.link`関数を上書きして、呼び出されたときに3つの処理のいずれかを実行します。

1. `linkName`が渡された場合は、`tl()`が呼び出したので、`tl()`が`linkName`として渡した値を返すだけです。
2. レポート時にActivity Mapから呼び出されると、`linkName`は渡されないので、リンク要素を使用して`makeLinkName()`を呼び出します。 これは、ここでの重要なステップです。`makeLinkName(element)`呼び出しは、`<button>`タグ内の`tl()`呼び出しの3番目の引数と同じである必要があります。 つまり、`tl()`が呼び出されると、`makeLinkName()`から返された文字列を追跡します。 Activity Mapがページ上のリンクを報告する場合、同じ呼び出しを使用してリンクを作成します。
3. 最後の解決方法は、単にデフォルトの Activity Map link 関数の元の戻り値を返すというものです。この参照をデフォルトのケースで呼び出すまでに保つと、`makeLinkName()`のカスタムコードを上書きまたは書き込むだけで済み、ページ上のすべてのリンクのリンク戻り値を生成する必要がなくなります。
