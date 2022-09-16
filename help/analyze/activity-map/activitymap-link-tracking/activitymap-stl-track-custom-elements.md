---
title: tl() メソッドとActivity Map
description: tl() メソッドを使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 43%

---

# 以下を使用： `tl()` Activity Map法

`tl()` メソッドを使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。

## カスタム要素の追跡

[`tl()` メソッド](/help/implement/vars/functions/tl-method.md)を Activity Map AppMeasurement モジュールの一部として使用すると、アンカータグや画像要素以外のオブジェクトも含めて、クリックされたすべてのオブジェクトを追跡できます。使用 `tl()`を使用すると、ページ読み込みにつながらないカスタム要素を追跡できます。

`tl()` メソッドでは、現在離脱リンクやカスタムリンクなどを識別するために使用されている `linkName` パラメーターを使用して、Activity Map 変数のリンク ID を識別できるようになりました。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

つまり、 `tl()` カスタム要素を追跡するために、リンク ID が、 `tl()` メソッド。 Activity Map の[デフォルトの追跡](activitymap-link-tracking-methodology.md)に使用される標準のリンクトラッキングアルゴリズムから引き出されるのではありません。

## 動的コンテンツのオーバーレイレンダリング

次の場合に `tl()` メソッドは、HTML要素のオンクリックイベントから直接呼び出されます。Activity Mapは、web ページの読み込み時に、その要素のオーバーレイを表示できます。 例：

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

Activity Mapが動的コンテンツのリンクをオーバーレイする最善の方法は、 `ActivityMap.link` 関数が設定され、戻り値が `tl()`. 次に例を示します。

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

ここでは、 `ActivityMap.link` 関数は、を呼び出したときに次の 3 つのいずれかを実行します。

1. If `linkName` が渡された場合、これは `tl()`ですので、 `tl()` ～として渡される `linkName`.
2. レポート時にActivity Mapによって呼び出された場合、 `linkName` は渡されないので、呼び出しは行われます。 `makeLinkName()` をリンク要素に置き換えます。 これは、ここでの重要なステップです — `makeLinkName(element)` 呼び出しは、 `tl()` 内での第 3 の議論 `<button>` タグを使用します。 つまり、 `tl()` が呼び出された場合、 `makeLinkName()`. Activity Mapがページ上のリンクに関するレポートを作成する場合、同じ呼び出しを使用してリンクを作成します。
3. 最後の解決方法は、単にデフォルトの Activity Map link 関数の元の戻り値を返すというものです。デフォルトでは、を呼び出すためにこの参照を保持すると、のカスタムコードを上書きまたは書き込むだけで済みます。 `makeLinkName()` ページ上のすべてのリンクに対してリンク戻り値を生成する必要はありません。
