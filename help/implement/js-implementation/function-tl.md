---
description: ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。
keywords: Analytics の導入
seo-description: ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。
seo-title: s.tl() 関数 - リンクトラッキング
solution: Analytics
subtopic: リンクトラッキング
title: s.tl() 関数 - リンクトラッキング
topic: 開発者と導入
uuid: f28f071a-8820-4f74-89cd- fd2333a21f22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# s.tl() 関数 - リンクトラッキング

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## s.tl() 関数 - リンクトラッキング {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

以下に説明するように、これらのタイプのリンクは、必要に応じてカスタムリンクコードを使用して手動で追跡できます。また、カスタムリンクコードは、様々なトラッキングやレポートのニーズに利用される一般的なカスタムリンクを追跡するために使用することもできます。

## s.tl() パラメーターリファレンス {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

最初の引数は、必ず this（デフォルト）または true に設定します。この引数はクリックされるオブジェクトを参照します。「this」に設定されている場合は、リンクの HREF プロパティを参照します。

HREFプロパティのないオブジェクトでリンクトラッキングを導入する場合は、この引数を&quot;this&quot;に設定する必要があります。

リンクをクリックすると訪問者が現在のページから離れることが多いので、ユーザーがページを離れる前にイメージリクエストがアドビに確実に送信されるように、500 ms の遅延が使用されます。この遅延はページを離れるときにのみ必要ですが、通常、s.tl() 関数が呼び出されるときにもこの遅延が発生します。この遅延を無効にするには、s.tl() 関数を呼び出すときに最初のパラメーターとしてキーワード「true」を渡します。

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

linkType には、取り込むリンクのタイプに従って 3 つの値を指定できます。リンクがダウンロードリンクまたは離脱リンクではない場合、カスタムリンクオプションを選択してください。

| タイプ | linkType の値 |
|--- |--- |
| ファイルのダウンロード数 | &#39;d&#39; |
| 離脱リンク | &#39;e&#39; |
| カスタムリンク | &#39;o&#39; |

**linkName**

この値には、100 文字までのカスタム値を使用できます。該当するレポートでリンクをどのように表示するかを指定します。

**variableOverrides**

（オプションです。使用しない場合は null を渡します）これを使用すると、送信される変数値を変更できます。他の [!DNL AppMeasurement] ライブラリと類似しています。

**useForcedLinkTracking**

このフラグは、一部のブラウザーでの強制のリンクトラッキングを無効にするために使用します。強制のリンクトラッキングは、FireFox 20 以降および WebKit ブラウザーではデフォルトで有効になっています。

Default Value= true

例: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

`s.tl` に渡された doneAction の実行前に、トラッキングの完了を待機する時間（ミリ秒）の最大値。この値によって、最大の待機時間が指定されます。このタイムアウトの前にリンクトラッキングが完了した場合は、doneAction が直ちに実行されます。リンクトラッキングが未完了になっている場合は、このタイムアウト時間を長くする必要があると考えられます。

デフォルト値=250

例: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

useForcedLinkTracking が有効になっている場合、リンクトラッキングが完了した後に実行するナビゲーションアクションを指定するオプションのパラメーター。

構文：

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

doneAction：（オプション）リンクトラッキングの送信後、またはリンクトラッキングのタイムアウト後（指定値に基づく）に実行するアクションを指定します。

`s.forcedLinkTrackingTimeout`

doneAction 変数に navigate という文字列を指定すると、このメソッドによって `document.location` に linkObject の href 属性が設定されます。また、doneAction 変数に関数を指定し、高度なカスタマイズをおこなうこともできます。

アンカーの onclick イベントの doneAction に値を指定する場合は、`s.tl` の呼び出し後に false を返すようにし、デフォルトのブラウザーナビゲーションがおこなわれないようにする必要があります。

デフォルトの動作を反映し、href 属性で指定された URL に移動するには、doneAction に navigate の文字列を指定します。

オプションとして、ナビゲーションイベントを処理するために独自の関数を指定するには、この関数を doneAction として渡すことができます。

例：

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**例**

次の例に示す [!UICONTROL s.tl()] 関数の呼び出しでは、ページを離れる前にデータが確実に収集されるように、デフォルトの 500 ms の遅延を使用しています。

```js
s.tl(this,'o','link name');
```

次の例では、ユーザーがページを離れない場合またはクリックされるオブジェクトに HREF がない場合に、500 ms の遅延を無効にしています。

```js
s.tl(true,'o','link name');
```

