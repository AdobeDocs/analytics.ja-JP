---
title: Activity Map の FAQ
description: Activity Mapに関するよくある質問です。
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 22%

---

# Activity Map の FAQ

Activity Mapに関するよくある質問です。

+++Activity Mapに権限を付与するにはどうすればよいですか？

Activity Mapおよび関連するディメンションを使用する権限は、[Adobe Admin Console](/help/admin/admin-console/home.md) で処理されます。

Activity Mapに必要な [ 権限項目 ](/help/admin/admin-console/permissions/product-profile.md) には、次のものが含まれます。

* **[!UICONTROL Analytics ツール]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Analytics ツール]**/**[!UICONTROL セグメント公開]**
* **[!UICONTROL 寸法]** > **[!UICONTROL Activity Mapのスクロール範囲]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map リンク （地域別）]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map地域]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Map リンク]**
* **[!UICONTROL ディメンション]** > **[!UICONTROL Activity Mapページ]**

詳しくは、[Analytics ツールの製品プロファイル権限 ](/help/admin/admin-console/permissions/analytics-tools.md) を参照してください。

+++

+++Analytics ユーザー全員がActivity Mapにアクセスできますか？

Adobe Analytics Standard、Premium およびUltimateの契約を締結している組織は、Activity Mapにアクセスできます。 これらのコントラクト型は、Adobe Analyticsのお客様の大部分を占めています。

+++

+++Activity Map は単一ページアプリケーション（SPA）をどのようにサポートしていますか？

Activity Mapは数秒ごとに web ページをスキャンし、変更を探します。 Activity Mapは、再読み込みを必要とせずにページ上で新しいコンテンツを見つけますが、この新しいコンテンツは常に最初のページディメンション値に関連付けられます。

* Activity Map は、把握しているリンクの表示／非表示が変更されたかどうかを確認します。表示に変更が見つかった場合、そのリンクの「ページ上のリンク」の表の「現在の列」が、「[!UICONTROL 表示]」または「[!UICONTROL 非表示]」に更新されます。

* ユーザーの操作によって新しいコンテンツが作成されると、AppMeasurementによってリンクとして特定された新しい要素が、[!UICONTROL  ページ上のリンク ] の表に追加されます。 Activity Map は、これらの新しいリンクを含む新しいデータリクエストを送信します。データリクエストが返されると、新しいリンクが [!UICONTROL  ページ上のリンク ] テーブルに表示されます。

+++

+++Activity Mapは、表示されたがクリックされなかったリンクに関するデータを提供しますか？

いいえ。Adobeでは、表示されただけのリンクは自動的には追跡されません。

+++

+++Activity Map はどのブラウザーとバージョンをサポートしていますか？

Activity Mapでは、ほとんどのブラウザーの最新バージョンがサポートされています。

+++

+++Activity Map によってサーバーの呼び出しが増加しますか？

Activity Map 自体は、サーバーの呼び出しを送信しません。代わりに、Activity Map コンテキストデータ変数が、後続のページでの Analytics ページビュー呼び出しに含まれます。 ただし、Web SDK上のActivity Mapの以前のバージョンの一部は、Activity Map データに対して別の呼び出しを送信します。 最新バージョンの web SDKを使用している場合、Activity Mapのデータは次のイベントと結合されます。

+++

+++オーバーレイに一部のランク番号が表示されないのはなぜですか。

メニュー内に含まれているリンクなど、一部のリンクはページに表示されません。 その結果、対応するリンクオーバーレイは表示されません。 ランクは、非表示のリンクも含め、ページ上のすべてのリンクに対して計算されます。

+++

+++すべてのリンクレポートで、リンクのランキングはどのように決定されますか。

* **グラデーションおよびバブルモードの場合**：ランクは指標列によって決定されます。 指標の値が同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。
* **勝者および敗者モードの場合**：獲得率の列がランクを決定します。 獲得率が同じリンクに関しては、ランクはリンク ID のアルファベット順になります。

+++

+++複数のレポートスイートを使用するページでは、Activity Map はどのように動作しますか？

デフォルトでは、Activity Mapは、ページの最初のタグと関連付けられているレポートスイートを使用します。 別のレポートスイートは、**[!UICONTROL Activity Map設定]**/「その他 **[!UICONTROL タブから選択]** きます。

+++

+++Activity Map はページ上で Adobe Analytics をスキャンするのにどのくらい時間がかかりますか？

Activity Map は、ページの完了イベント後、Adobe Analytics のプレゼンスを最大 20 秒間スキャンします。

+++

+++Activity Map では、動的コンテンツをどのように処理しますか？

