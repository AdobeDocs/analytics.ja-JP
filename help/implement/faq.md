---
title: Analytics の実装に関する FAQ
description: 実装に関するよくある質問と、詳細情報へのリンクです。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Analytics の実装に関する FAQ

実装に関するよくある質問と、詳細情報へのリンクです。

**変数の配分と有効期限の違いは何ですか。**

配分と有効期限は、どちらもカスタム変数に適用できる設定です。 *割り当ては* 、永続的な変数値と新しい変数値がある場合に再生されます。 古い値を保持するか、新しい値を保持するかを決定します。 *変数* 値を維持し続けたくない場合、有効期限が有効になります。

**Experience cloud訪問者IDとAnalytics訪問者IDの違いは何ですか。**

IDサービスは、Experience cloudの他のソリューション間で共有できる一意の永続的な識別子を割り当てます。 Analytics訪問者IDは、Analyticsでのみ使用されます。 導入時にExperience cloud訪問者IDサービスを使用することをお勧めします。

**cookieがブロックされている場合、訪問者IDはどのように設定されますか。**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**ハートビートビデオトラッキングの実装方法**

[Adobe Analytics でのオーディオおよびビデオの測定](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)を参照してください。

**アドビのサービスを中断すると、パフォーマンスに影響を与える可能性はありますか。**

いいえ。JavaScriptファイルはAdobeサーバー上でホストされないので、Adobeの停止状態はAppMeasurementライブラリに影響を与えません。 Adobe Experience Platform Launchを使用する場合、JavaScriptファイルはAkamaiによってホストされるか、組織が決定したサーバーの場所に配置されます。

**ブラウザーからアドビのサービスにデータを送信すると、パフォーマンスが低下する可能性はありますか。**

AppMeasurementはHTMLページ内にイメージオブジェクトを作成し、ブラウザーはAdobeデータ収集サーバーからイメージオブジェクトを要求します。 データ収集サーバーの動作が遅かったり応答しなかった場合は、イメージが返されるかタイムアウトが発生するまで、その要求を処理するスレッドが遅延することになります。 ブラウザーはイメージを複数のスレッドで処理するので、アドビの停止状態はページ読み込み時間にわずかな影響しか与えず、1 つのスレッドが停止していても、他のスレッドは機能し続けます。

**モバイルアプリの追跡方法を教えてください。**

Adobe Experience Platform SDKを使用できます。 詳しく [は、Adobe Experience Platform SDKの概要](https://aep-sdks.gitbook.io/docs/) （英語のみ）を参照してください。

**プラグインとは**

プラグインは、高度な機能を実行するコードスニペットです。 AppMeasurementの機能を拡張し、実装でより多くの機能を提供します。