500 ms が最大の遅延です。要求されたイメージが 500 ms 経過しないうちに返されると、遅延は直ちに停止します。これにより、訪問者は次のページまたはページ内の次のアクションに移ることができます。

次の例は、WebKit ブラウザーでカスタムリンクを扱う際の例です。

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>カスタムリンクコードの使用は、多くの場合、ウェブサイトやレポートニーズに特化しています。カスタムリンクコードで利用できる機能、およびビジネスニーズに基づいてこの機能を最大限に活用する方法を理解するには、カスタムリンクコードを導入する前に、アドビコンサルタントまたはアドビカスタマーケアにお問い合わせください。

カスタムリンクコードを使用するリンクを追跡する基本コードを、次の例に示します。

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>[!UICONTROL s_ gi] 関数には、レポートスイートIDを関数パラメーターとして含める必要があります。個別のレポートスイート ID の [!DNL rsid] を必ずスワップアウトしてください。

>[!NOTE]
>
>リンク名パラメーターを定義していない場合、（&quot;this&quot;オブジェクトから決定された）リンクのURLがリンク名として使用されます。

[!DNL Analytics] 変数は、カスタムリンクコードの一部として定義できます。

## 離脱リンクとファイルのダウンロード数の自動トラッキング {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

ファイルのダウンロードのファイルタイプおよび離脱リンクを定義するパラメーターに基づき、ファイルのダウンロード数と離脱リンクを自動的に追跡するよう JavaScript ファイルを設定できます。

<!-- 

link_automatic.xml

 -->

自動トラッキングを制御するパラメーターは、以下のとおりです。

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

パラメーター *`trackDownloadLinks`* 自動ファイルダウンロードと離脱リンクトラッキングが有効かどうかを *`trackExternalLinks`* 判断できます。When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

次の設定の場合、以下の例は離脱リンクとしてカウントされます。

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## 例 3 {#section_2A78D05162D640169844A7D1E9799BAA}

次の設定の場合、以下のリンクは離脱リンクとしてカウントされません。

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>単一リンクはファイルのダウンロードまたは離脱リンクとしてのみ追跡でき、ファイルのダウンロードが優先されます。If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. ファイルのダウンロード数と離脱リンクの自動トラッキングについて、以下の表にまとめます。

## カスタムリンクコードを使用した手動リンクトラッキング {#concept_7113B5D037BE4622B6934554C6D18F96}

カスタムリンクコードを使用すると、自動トラッキングが不十分または適用できない状況で、ファイルのダウンロード数、離脱リンクおよびカスタムリンクを追跡することができます。

<!-- 

link_manual.xml

 -->

通常、カスタムリンクコードは、リンクに [!UICONTROL onClick] イベントハンドラーを追加するか、既存のルーチンにコードを追加することで導入されます。また、カスタムリンクコードは基本的にはいずれの JavaScript イベントハンドラーまたは関数からも導入できます。

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. この関数（[!UICONTROL s.tl()]）は、[!UICONTROL onClick] や [!UICONTROL onChange] などのイベントハンドラーで直接呼び出したり、個別の関数内から呼び出すことができます。この [!UICONTROL s.tl()] 関数は次の 5 つの引数を使用します。最初の 3 つは必須です。

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## FireFox および WebKit ブラウザーでのカスタムリンクトラッキング {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 では、WebKit ブラウザー（Safari および Chrome）でリンクトラッキングを正常に完了するように更新されました。JavaScript H.26 では、FireFox 20 以降でリンクトラッキングを正常に完了するように更新されました。

この更新により、自動的に追跡されるダウンロードリンクおよび離脱リンク（[!DNL s.trackDownloadLinks] および [!DNL s.trackExternalLinks] で指定）は正常に追跡されるようになりました。手動による JavaScript 呼び出しを使用してカスタムリンクを追跡している場合は、これらの呼び出しの実行方法を修正する必要があります。例えば、離脱リンクおよびダウンロードリンクは、多くの場合次のようなコードを使用して追跡されています。

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer では、リンクトラッキングが実行され新しいページが開きます。その他のブラウザーでは、新しいページを開くとリンクトラッキングの実行がキャンセルされる場合があります。これにより、リンクトラッキングが完了できないことがあります。

