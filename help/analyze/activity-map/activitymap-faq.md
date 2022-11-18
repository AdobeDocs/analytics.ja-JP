---
description: Activity Map での設定や機能の使用に関するよくある質問（FAQ）です。
title: Activity Map の FAQ
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 0570bea923edc21a0f185f49fd6f604115d4a6e1
workflow-type: ht
source-wordcount: '689'
ht-degree: 100%

---

# Activity Map の FAQ

Activity Map での設定や機能の使用に関するよくある質問（FAQ）です。

+++Analytics ユーザー全員が管理ツールの ActivityMap イネーブルメントページにアクセスできますか？
Adobe Analytics Standard、Premium および Ultimate の契約を締結している組織は、Activity Map にアクセスできます。
+++

+++Activity Map は単一ページアプリケーション（SPA）をどのようにサポートしていますか？
Activity Map は数秒ごとに Web ページをスキャンし、ページの変更を探します。ActivityMap は、新しいページ読み込みを必要とせずにページ上で新しいコンテンツを見つけますが、この新しいコンテンツは常に、ページ読み込み時に見つかった最初の pageName に関連付けられます。

* Activity Map は、把握しているリンクの表示／非表示が変更されたかどうかを確認します。表示に変更が見つかった場合、そのリンクの「ページ上のリンク」の表の「現在の列」が、「[!UICONTROL 表示]」または「[!UICONTROL 非表示]」に更新されます。

* ユーザーの操作によって新しいコンテンツが作成されると、AppMeasurement でリンクと見なされる新しい要素が[!UICONTROL ページ上のリンク]の表に追加されます。Activity Map は、これらの新しいリンクを含む新しいデータリクエストを送信します。データリクエストが UI で処理されると、新しいリンクが[!UICONTROL ページ上のリンク]の表に表示されます。
+++

+++Activity Map は「表示」に関するデータを提供しますか？
いいえ。アドビでは、表示されたリンクの追跡は行いません。
+++

+++Activity Map では、どのブラウザーとバージョンをサポートしていますか？
Activity Map では、ほとんどのブラウザーの最新バージョンがサポートされています。
+++

+++Activity Map によってサーバーの呼び出しが増加しますか？
Activity Map 自体は、サーバーの呼び出しを送信しません。代わりに、Activity Map コンテキストデータ変数が、後続のページでの Analytics ページビュー呼び出しに含まれます。
+++

+++ランク付けされた項目の一部のオーバーレイが欠落しているのはなぜですか？
サブメニューリンクなど、ランク付けされたリンクの一部はページに表示されません。その結果、対応するリンクオーバーレイも表示されません。ランクは、非表示のリンクも含め、ページ上のすべてのリンクに対して計算されます。
+++

+++すべてのリンクレポートで、リンクのランクはどのように決定されますか？**
* **グラデーションおよびバブルモードの場合**：ランクは指標列によって決定されます。指標の値が同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。
* **勝者および敗者モードの場合**：ランクは主に「獲得率（%）」列によって決定されます。獲得率が同じリンクに関しては、ランクはリンク ID のアルファベット順になります。
+++

+++複数のレポートスイートを使用するページを Activity Map はどのように扱いますか？
デフォルトでは、Activity Map は、ページから最初に送信されたタグと関連付けられているレポートスイートを使用します。別のタグ付きレポートを選択するには、**[!UICONTROL Activity Map Settings]**／**[!UICONTROL Others]** タブを使用します。
+++

+++Activity Map がページ上で Adobe Analytics をスキャンするのにかかる時間はどのくらいですか？
Activity Map では、ページの完了イベントの後、Adobe Analytics が存在するかどうかを最大 20 秒間スキャンします。
+++

+++Activity Map では、動的コンテンツをどのように処理しますか？
Activity Map では、2 秒ごとにチェックをおこない、web ページに次のような状態の変化が見つかったかどうかを確認します。

* HTML コンテンツの表示
* HTML コンテンツの非表示
* 新しく挿入された HTML コンテンツ

コンテンツの表示、非表示に変化があった場合、アプリケーションでは影響を受けるリンクの状態（およびオーバーレイ）が、非表示から表示、または表示から非表示に、自動的に変更されます。新しいコンテンツが挿入された場合、アプリケーションは関連するリンクを取得し、リンクの分析データを取り込んで、これらのリンクのオーバーレイを追加します。
+++

+++ページフローレポートはどのような指標に基づいていますか？
表示されるデータはすべて、ページビューに基づいています。
+++

+++データフィードを使用して Activity Map のコンテキストデータ変数を書き出すことはできますか？
はい。Activity Map が使用する[データ列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)は、`clickmaplink`、`clickmaplinkbyregion`、`clickmappage` および `clickmapregion` です。
+++

+++セグメントはライブモードで動作しますか？
いいえ。セグメントはライブモードでは動作しません。この機能は、Reports &amp; Analytics のリアルタイムレポートと同様、セグメント化をサポートしません。
+++

+++Activity Map は、仮想レポートスイートと互換性がありますか？
はい。ただし、仮想レポートスイートの制限により、Activity Map のライブモードは仮想レポートスイートと互換性がありません。
+++

+++Activity Map を無効にするにはどうすればよいですか？
次の 3 つの選択肢があります。

* `AppMeasurement_Module_ActivityMap` 関数を JS ファイルから削除します。
* 上記の関数を空の本文に書き換えるカスタムコードを追加します。次に例を示します。

   ```js
   function AppMeasurement_Module_ActivityMap() {}
   ```

* `s.trackClickMap` および `s.trackInlineStats` を `false` に設定して AppMeasurement を設定します。
+++
