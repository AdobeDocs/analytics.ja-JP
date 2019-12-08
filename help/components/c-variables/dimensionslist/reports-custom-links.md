---
description: サイトの訪問者が好むリンクが表示されます。例えば、サイトのホームページには、同一ページを表示する複数のリンクが貼られていることがよくあります。画像リンクとテキストリンクが同じリンク先ページに接続されている場合もあります。このレポートは、画像リンクを使用した訪問者とテキストリンクを使用した訪問者のパーセントを示します。
title: カスタムリンク
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# カスタムリンク

サイトの訪問者が好むリンクが表示されます。例えば、サイトのホームページには、同一ページを表示する複数のリンクが貼られていることがよくあります。画像リンクとテキストリンクが同じリンク先ページに接続されている場合もあります。このレポートは、画像リンクを使用した訪問者とテキストリンクを使用した訪問者のパーセントを示します。

トラッキング対象のリンクは、特別なタグで変更する必要があります。詳しくは、[リンクトラッキング](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)を参照してください。

[!UICONTROL カスタムリンクレポート]は次の目的で使用できます。

* 訪問者がより頻繁にクリックするリンク タイプに合わせて、サイトのデザインを最適化できます。
* 単一ページへ複数のリンクを設定する必要があるかどうかを検証できます。

## モバイル SDK のリンク名 {#section_70C91FE794104B5FBF289B19CC02EA8E}

[モバイル SDK](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) では、カスタムリンクを使用してアクションとライフサイクル指標をトラッキングします。モバイルアプリの測定に使用されるレポートスイートには、SDK によって設定される次のリンク名が表示されます。

| ADBINTERNAL:Lifecycle | 4.x SDK のライフサイクル呼び出しによって送信されます。 |
|---|---|
| AMACTION:[action name] | 4.x SDK の trackAction() メソッドによって送信されます。アクション名には、メソッドの呼び出し時に設定された名前が使用されます。 |
| ADMS BP Event | 3.x SDK のライフサイクル呼び出しによって送信されます。 |

