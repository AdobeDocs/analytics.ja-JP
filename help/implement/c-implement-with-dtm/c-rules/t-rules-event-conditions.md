---
description: 条件は、イベント型ルールがいつトリガーされるかを決定するものです。
keywords: Dynamic Tag Management；ルール；ルールの作成；ルールの新規作成；イベント型ルール；リンクのアクティブ化の遅延；要素にイベントハンドラーを直接適用；バブリング；イベントバブリング
seo-description: 条件は、イベント型ルールがいつトリガーされるかを決定するものです。
seo-title: イベント型ルールの条件の作成
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: イベント型ルールの条件の作成
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# イベント型ルールの条件の作成

条件は、イベント型ルールがいつトリガーされるかを決定するものです。

1. マウスクリック、フォームの送信など、追跡したい操作の種類を選択します。

   ![](assets/condition-event-based.png)

   詳しくは、Adobe Tag Management 製品ドキュメントの[イベントタイプ](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html)を参照してください。

1. 必要に応じて、次のオプションを有効にします。

   | 要素 | 説明 |
   |--- |--- |
   | リンクの有効化の遅延 | 別のページに移動するリンクのクリック時に、処理に時間がかかるルールを実行する場合に有効にします。ページ移動など、クリック後に本来おこなわれるべき処理がスタートする前に待ち時間が発生するようになります。 |
   | イベントハンドラーを要素に直接適用 | 対象にした特定の要素にイベントハンドラーを適用します。この設定は、ブラウザーのバブリングおよびレイヤリング概念とも関連します。 |

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. An event like a click can potentially bubble up to `<body>`. ルールが正しく起動するようにするには、イベントが実際にバインドされている対象を理解し、具体的にイベント型ルールを設定することが重要です。

   *バブリング*&#x200B;とは、イベントが最も深い要素で最初にキャプチャおよび処理され、次に外側の要素に伝達されることを意味します。

1. 追跡したいタグの名前と、さらに絞り込むための追加のプロパティを指定します。

   ![](assets/condition-event-based2.png)

   正しい要素タグの見つけ方については、Dynamic Tag Management 製品ドキュメントの [CSS セレクターの使用](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html)を参照してください。

1. さらに条件を追加することもできます。

   ![](assets/condition-event-based3.png)

1. イベントバブリングに関する優先順位を指定します。

   イベントバブリングは、HTML DOM でのイベント伝達の方法の 1 つです。

   | 目的 | チェックするオプション |
   |--- |--- |
   | 子要素の同じイベントでもルールを起動したい場合。 | 子要素のイベントのバブリングを許可する。 |
   | 子要素で既に独自のイベントがトリガーされているので、バブリングを避けたい場合。 | 子要素が既にイベントをトリガーしている場合、許可しない。 |
   | 明示的にイベントを指定し、親や子要素から切り離したい場合。 | イベントに親へのバブリングを許可しない。 |