Activity Map では、2 秒ごとにチェックをおこない、web ページに次のような状態の変化が見つかったかどうかを確認します。

* HTML コンテンツの表示
* HTML コンテンツの非表示
* 新しく挿入された HTML コンテンツ

コンテンツの表示、非表示に関係なく、影響を受けるリンクの状態（およびオーバーレイ）が、非表示から表示、または表示から非表示に、拡張機能によって自動的に変更されます。 新しいコンテンツが挿入された場合、アプリケーションは関連するリンクを取得し、リンクの分析データを取り込んで、これらのリンクのオーバーレイを追加します。

+++

+++ページフローレポートはどのような指標に基づいていますか？

表示されるデータはすべて、ページビューに基づいています。

+++

+++データフィードを使用してActivity Map データを書き出すことはできますか？

はい。Activity Mapが使用する [ データフィード列 ](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) は次のとおりです。

* Activity Map リンク：`clickmaplink`
* Activity Mapページ：`clickmappage`
* Activity Map地域：`clickmapregion`
* 地域別のActivity Map リンク：`clickmaplinkbyregion`

+++

+++セグメントはライブモードで動作しますか？

いいえ。セグメントはライブモードでは機能しません。

+++

+++Activity Map は、仮想レポートスイートと互換性がありますか？

はい。ただし、仮想レポートスイートの制限により、Activity Mapのライブモードは仮想レポートスイートと互換性がありません。

+++

+++Activity Map を無効にするにはどうすればよいですか？

Activity Mapを無効にする方法は、実装の種類によって異なります。

* **Web SDK拡張機能**：拡張機能の設定で、「**[!UICONTROL 内部リンククリック数を収集]**」、「**[!UICONTROL 外部リンククリック数を収集]**」および「**[!UICONTROL ダウンロードリンクのクリック数を収集]**」チェックボックスをオフにします。
* **Web SDK JavaScript ライブラリ**:[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) を `false` に設定します。
* **Analytics 拡張機能**：拡張機能の設定で、「Activity Mapを使用 **[!UICONTROL というラベルの付いたボックスをオフに]** ます。
* **AppMeasurement**: `AppMeasurement.js` 内のActivity Map モジュールを削除またはコメントアウトするか、空の本文でモジュール関数呼び出しを上書きします：

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Activity Map オーバーレイを使用するための必要システム構成は何ですか？

Activity Map拡張機能では、最新バージョンのChrome、Edgeまたは Firefox を使用できます。

+++

+++Activity Mapを個人を特定できる情報に使用する際には、何を検討する必要がありますか？

Activity Mapを使用して個人を特定できるデータを収集できる次のシナリオを考えてみましょう。

* **メールリンク**：メールアドレスをクリックしてユーザーのメールクライアントを開いた場合、Activity Mapはクリックされたメールアドレスを収集できます。
* **ユーザー ID リンク**：訪問者がログインすると、Activity Mapでは訪問者のユーザー ID を含むリンクをすべて記録できます。
* **機密情報のリンク**：金融機関では、アカウント番号などの機密情報がリンクである場合に、訪問者がそれらをクリックすると追跡できます。
* **個人情報を含むリンク**：ヘルスケア web サイトの場合、リンクには個人情報を含めることができます。 訪問者がこれらのリンクをクリックすると、Activity Mapはそのリンクテキストを収集します。

+++

+++Activity Mapは、どのデータをデフォルトで追跡しますか？

Activity Mapは、次の要素を追跡します。

* `<a>` プロパティを持つ `<area>` または `href` タグ。 デフォルトでは、アンカータグリンク（`#`）は追跡されません。
* `onclick` 変数を設定する `s_objectID` 属性
* 値または子テキストを持つ `<input>` タグまたは `submit` ボタン
* タイプ `<input>` の `image` タグと `src` プロパティ
* 属性 `<button>` を持たない `type="button"` タグ。 `<button>` のタグをトラッキングする場合は、代わりに `role="button"` や `submit="button"` などの属性を使用することを検討してください。

+++

+++Activity Mapで自動的に追跡されるリンクの例をいくつか挙げてください。

Activity Mapに、リンクのトラッキングに必要な情報がすべて含まれている例を以下に示します。

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

+++Activity Mapで自動的に追跡されないリンクの例をいくつか示します。

* アンカータグに有効な `href` がありません
* [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md) もメソッドも存在 [`tl()`](/help/implement/vars/functions/tl-method.md) ません
* フォーム入力要素に `src` プロパティがありません

次に、Activity Mapでクリック数が追跡されない例を示します。

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
