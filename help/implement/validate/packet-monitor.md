---
title: パケットアナライザー
description: パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。
keywords: パケットスニファー、http ステータス、200、302、charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 679
ht-degree: 67%

---

# パケットアナライザー

パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。

Adobe CX Enterprise Debuggerと同様に、パケットモニターは、イメージリクエストで渡されるデータパラメーターを示します。ただし、パケットモニターは追加の機能を提供します。

* イメージリクエストをトラッキングするカスタムリンクの表示
* JavaScript 以外の導入メソッド（ハードコードされたイメージリクエストや [!DNL Appmeasurement] など）を使用するイメージリクエストの表示

Analytics の要求を表示するには、「b/ss」を使用して送信要求をフィルターします。

極めてまれなケースですが、デバッガーは、アドビの [!DNL Analytics] 処理サーバーに対して実際には要求がおこなわれないにもかかわらずイメージリクエストをレポートすることがあります。 パケットモニターを使用すると、特定のイメージリクエストが正常に実行されていることを100%確認できます。

Adobeは公式のパケットモニターを提供していませんが、インターネット上には幅広いパケットモニターがあります。 以下は、その他のパケットモニターの一部です。

>[!TIP]
>
>以下の表は、詳細な情報を示したものではありませんが、頻繁に使用される監視の概要を示しています。

| Firefox | Internet Explorer | Chrome | スタンドアロンプログラム |
|---|---|---|---|
| [ ポイントを監視](https://www.observepoint.com/product#plugin) （タグビューアー） | [HttpWatch](https://www.httpwatch.com/) | [ ポイントを監視](https://www.observepoint.com/product#plugin) （タグビューアー） | [ チャールズ ](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.telerik.com/fiddler) |
| [改ざんデータ ](https://addons.mozilla.org/ja-JP/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>アドビでは、これらのパケット監視プログラムで発生した問題について、サポートやトラブルシューティングをおこなっておりません。 サポートが必要な場合は、パケット監視の作成元のサイトを参照してください。

## 一般的な HTTP 応答のステータスコード

AppMeasurement がアドビのデータ収集サーバーにデータを送信すると、サーバーは応答ステータスコードで応答します。

* **200 OK**：データ収集サーバーからの最も一般的な応答。 イメージリクエストが正常に受信され、透明なイメージが返されました。
* **302 FOUND**：この応答を受け取る理由はいくつか考えられます。
   * 訪問者の最初のイメージリクエスト：リダイレクトは、ユーザーが初めてサイトを訪問した場合に発生します。 このリダイレクトは、訪問者 Cookie を取得するためのものです。 データ収集には影響しません。
   * Comscore と Adobe の統合：組織で Comscore／Analytics 統合を使用している場合、各イメージリクエストの結果は常に 302 応答になります。
* **404 NOT FOUND**:この応答は、イメージリクエストが見つからず、データがアドビのデータ収集サーバーに送信されないことを意味します。 この応答は、ハードコードされたイメージリクエストが正しく形式設定されていない場合にも発生します。 この問題を解決するには、Analytics を実装した個人またはチームに相談してください。

## 応答コード内の NS_BINDING_ABORTED

このメッセージが発生する理由は、リンクトラッキングイメージリクエストが、アドビのデータ収集サーバーからの応答を待機する前にブラウザーに次のページへの移動を許可するように設計されていることです。

イメージリクエストに対するアドビの応答は、ブランクの 1 x 1 透過イメージのみであり、ページの内容とは関係ありません。 アドビのパケット監視に、「**[!UICONTROL 200 OK]**」の応答または「**[!UICONTROL NS_BINDING_ABORTED]**」の応答を含む行項目がある場合、データはアドビのサーバーに到達しています。 ページの入力を待つ必要はもうありません。

プラグインとして統合されたパケットモニターが完全な応答を確認することはほとんどありません。 完全な応答が受信されなかったため、リクエストが中断されたと見る傾向があります。 また、これらのモニターは、中止されたリクエストとレスポンスのどちらかを区別することはほとんどありません。 スタンドアロンのパケットモニターでは、通常、より詳細なメッセージが表示され、ステータスをより正確に報告します。 例えば、*Charles*&#x200B;で「クライアントが応答を受信する前に接続を閉じました」というメッセージが表示される場合があります。 つまり、データがサーバーに届いたのか、ブラウザーが1x1 ピクセルを受信する前に次のページに移動しただけです。

外部パケットモニターが応答でなくデータ収集リクエストの中止をレポートしている場合、問題の可能性があります。 Adobe [!DNL Customer Care] からトラブルシューティングのサポートを受けることができます。