これに対応するために、H.25（2012 年 7 月リリース）以降ではリンクトラッキングメソッド（[!DNL s.tl]）で指定できるオプションを追加し、リンクトラッキングが完了できないブラウザーでこの完了を強制的に待機させるようになりました。この新しいメソッドでは、リンクトラッキングを実行し、デフォルトのブラウザーのアクションを使用せずにナビゲーションイベントとして処理します。そのためには、[!UICONTROL doneAction] パラメーターを追加し、リンクトラッキングが完了したときにおこなうアクションを指定する必要があります。

[!DNL s.tl] の記述を次のように変更し、リンクトラッキング後に実行すべき関数名または「navigate」という文字列を 5 つめの引数である [!UICONTROL doneAction] パラメーターとして指定してください。

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

[!UICONTROL doneAction] として渡された navigate は実行すべきオリジナルの関数名ではなく事前定義された特殊な文字列であり、トラッキングが完了した後に、href 属性で指定された URL が開くようになります。

JavaScript H.25.4（2013 年 2 月リリース）では、`useForcedLinkTracking` を有効にしたときに追跡されるリンクについて、次のような範囲制限が追加されました。自動強制のリンクトラッキングは、次の場合にのみ適用されます。

* `<A>``<AREA>` とタグを使用します。
* タグに `HREF` 属性が含まれている必要がある。
* The `HREF` can&#39;t start with `#`, `about:`, or `javascript:`.
* `TARGET` 属性を設定しないでください。または `TARGET` 、現在のウィンドウ（ `_self`、 `_top`または値 `window.name`）を参照する必要があります。

## イメージリクエストを使用したリンクトラッキング {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

イメージリクエストを作成すると、s.tl() 関数を呼び出さずにリンクをトラッキングすることができます。

<!-- 

link_img.xml

 -->

イメージリクエストは、次のように、イメージリクエストの src パラメーターに「pe」パラメーターを追加することでハードコードされます。

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = ダウンロード
* lnk_e = 離脱
* lnk_o = カスタム

また、pev1 パラメーターに URL を渡すことで、リンク URL を指定できます。

```
pev1=mylink.com
```

pev2 パラメーターにリンクの名前を渡すことで、リンク名を指定することもできます。

```
pev2=My%20Link
```

以下に例を示します。

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## ファイルのダウンロード数、離脱リンクおよびカスタムリンクに対する追加変数の設定 {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

デフォルトでは、これらのパラメーターは JS ファイル内で次のように設定されます。

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

&quot;*`linkTrackVars`* パラメーターには、すべてのファイルのダウンロード、離脱リンク、カスタムリンクで追跡する各変数を含める必要があります。*`linkTrackEvents`* パラメーターには、すべてのファイルのダウンロード、離脱リンクおよびカスタムリンクで追跡する各イベントを含める必要があります。これらのリンクタイプのいずれかが発生した場合、識別された各変数の現在値が追跡されます。

例えば、すべてのファイルのダウンロード、離脱リンク、カスタムリンクで prop1、eVar1、event1 を追跡するには、グローバル JS ファイル内で以下の設定を使用します。

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>*`linkTrackVars`* （また *`linkTrackEvents`*は）がnull（または空の文字列）の場合、現在のページに対して定義されている [!DNL Analytics] すべての変数（またはイベント）が追跡されます。これにより、各変数のインスタンスが増大する可能性があるので、null を避ける必要があります。

## ベストプラクティス {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. 各変数とイベントのインスタンスは、変数（またはイベント）が現在のページに適用される場合に増加できますが、特定のファイルのダウンロード、離脱リンクまたはカスタムリンクでは増加できません。

カスタムリンクコードによって適切な変数が設定されるように、アドビではカスタムリンクコード内で *`linkTrackVars`* カスタムリンクコード *`linkTrackEvents`* 内で、次のように指定します。

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>上記の例では、prop1の値がカスタムリンクコード内で設定されています。prop2 の値はページで設定された変数の現在値から適用されます。

## カスタムリンクコードによる関数呼び出しの使用方法 {#concept_DB662C93B3ED415DB72C80270502BE5D}

カスタムリンクコードには複雑な特性があるので、コードを自己充足型 JavaScript 関数（ページまたはリンクされた JavaScript ファイルで定義）に統合したり、[!UICONTROL onClick] ハンドラー内の関数を呼び出したりできます。

<!-- 

link_functions.xml

 -->

`AppMeasurement.js` 例えば、ファイルに次の2つの関数を挿入して `s_doPlugins()` 、その関数のすぐ下に、サイト全体で使用することができます。

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>必要に応じて、JavaScript関数の追加パラメーターとしてリンクタイプとリンク名を渡すことができます。

