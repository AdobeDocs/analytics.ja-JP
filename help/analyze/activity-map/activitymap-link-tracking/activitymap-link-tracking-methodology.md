---
description: このセクションは Adobe Analytics 管理者を対象としています。新しいリンクトラッキングパラメーターについて説明し、それによって異なるブラウザー間、デバイス間でのリンクの一意性と一貫性を確保し、ページ上でのリンクの再配置の処理を向上する方法を示します。
title: リンクトラッキング手法
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: 営業者、管理者
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 96%

---


# リンクトラッキング手法

このセクションは Adobe Analytics 管理者を対象としています。新しいリンクトラッキングパラメーターについて説明し、それによって異なるブラウザー間、デバイス間でのリンクの一意性と一貫性を確保し、ページ上でのリンクの再配置の処理を向上する方法を示します。

>[!IMPORTANT]
>
>テキスト（href 以外）に PII（Personally Identifiable Information：個人を特定できる情報）が含まれている可能性のあるリンクは、[s_objectID](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/page-variables.html) を使用して明示的に実装するか、[s.ActivityMap.linkExclusions または s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars) で ActivityMap リンクコレクションを除外して実装する必要があります。Activity Map によって PII データがどのように収集される可能性があるかについて詳しくは、[こちら](/help/analyze/activity-map/lnk-tracking-overview.md)を参照してください。

Activity Map では、次の 2 つの ID に基づいてリンクトラッキングをおこないます。

* プライマリ ID：リンクの認識可能なパラメーターです。
* リンク領域：このセカンダリパラメーターを使用すると、ページまたは領域の全体的なリンク領域を表現する文字列を指定できます。このパラメーターは、ユーザーが指定しない場合は自動的に生成できます。

## プライマリ ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

HTML に s_objectid が含まれている場合、プライマリ ID はデフォルトで s_objectid になります。その他の場合は、以下のパラメーターがプライマリ ID として使用されます（優先順位が高い順）。

* Innertext
* Alttext
* タイトル
* Src
* Action

## InnerText の使用とリンクアクション（URL）の使用  {#section_70C3573E22274522A8CC035BF18EC468}

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

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数名 </th> 
   <th colname="col2" class="entry"> 例 </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> デフォルトで "id" パラメーターに設定されます。これを別のパラメーターに設定できます。 </td> 
   <td colname="col3"> s.linkObject の上位（parent、parent.parent など）要素（<b>クリックされた要素</b>）の領域 ID として使用するタグ属性を識別する文字列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;linkId;</code><br/>
    <code>&nbsp;&nbsp;if&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A')&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title');</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;return&nbsp;linkId;</code><br/>
    <code>}</code> </td>
   <td colname="col3"> クリックされた HTMLElement を受け取り、<b>クリックされたリンク</b>を表す文字列値を返す関数。<br/>
      <br/>
     戻り値がfalse（null、未定義、空の文字列、0）の場合、リンクは追跡されません。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
        <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;regionId,&nbsp;className;</code><br/>
    <code>&nbsp;&nbsp;while&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement&nbsp;=&nbsp;clickedElement.parentNode))&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(regionId)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;regionId.toLowerCase();</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>}</code> </td> 
   <td colname="col3"> クリックされた HTMLElement を受け取り、<b>クリックしたときにリンクが見つかった領域</b>を表す文字列値を返す関数。<br/>
      <br/>
     戻り値がfalse（null、未定義、空の文字列、0）の場合、リンクは追跡されません。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
     <code>//&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class</code><br/>
    <code>&lt;style&gt;</code><br/>
    <code>.linkExcluded&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;display:&nbsp;block;</code><br/>
    <code>&nbsp;&nbsp;height:&nbsp;1px;</code><br/>
    <code>&nbsp;&nbsp;left:&nbsp;-9999px;</code><br/>
    <code>&nbsp;&nbsp;overflow:&nbsp;hidden;</code><br/>
    <code>&nbsp;&nbsp;position:&nbsp;absolute;</code><br/>
    <code>&nbsp;&nbsp;width:&nbsp;1px;</code><br/>
    <code>}</code><br/>
    <code>&lt;/style&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> リンクテキスト内を検索する文字列のコンマ区切りのリストを受け取る文字列。見つかった場合、リンクは Activity Map による追跡から除外されます。設定されていない場合、Activity Map によるリンクの追跡を停止することはありません。 </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap</code><br/>
    <code>&lt;div&nbsp;id="links-included"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;div&nbsp;id="links-excluded"&gt;&nbsp;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> 地域テキスト内を検索する文字列のコンマ区切りのリストを受け取る文字列。見つかった場合、リンクは Activity Map による追跡から除外されます。設定されていない場合、Activity Map によるリンクの追跡を停止することはありません。 </td>
  </tr>
 </tbody>
</table>
