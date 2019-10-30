---
description: s.tl() 関数を使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。
seo-description: s.tl() 関数を使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。
seo-title: s.tl() 関数の使用
solution: Analytics
title: s.tl() 関数の使用
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# s.tl() 関数の使用

s.tl() 関数を使用してカスタム要素を追跡し、動的コンテンツのオーバーレイレンダリングを設定できます。

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

[s.tl() 関数](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html)を AppMeasurement モジュールの一部として使用すると、アンカータグや画像要素以外のオブジェクトも含めて、クリックされたすべてのオブジェクトを追跡できます。[!DNL Activity Map]s.tl を使用すると、ページ読み込みにつながらないカスタム要素を追跡できます。

s.tl 関数では、現行では離脱リンクやカスタムリンクなどを識別するために使用されている linkName パラメーターis now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

つまり、s.tl を使用してカスタム要素を追跡した場合、リンク ID は、s.tl 関数の 3 番目のパラメーター（linkName）として渡された値から引き出されます。It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element’s on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. 例：

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

最初のページ読み込み後に何らかの Web ページコンテンツが追加されるたびに、s.tl 関数は間接的に呼び出されるので、明示的に有効化またはクリックしない限りは、新しいコンテンツのオーバーレイは表示できません。Then a new link collection process is triggered from [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element’s on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. s.tl() 関数が間接的に呼び出される場合の例を以下に示します。

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. 次に例を示します。

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

ここで、呼び出された際に 3 つのうちのいずれかをおこなうために、ActivityMap.link 関数を上書きしました。

1. linkName が渡された場合、これは s.tl() によって呼び出され、s.tl が linkName として渡した値を返します。
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. これは、s.tl が呼び出される際に、makeLinkName によって返された文字列を追跡することを意味します。When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link.
1. 最後の解決方法は、単にデフォルトの Activity Map link 関数の元の戻り値を返すというものです。デフォルトの呼び出しに関するこの参照を維持することにより、上書きまたは makeLinkName のカスタムコードを記述するだけで済み、ページ上のすべてのリンクのリンク戻り値を見つけ出す必要がなくなります。