そのような関数を呼び出すには、以下のようなコードを使用します。

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## リンクの二重カウントの防止 {#section_9C3F73DE758F4727943439DED110543C}

リンクが自動ファイルダウンロードまたは離脱リンクの自動トラッキングで取り込まれる状況下で、リンクが二重にカウントされる可能性があります。

例えば、PDF ダウンロードを自動トラッキングしている場合、以下のコードを使用するとダウンロードが二重にカウントされます。

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

リンクの二重カウントが発生しないようにするには、次の変更された JavaScript 関数を使用します。

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

上記のコードの最後の 2 行は、自動トラッキング動作のみが発生し、二重カウントを排除するように、カスタムリンクコードの動作を変更します。

## useForcedLinkTracking を使用したポップアップウィンドウ {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] では、リンクトラッキングを実行し、デフォルトのブラウザーのアクションを使用せずにナビゲーションイベントとして処理します。

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

これにより、問題なくリンクが追跡され、ポップアップが読み込まれます。

## URL 短縮サービスからのリンク {#concept_CD792362A8E04448B452BE9A18772024}

一般に、URL 短縮サービス（bit.ly など）からのリンクは、ページビューまたはリファラーとして追跡されません。URL 短縮サービスは、完全修飾 URL と共に 301/302 リダイレクトを Web ブラウザーに返し、Web ブラウザーはその完全修飾 URL に別の新しい要求を送信します。これ以降は URL 短縮サービスが処理に関与しないため、リンク掲載元が保持されます。また、URL の取得にリダイレクトサービスが使用されたという形跡が残ることもありません。

<!-- 

link_shortener.xml

 -->

URL 短縮サービスには多様な種類があるため、各サービスで使用されるリダイレクトメカニズムを調べるために、実際のサイトで使用する特定のシナリオをテストしてみることをお勧めします。

## doPlugins のリンクトラッキング変数 {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

リンクトラッキングの管理のために、`doPlugins` 関数の実行前に以下の変数が設定されます。

<!-- 

util_linkhandler.xml

 -->

`doPlugins` 内部で以下の値を使用して、リンクトラッキングの動作を変更することができます。例えば、トラッキングを中止したり、トラッキングリクエストに変数を追加したりできます。

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> 影響 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>自動的に決定されたリンクタイプがある場合はその値を含みます。次のいずれかに設定できます。 </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d（ダウンロード） </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e（離脱） </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o（カスタム／その他） </li> 
    </ul> <p>これはイメージリクエストの <code>pe</code> パラメーターです。 </p> </td> 
   <td colname="col3"> <p><code>linkURL</code> または <code>linkName</code> と共に設定される場合、サーバーコールはダウンロードリンク、カスタムリンクまたは離脱リンクとして送信されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>カスタムリンク、ダウンロードリンクまたは離脱リンクのレポートに表示される名前。100 文字以下に切り捨てられます。どの文字列にも設定できます。 </p> <p>これはイメージリクエストの <code>pev2</code> パラメーターです。 </p> </td> 
   <td colname="col3"> <p> <code>linkType</code> と共に設定される場合、イメージリクエストはダウンロードリンク、カスタムリンクまたは離脱リンクとして送信されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>リンクの URL。linkName がない場合には名前として使用されます。どの URL 文字列にも設定できます。 </p> <p>これはイメージリクエストの <code>pev1</code> パラメーターです。 </p> </td> 
   <td colname="col3"> <p><code>linkType</code> と共に設定される場合、イメージリクエストはダウンロードリンク、カスタムリンクまたは離脱リンクとして送信されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>参照用のクリックされたオブジェクト。読み取り専用です。 </p> </td> 
   <td colname="col3"> <p>測定に直接影響はありません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## ファイルのダウンロード数、離脱リンク、およびカスタムリンクの確認 {#concept_0B43AD582D3E470899FCCB58E44D3D49}

ダウンロードリンク、離脱リンクおよびカスタムリンクを完全に検証するために、アドビではパケットアナライザーを使用してリアルタイムでリンクを調査することをお勧めします。

<!-- 

downloads_validate.xml

 -->

ファイルのダウンロード数、離脱リンク、カスタムリンクはページビューではないので、[!UICONTROL DigitalPulse Debugger] ツールを使用してパラメーターと変数の設定を検証することはできません。リンクトラッキングのデータを表示するには、[パケットアナライザー](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) を使用して追跡リンクデータを表示できます。
