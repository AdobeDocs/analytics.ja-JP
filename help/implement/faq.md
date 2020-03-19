---
title: Analytics の実装に関する FAQ
description: 実装に関するよくある質問と、詳細情報へのリンクです。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Analytics の実装に関する FAQ

実装に関するよくある質問と、詳細情報へのリンクです。

**変数の配分と有効期限の違いは何ですか。**

配分と有効期限は、どちらもカスタム変数に適用できる設定です。*配分*&#x200B;は、永続的な変数値と新しい変数値がある場合に動作し、古い値を保持するか、新しい値を保持するかを決定します。*有効期限*&#x200B;は、変数値を維持し続けたくない場合に動作します。

**Experience Cloud 訪問者 ID と Analytics 訪問者 ID の違いは何ですか。**

ID サービスは、Experience Cloud の他のソリューション間で共有できる一意の永続的な識別子を割り当てます。Analytics 訪問者 ID は、Analytics でのみ使用されます。実装に Experience Cloud 訪問者 ID サービスを使用することをお勧めします。

**Cookie がブロックされている場合に訪問者 ID がどのように設定されるのかを教えてください。**

標準的な「`s_vi`」Cookie を使用できない場合は、ランダムに生成された一意の ID を使用して、Web サイトでフォールバック Cookie が作成されます。この「`s_fid`」と呼ばれる Cookie は、2 年間の有効期限付きで設定され、今後のフォールバック識別方法として使用されます。

**ハートビートビデオトラッキングを実装する方法を教えてください。**

[Adobe Analytics でのオーディオおよびビデオの測定](https://docs.adobe.com/content/help/ja-JP/media-analytics/using/media-overview.html)を参照してください。

**アドビのサービスを中断すると、パフォーマンスに影響を与える可能性はありますか。**

いいえ。JavaScript ファイルは、アドビのサーバーでホストされていないでため、アドビの停止状態が AppMeasurement ライブラリに影響することはありません。Adobe Experience Platform Launch を使用する場合、JavaScript ファイルは Akamai または組織が決定したサーバーでホストされます。

**ブラウザーから Adobe サーバーへのデータの送信によってパフォーマンスが低下することはありますか。**

AppMeasurement は、HTML ページ内にイメージオブジェクトを作成し、ブラウザーは、Adobe データ収集サーバーからイメージオブジェクトをリクエストします。データ収集サーバーが低速になったり応答しなくなった場合、そのリクエストを処理するスレッドは、イメージが返されるかタイムアウトが発生するまで、遅延します。ブラウザーはイメージを複数のスレッドで処理するので、アドビの停止状態はページ読み込み時間にわずかな影響しか与えず、1 つのスレッドが停止していても、他のスレッドは機能し続けます。

**モバイルアプリを追跡する方法を教えてください。**

Adobe Experience Platform SDK を使用できます。詳しくは、[Adobe Experience Platform SDK の概要](https://aep-sdks.gitbook.io/docs/)を参照してください。

**プラグインとは何ですか。**

プラグインは、高度な機能を実行するコードスニペットです。プラグインは AppMeasurement の機能を拡張し、実装でより多くの機能を提供します。
