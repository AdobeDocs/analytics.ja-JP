---
title: Activity Map の FAQ
description: Activity Mapに関するよくある質問。
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
TQID: https://experienceleague.adobe.com/Bpcg3brrcxd9D6O3vFfhdZ7evCrJfarsKSzlOcYCMUg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1123
ht-degree: 22%

---

# Activity Map の FAQ

Activity Mapに関するよくある質問。

+++Activity Mapに権限を付与するにはどうすればよいですか？

Activity Mapとその関連ディメンションを使用する権限は、[Adobe Admin Console](/help/admin/admin-console/home.md)で処理されます。

Activity Mapに必要な[権限項目](/help/admin/admin-console/permissions/product-profile.md)は次のとおりです。

* **[!UICONTROL 分析ツール]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL 分析ツール]** > **[!UICONTROL セグメント公開]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Mapのスクロール範囲]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL 地域ごとのActivity Map リンク]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map リージョン]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map リンク]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map Page]**

詳しくは、[Analytics ツールの製品プロファイル権限](/help/admin/admin-console/permissions/analytics-tools.md)を参照してください。

+++

+++Adobe Analyticsをご利用のお客様は、Activity Mapにアクセスできますか？

Adobe Analytics Standard、Premium、およびUltimateの契約を結んでいる企業は、Activity Mapにアクセスできます。 これらの契約形態は、Adobe Analyticsのお客様の大部分を表します。

+++

+++Activity Map は単一ページアプリケーション（SPA）をどのようにサポートしていますか？

Activity Mapは、数秒ごとにweb ページをスキャンし、変化を探します。 Activity Mapは、再読み込みを必要とせずにページ上の新しいコンテンツを見つけますが、この新しいコンテンツは常に最初のページディメンション値に関連付けられます。

* Activity Map は、把握しているリンクの表示／非表示が変更されたかどうかを確認します。 表示に変更が見つかった場合、そのリンクの「ページ上のリンク」の表の「現在の列」が、「[!UICONTROL 表示]」または「[!UICONTROL 非表示]」に更新されます。

* ユーザーによる操作で新しいコンテンツが作成されると、AppMeasurementがリンクとして判断した新しい要素が[!UICONTROL  ページ上のリンク ] テーブルに追加されます。 Activity Map は、これらの新しいリンクを含む新しいデータリクエストを送信します。 データリクエストが返されると、新しいリンクが[!UICONTROL  ページ上のリンク ] テーブルに表示されます。

+++

+++Activity Mapは、閲覧されたもののクリックされたものではないリンクに関するデータを提供していますか？

いいえ。Adobeでは、表示されたリンクのみを自動的にトラッキングしません。

+++

+++Activity Map はどのブラウザーとバージョンをサポートしていますか？

Activity Mapでは、ほとんどのブラウザーの最新バージョンがサポートされています。

+++

+++Activity Map によってサーバーの呼び出しが増加しますか？

Activity Map 自体は、サーバーの呼び出しを送信しません。 代わりに、後続のページでAnalytics ページビュー呼び出しにActivity Map コンテキストデータ変数が含まれます。 ただし、以前のバージョンのActivity Map Web SDKでは、Activity Map データに対して別の呼び出しが送信されます。 最新バージョンのWeb SDKを使用している場合、Activity Map データは次のイベントと結合されます。

+++

+++オーバーレイにランク番号が表示されないのはなぜですか？

メニュー内に含まれるリンクなど、一部のリンクはページから非表示になります。 その結果、対応するリンクオーバーレイは表示されません。 ランクは、非表示のリンクも含め、ページ上のすべてのリンクに対して計算されます。

+++

+++「すべてのリンク」レポートでは、リンクのランキングはどのように決定されますか？

* **グラデーションモードとバブルモード**：指標の列でランクが決まります。 同じ指標値を持つリンクの場合、ランクはさらにリンク IDのアルファベット順に基づきます。
* **ゲインと敗者モード**：得られたパーセント列がランクを決定します。 獲得率が同じリンクに関しては、ランクはリンク ID のアルファベット順になります。

+++

+++複数のレポートスイートを使用するページでは、Activity Map はどのように動作しますか？

デフォルトでは、Activity Mapは、ページの最初のタグに関連付けられているレポートスイートを使用します。 別のレポートスイートを選択するには、「**[!UICONTROL Activity Map設定]** > **[!UICONTROL その他]**」タブを使用します。

+++

+++Activity Map はページ上で Adobe Analytics をスキャンするのにどのくらい時間がかかりますか？

Activity Map は、ページの完了イベント後、Adobe Analytics のプレゼンスを最大 20 秒間スキャンします。

