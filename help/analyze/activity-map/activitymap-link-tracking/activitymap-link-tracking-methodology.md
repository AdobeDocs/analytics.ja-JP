---
description: このセクションは Adobe Analytics 管理者を対象としています。新しいリンクトラッキングパラメーターについて説明し、それによって異なるブラウザー間、デバイス間でのリンクの一意性と一貫性を確保し、ページ上でのリンクの再配置の処理を向上する方法を示します。
title: リンクトラッキング手法
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 95%

---

# リンクトラッキング手法

このセクションは Adobe Analytics 管理者を対象としています。新しいリンクトラッキングパラメーターについて説明し、それによって異なるブラウザー間、デバイス間でのリンクの一意性と一貫性を確保し、ページ上でのリンクの再配置の処理を向上する方法を示します。

>[!IMPORTANT]
>
>テキスト（href 以外）に PII（Personally Identifiable Information：個人を特定できる情報）が含まれている可能性のあるリンクは、[s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=ja) を使用して明示的に実装するか、[s.ActivityMap.linkExclusions または s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars) で ActivityMap リンクコレクションを除外して実装する必要があります。Activity Map によって PII データがどのように収集される可能性があるかについて詳しくは、[こちら](/help/analyze/activity-map/lnk-tracking-overview.md)を参照してください。

Activity Map では、次の 2 つの ID に基づいてリンクトラッキングをおこないます。

* プライマリ ID：リンクの認識可能なパラメーターです。
* リンク領域：このセカンダリパラメーターを使用すると、ページまたは領域の全体的なリンク領域を表現する文字列を指定できます。このパラメーターは、ユーザーが指定しない場合は自動的に生成できます。

## プライマリ ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

HTML に s_objectid が含まれている場合、プライマリ ID はデフォルトで s_objectid になります。その他の場合は、以下のパラメーターがプライマリ ID として使用されます（優先順位が高い順）。

* Innertext
* Alttext
* タイトル
* Src
* アクション

## InnerText の使用とリンクアクション（URL）の使用 {#section_70C3573E22274522A8CC035BF18EC468}

リンクアクションは、リンクをクリックしたときに Web ページで実行されるアクションです。通常は、リンクをクリック後の訪問先の URL です。リンクアクションを使用すると、以下のような問題が発生する場合があります。

* 2 つ以上の異なるリンクの ID が同じになる
* リンクの読みやすさ
* 1 つのリンクが複数のアクションを持つ（リンクを表示するデバイスによる）

その結果、InnerText を使用すると、リンクアクション（URL）を使用した場合に比べて以下のメリットがあります。

* リンクの ID が適切に表現されます。一般的に複数のリンクが同じテキストになることがないので、プライマリ ID の重複が大幅に減少します。
* デバイスやブラウザーのタイプをまたがってプライマリ ID の一貫性が確保されます。
* ページ上のリンク再配置の影響を受けません。
* 読みやすさが向上するので、Activity Map 外でリンクトラッキングレポートの分析を開始できます。

## リンク領域 {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

この新しい属性では、リンクが配置されているページ領域を表現する文字列を指定できます。

例えば、Web ページのメニューセクションに配置されている「お問い合わせ」リンクに関して、「メニュー」領域パラメーターを渡したい場合があります。同様に、Web ページのフッターに配置されている「お問い合わせ」リンクに関しては、領域パラメーターが「フッター」に設定される場合があります。

リンク領域の値はリンク自体に設定されるのではなく、その領域を含む DOM HTML ツリー内の 1 つ上の HTML 要素に設定されます。リンク領域を使用すると、次のようなメリットがあります。

* プライマリ ID が同じ複数のリンクを区別できます。
* 領域のトレンドに対する Web ページの動的側面の影響が小さくなります。
* 領域内でパフォーマンスが上位のリンクを確認できます。領域をアンカーとして、現在ページに表示されていないリンク（Ajax、ターゲティング）のオーバーレイを表示できます。
* 特定の領域を複数の Web ページで使用する場合があるので、領域をページより優先させることができます。これは、「製品提供」領域が女性のランディングページと男性のランディングページのどちらで良いパフォーマンスを発揮するかといった質問に回答する際に役立ちます。
* 領域は、それ自体、高度に動的な Web ページの分析に関連するディメンションです。これは、リンクが絶え間なく変化することによるノイズが削減されるからです。CNN のランディングページの「最新ニュース」領域では、多くのリンクが頻繁に変更されている可能性があります。それでも、領域は常にそこにあります。そのため、領域レベルで長期に渡ってトレンドを分析すると興味深い結果が得られる場合があります。

**カスタマイズされた領域トラッキング**

リンクの領域パラメーターをカスタマイズできます（デフォルトはリンク ID）。「ID」に設定されているタグは、領域としての &quot;id&quot; パラメーターを持つすべての HTML 要素を使用します。したがって、領域タグを &quot;id&quot; に設定すると、多くの場合、多数の異なる領域が返されます（ページ上の「ID」の数に応じて）。また、よりカスタマイズされた実装が必要な場合は、領域タグを &quot;region_id&quot; など、より具体的なものに設定できます。

以下に、デフォルトの領域 ID 属性 &quot;id&quot; を使用したサンプルの HTML を示します。

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

必要に応じて、任意の文字列 ID（この場合は &quot;lpos&quot;）を使用して要素にタグを付け、&quot;lpos&quot; という名前で属性を追加することもできます。

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## 設定変数 {#configuration-vars}

以下の変数はあくまでも参照目的です。Activity Map は追加設定なしで適切に設定できますが、以下の変数を使用して実装をカスタマイズすることもできます。

### `s.ActivityMap.regionIDAttribute`

`s.linkObject`、つまり **クリックされたエレメント (親、親、親、親、...) エレメントの領域 ID として使用するタグ属性を指定するストリングです** 。

**例**

デフォルトで &quot;id&quot; パラメーターに設定されます。これを別のパラメーターに設定できます。

### `s.ActivityMap.link`

クリックされたを受け取る、 `HTMLElement` クリックされたリンクを表すストリング値を返す関数。 戻り値が false（null、未定義、空の文字列、0）の場合、リンクは追跡されません。

**例**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

クリックされた HTMLElement を受け取り、**クリックしたときにリンクが見つかった領域を表す文字列値を返す関数。**&#x200B;戻り値が false（null、未定義、空の文字列、0）の場合、リンクは追跡されません。

**例**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

リンクテキスト内を検索する文字列のコンマ区切りのリストを受け取る文字列。見つかった場合、リンクは Activity Map による追跡から除外されます。設定されていない場合、Activity Map によるリンクの追跡を停止することはありません。

**例**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

地域テキスト内を検索する文字列のコンマ区切りのリストを受け取る文字列。見つかった場合、リンクは Activity Map による追跡から除外されます。設定されていない場合、Activity Map によるリンクの追跡を停止することはありません。

**例**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
