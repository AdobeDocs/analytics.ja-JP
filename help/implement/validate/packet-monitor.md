---
title: パケットアナライザー
description: パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# パケットアナライザー

パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。

Adobe Experience cloudデバッガーと同様に、パケット監視はイメージリクエストで渡されているデータパラメーターを示します。ただし、パケットモニターには次の追加機能が用意されています。

* イメージリクエストをトラッキングするカスタムリンクの表示
* JavaScript 以外の導入メソッド（ハードコードされたイメージリクエストや [!DNL Appmeasurement] など）を使用するイメージリクエストの表示

Analytics の要求を表示するには、「b/ss」を使用して送信要求をフィルターします。

極めてまれなケースですが、デバッガーは、アドビの [!DNL Analytics] 処理サーバーに対して実際には要求がおこなわれないにもかかわらずイメージリクエストをレポートすることがあります。パケット監視の使用は、特定のイメージリクエストが正常に実行されていることを確認する上でとても高い効果があります。

アドビでは公式のパケット監視を提供していませんが、インターネットには様々なパケット監視があります。便利と評価されているパケット監視のいくつかを以下に示します。

> [!NOTE]以下のリストは、詳細な情報を示したものではありませんが、頻繁に使用される監視プログラムの概要を示しています。パケット監視を既にお持ちで、正しく使用しており、その便利さを実感されている場合は、このウィンドウの右にある「[!UICONTROL フィードバック]」ボタンを使用して、ご意見をお寄せください。

| Firefox | Internet Explorer | Chrome | スタンドアロンプログラム |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin)（タグビューア） | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin)（タグビューア） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

> [!NOTE]アドビでは、これらのパケット監視プログラムで発生した問題について、サポートやトラブルシューティングをおこなっておりません。サポートが必要な場合は、パケット監視の作成元のサイトを参照してください。

## 応答コード内のNS_BINDING_ABORTED

このエラーが発生する理由は、リンクトラッキングイメージリクエストが、アドビのデータ収集サーバーからの応答を待機する前にブラウザーに次のページへの移動を許可するように設計されていることです。

イメージリクエストに対するアドビの応答は、ブランクの 1 x 1 透過イメージのみであり、ページの内容とは関係ありません。アドビのパケット監視に、「**[!UICONTROL 200 OK]**」の応答または「**[!UICONTROL  NS_BINDING_ABORTED]**」の応答を含む行項目がある場合、データは Adobe サーバーに到達しています。ページがそれ以上待機する必要はありません。

プラグインとして統合されたパケットモニターでは、完全応答が表示されることがほとんどありません。完全応答が受信されなかったことが原因で中止されたものとして、リクエストが表示される傾向があります。これらのモニターでは、中止されたのがリクエストと応答のどちらだったかが区別されることはほとんどありません。通常、スタンドアロンのパケットモニターはより詳細なメッセージを保持しており、ステータスがより正確にレポートされます。例えば、ユーザーが *Charles* 内で「Client closed connection before receiving entire response（クライアントは応答全体を受信する前に接続を閉じました）」というメッセージを取得したとします。これは、データが Adobe サーバーに到達したが、1 x 1 ピクセルを受信する前にブラウザーが次のページに移動したことを意味します。

外部パケットスニファーが応答でなくデータ収集リクエストの中止をレポートしている場合、問題の可能性があります。Adobe [!DNL Customer Care] からトラブルシューティングのサポートを受けることができます。
