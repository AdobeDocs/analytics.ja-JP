---
title: パケットアナライザー
description: パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# パケットアナライザー

パケットアナライザーを使用すると、実装によってアドビのデータ収集サーバーに送信されたデータを表示できます。

Adobe Experience Cloud デバッガーと同様、パケット監視ではどのデータパラメーターがイメージリクエストに渡されているかが示されますが、パケット監視は次に示す追加機能も提供します。

* イメージリクエストをトラッキングするカスタムリンクの表示
* JavaScript 以外の導入メソッド（ハードコードされたイメージリクエストや [!DNL Appmeasurement] など）を使用するイメージリクエストの表示

Analytics の要求を表示するには、「b/ss」を使用して送信要求をフィルターします。

極めてまれなケースですが、デバッガーは、アドビの [!DNL Analytics] 処理サーバーに対して実際には要求がおこなわれないにもかかわらずイメージリクエストをレポートすることがあります。パケット監視の使用は、特定のイメージ要求が正常に実行されることを100%確認する優れた方法です。

アドビは公式のパケット監視を提供していませんが、インターネット上には様々なパケット監視が存在します。 次に、他のパケット監視が役に立つと判断した場合の例を示します。

>[!NOTE]以下のリストは、詳細な情報を示したものではありませんが、頻繁に使用される監視プログラムの概要を示しています。パケット監視をお持ちの方は、正常に使用し、役に立つ情報をお探しの場合は、このウィンドウの右側にあるボタンを使用して、フ [!UICONTROL Feedback] ィードバックをお寄せください。

| Firefox | Internet Explorer | Chrome | スタンドアロンプログラム |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) （タグビューア） | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) （タグビューア） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [フィドラー](https://www.fiddler2.com/fiddler2/) |
| [改ざんデータ](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]アドビでは、これらのパケット監視プログラムで発生した問題について、サポートやトラブルシューティングをおこなっておりません。サポートが必要な場合は、パケット監視の作成元のサイトを参照してください。

## 応答コード内の NS_BINDING_ABORTED

このエラーは、リンクトラッキングイメージリクエストが、アドビのデータ収集サーバーからの応答を待つ前にブラウザーで次のページに進むように設計されているために発生します。

イメージリクエストに対するアドビの応答は、空白の1 x 1透過イメージであり、ページのコンテンツには関係ありません。 アドビのパケット監視に、「**[!UICONTROL 200 OK]**」の応答または「**[!UICONTROL NS_BINDING_ABORTED]**」の応答を含む行項目がある場合、データは Adobe サーバーに到達しています。ページをこれ以上待つ必要はありません。

プラグインとして統合されたパケット監視では、完全な応答が表示されることはほとんどありません。 完全な応答が受信されなかったために中止されたとして、リクエストが表示される傾向があります。 また、中止されたのがリクエストか応答かを区別することもほとんどありません。 通常、スタンドアロンのパケット監視は、より詳細なメッセージを持ち、ステータスをより正確に報告します。 例えば、ユーザーが *Charlesで「Client closed connection before receiving entire response* 」というメッセージを受け取る場合があります。 つまり、データがアドビのサーバーに到達し、1x1ピクセルを受信する前にブラウザーが次のページに移動しただけです。

外部パケットスニファーが、応答ではなくデータ収集リクエストの中止をレポートした場合、これが問題の原因となります。 Adobe [!DNL Customer Care] からトラブルシューティングのサポートを受けることができます。
