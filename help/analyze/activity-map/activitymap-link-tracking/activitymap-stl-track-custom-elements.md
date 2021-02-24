---
title: Activity Mapでtl()メソッドを使用する
description: tl()メソッドを使用して、カスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。
topic: Activity Map
translation-type: tm+mt
source-git-commit: 65cb0a49ef74156f0b8adf4a11c6fec6394d306f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 43%

---


# Activity Mapに`tl()`メソッドを使用

`tl()` メソッドを使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。

## カスタム要素の追跡

[`tl()` メソッド](/help/implement/vars/functions/tl-method.md)を Activity Map AppMeasurement モジュールの一部として使用すると、アンカータグや画像要素以外のオブジェクトも含めて、クリックされたすべてのオブジェクトを追跡できます。`tl()`を使用すると、ページ読み込みに結びつかないカスタム要素を追跡できます。

`tl()` メソッドでは、現在離脱リンクやカスタムリンクなどを識別するために使用されている `linkName` パラメーターを使用して、Activity Map 変数のリンク ID を識別できるようになりました。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

つまり、`tl()`を使用してカスタム要素を追跡する場合、リンクIDは、`tl()`メソッドの3番目のパラメーター(Link name)として渡された値から取得されます。 Activity Map の[デフォルトの追跡](activitymap-link-tracking-methodology.md)に使用される標準のリンクトラッキングアルゴリズムから引き出されるのではありません。

## 動的コンテンツのオーバーレイレンダリング

`tl()`メソッドをHTML要素のオンクリックイベントから直接呼び出すと、Activity MapはWebページの読み込み時にその要素のオーバーレイを表示できます。 例：

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

動的コンテンツのリンクをオーバーレイするActivity Mapに最適な方法は、カスタマイズした`ActivityMap.link`関数を設定して、戻り値が`tl()`に渡されるのと同じ関数を呼び出すことです。 次に例を示します。

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

ここでは、`ActivityMap.link`関数をオーバーライドして、呼び出し時に次の3つの処理のいずれかを実行します。

1. `linkName`が渡された場合、`tl()`が呼び出したので、`tl()`が`linkName`として渡したものを返すだけです。
2. レポート時にActivity Mapが呼び出すと、`linkName`は渡されないので、`makeLinkName()`をリンク要素と共に呼び出します。 これはここでの重要なステップです。`makeLinkName(element)`呼び出しは、`<button>`タグ内の`tl()`呼び出しの3番目の引数と同じでなければなりません。 つまり、`tl()`が呼び出されると、`makeLinkName()`から返された文字列を追跡します。 Activity Mapがページ上のリンクに関するレポートを作成する場合、同じ呼び出しを使用してリンクが作成されます。
3. 最後の解決方法は、単にデフォルトの Activity Map link 関数の元の戻り値を返すというものです。この参照をデフォルトの場合に呼び出すまで保つと、`makeLinkName()`のカスタムコードを上書きまたは書き込むだけで済み、ページ上のすべてのリンクのリンク戻り値を考え出す必要がなくなります。