+++

+++Activity Map では、動的コンテンツをどのように処理しますか？

Activity Map では、2 秒ごとにチェックをおこない、web ページに次のような状態の変化が見つかったかどうかを確認します。

* 見えるようになったHTMLコンテンツ
* 非表示のHTML コンテンツ
* 挿入された新しいHTML コンテンツ

コンテンツが非表示または表示されている場合、拡張機能は、影響を受けるリンクの状態（したがってオーバーレイ）を非表示から表示または非表示に変更します。 新しいコンテンツが挿入された場合、アプリケーションは関連するリンクを取得し、分析データを取得して、これらのリンクのオーバーレイを追加します。

+++

+++ページフローレポートはどのような指標に基づいていますか？

表示されるデータはすべて、ページビューに基づいています。

+++

+++データフィードを通じてActivity Map データを書き出すことはできますか？

はい。 Activity Mapが使用する[ データフィード列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)は次のとおりです。

* Activity Map リンク：`clickmaplink`
* Activity Map ページ：`clickmappage`
* Activity Map リージョン：`clickmapregion`
* リージョン別Activity Map リンク：`clickmaplinkbyregion`

+++

+++セグメントはライブモードで動作しますか？

いいえ、セグメントはライブモードでは機能しません。

+++

+++Activity Map は、仮想レポートスイートと互換性がありますか？

はい。 ただし、バーチャルレポートスイートの制限により、Activity Mapのライブモードはバーチャルレポートスイートと互換性がありません。

+++

+++Activity Map を無効にするにはどうすればよいですか？

Activity Mapを無効にする方法は、実装の種類によって異なります。

* **Web SDK拡張機能**：拡張機能の設定で、「**[!UICONTROL 内部リンククリックを収集]**」、「**[!UICONTROL 外部リンククリックを収集]**」、「**[!UICONTROL ダウンロードリンクを収集]**」のチェックボックスをオフにします。
* **Web SDK JavaScript library**: [`clickCollectionEnabled`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)を`false`に設定します。
* **Analytics拡張機能**：拡張機能の設定で、**[!UICONTROL Activity Mapを使用]**&#x200B;というラベルのボックスのチェックを外します。
* **AppMeasurement**: `AppMeasurement.js`内のActivity Map モジュールを削除またはコメント化するか、空の本文でモジュール関数呼び出しを上書きします。

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Activity Map オーバーレイを使用するための必要システム構成は何ですか？

Activity Map拡張機能を使用すると、Chrome、Edge、Firefoxの最新バージョンを使用できます。

+++

+++Activity Mapを個人を特定できる情報に使用する場合、何を考慮する必要がありますか？

Activity Mapを利用して個人を特定できるデータを収集する場合、次の点を考慮する必要があります。

* **電子メールリンク**：電子メールアドレスをクリックしてユーザーのメールクライアントを開くことができる場合、Activity Mapはクリックされた電子メールアドレスを収集できます。
* **ユーザーID リンク**：訪問者がログインすると、Activity Mapは訪問者のユーザーIDを含むリンクを記録できます。
* **機密情報リンク**：金融機関の場合、アカウント番号などの機密情報は、リンクであり、訪問者がクリックした場合に追跡できます。
* **個人情報を含むリンク**：ヘルスケアサイトの場合、リンクには個人情報を含めることができます。 訪問者がこれらのリンクをクリックすると、Activity Mapはそのリンクテキストを収集します。

+++

+++Activity Mapはデフォルトでどのようなデータを追跡しますか？

Activity Mapは、次の要素を追跡します。

* `<a>`または`<area>` タグと`href` プロパティ。 アンカータグリンク （`#`）は、デフォルトでは追跡されません。
* `s_objectID`変数を設定する`onclick`属性
* 値または子テキストを含む`<input>` タグまたは`submit` ボタン
* 型`image`および`src` プロパティを持つ`<input>` タグ
* 属性`type="button"`のない`<button>` タグ。 `<button>`個のタグを追跡する場合は、代わりに`role="button"`または`submit="button"`などの属性を使用することを検討してください。

+++

+++Activity Mapが自動的にトラッキングするリンクの例を教えてください。

次に、Activity Mapがリンクをトラッキングするために必要なすべての情報を持っている例をいくつか示します。

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Activity Mapで自動トラッキングされないリンクの例を教えてください。

* アンカータグに有効な`href`がありません
* [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md)または[`tl()`](/help/implement/vars/functions/tl-method.md) メソッドが存在しません
* フォーム入力要素に`src` プロパティがありません

次に、Activity Mapがクリックをトラッキングしない例をいくつか示します。

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
