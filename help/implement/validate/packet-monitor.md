---
title: パケットアナライザー
description: パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: b359582fe8ab6ee04bb478825d9989d850390f96
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 58%

---


# パケットアナライザー

パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。

Adobe Experience Cloud デバッガーと同様、パケット監視ではどのデータパラメーターがイメージリクエストに渡されているかが示されますが、パケット監視は次に示す追加機能も提供します。

* イメージリクエストをトラッキングするカスタムリンクの表示
* JavaScript 以外の導入メソッド（ハードコードされたイメージリクエストや [!DNL Appmeasurement] など）を使用するイメージリクエストの表示

Analytics の要求を表示するには、「b/ss」を使用して送信要求をフィルターします。

極めてまれなケースですが、デバッガーは、アドビの [!DNL Analytics] 処理サーバーに対して実際には要求がおこなわれないにもかかわらずイメージリクエストをレポートすることがあります。パケット監視の使用は、特定のイメージリクエストが正常に実行されていることを確認する上でとても高い効果があります。

アドビでは公式のパケット監視を提供していませんが、インターネットには様々なパケット監視があります。便利と評価されているパケット監視のいくつかを以下に示します。

>[!TIP]
>
>以下の表は、詳細な情報を示したものではありませんが、頻繁に使用される監視の概要を示しています。

| Firefox | Internet Explorer | Chrome | スタンドアロンプログラム |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin)（タグビューア） | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin)（タグビューア） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobeは、これらのパケット監視で発生した問題をサポートまたはトラブルシューティングしません。 サポートが必要な場合は、パケット監視の発信元サイトを参照してください。

## 一般的なHTTP応答のステータスコード

AppMeasurementがAdobeのデータ収集サーバーにデータを送信すると、サーバーは応答ステータスコードで応答します。

* **200 OK**:データ収集サーバーからの最も一般的な応答。 イメージリクエストが正常に受信され、透明なイメージが返されました。
* **302件見つかり**:この応答を受け取る理由はいくつか考えられます。
   * 訪問者の最初のイメージ要求：リダイレクトは、ユーザーが初めてサイトを訪問した場合に発生します。 このリダイレクトは、訪問者Cookieを取得するためです。 データ収集には影響しません。
   * ComscoreとAdobeの統合：組織でComscore/Analytics統合を使用している場合、各イメージリクエストの結果は常に302件の応答になります。
* **404が見つかりません**:この応答は、イメージリクエストが見つからず、データがAdobeデータ収集サーバーに送信されないことを意味します。 この応答は、ハードコードされたイメージ要求が正しく形式設定されていない場合にも発生します。 この問題を解決するには、Analyticsを導入した個人またはチームに相談してください。

## 応答コード内の NS_BINDING_ABORTED

このメッセージが発生する理由は、リンクトラッキングイメージリクエストが、Adobeデータ収集サーバーからの応答を待つ前に、ブラウザーで次のページに進むように設計されていることです。

イメージリクエストに対するアドビの応答は、ブランクの 1 x 1 透過イメージのみであり、ページの内容とは関係ありません。If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe&#39;s servers. ページがそれ以上待機する必要はありません。

プラグインとして統合されたパケットモニターでは、完全応答が表示されることがほとんどありません。完全応答が受信されなかったことが原因で中止されたものとして、リクエストが表示される傾向があります。これらのモニターでは、中止されたのがリクエストと応答のどちらだったかが区別されることはほとんどありません。通常、スタンドアロンのパケットモニターはより詳細なメッセージを保持しており、ステータスがより正確にレポートされます。例えば、ユーザーが *Charles* 内で「Client closed connection before receiving entire response（クライアントは応答全体を受信する前に接続を閉じました）」というメッセージを取得したとします。これは、データが Adobe サーバーに到達したが、1 x 1 ピクセルを受信する前にブラウザーが次のページに移動したことを意味します。

外部パケット監視が、応答ではなくデータ収集リクエストの中止を報告した場合、問題の原因です。 Adobe [!DNL Customer Care] からトラブルシューティングのサポートを受けることができます。
