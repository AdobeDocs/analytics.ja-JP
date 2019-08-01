---
description: DFA 用の Genesis 統合は、DFA Floodlight 設定 ID（dfa_SPOTID）を利用します。これにより、DFA と Adobe データ収集システム間のレポートの一貫性が向上します。
keywords: DFA
seo-description: DFA 用の Genesis 統合は、DFA Floodlight 設定 ID（dfa_SPOTID）を利用します。これにより、DFA と Adobe データ収集システム間のレポートの一貫性が向上します。
seo-title: Web サイトのデータコレクションコードの更新
solution: Analytics
title: Web サイトのデータコレクションコードの更新
topic: Data Connectors
uuid: a97d1b62- f883-48b1-9516-4f889e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Web サイトのデータコレクションコードの更新{#update-your-web-site-s-data-collection-code}

DFA 用の Genesis 統合は、DFA Floodlight 設定 ID（dfa_SPOTID）を利用します。これにより、DFA と Adobe データ収集システム間のレポートの一貫性が向上します。

>[!NOTE]
>
>Spotlightという用語は、Google DFAの最近のリリースでFloodlightに変更されました。JavaScript パラメーター `dfa_SPOTID` は、Spotlight の用語に基づいて命名されましたが、両方のバージョンで使用されます。

Web サイトで DFA 統合を有効にするには、次を追加して JavaScript データコレクションコードを更新する必要があります。

* DFA 用 Integrate モジュール
* コレクションコードへの追加

## DFA 用 Integrate モジュール {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA 統合は、Adobe Marketing Cloud Integrate モジュールを利用して、コア JavaScript データコレクションコード（`s_code.js`）に機能を追加します。The Integrate Module comes as part of the .zip file when you download the AppMeasurement for Javascript code from the [Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). 追加のヘルプが必要な場合にのみ、アドビコンサルタントにお問い合わせください。

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## コレクションコードへの追加 {#section-8f98c727f1ba414fb8b4f02d696b8791}

統合ウィザードでの DFA 統合のアクティブ化の際の選択に基づいて、Data Connectors は、カスタマイズした追加を JavaScript データコレクションコードに生成して電子メールで送付します。`s_code.js` ファイルの（`doPlugins` 関数またはその他の関数ではなく）メインセクションにこのコードを挿入します。

以下に示すサンプルコードは、説明用です。Data Connectors 統合ウィザードを完了後に電子メールで送信されるコードを使用してください。

コレクションコードは、次のコンポーネントで構成されています。

* DFA Integrate 設定
* 統合が必要なプラグイン

**DFA Integrate 設定**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA Integrate 設定ブロックは、DFA 統合で必要な変数を設定します。これらの各変数の値は、次のソースから取得されます。

**CSID**：クライアント側 ID。統合ウィザードを完了すると、DFA によって生成されます。Data Connectors は、DFA CS ID でこの変数を事前設定します。また、統合ウィザードを完了した後、この値がセットアップ電子メールで送信されます。アカウントでアドバンス広告配信が有効になっている場合、この変数は不要です。

**SPOTID**：Floodlight 設定（以前の Spotlight ID）。Data Connectors は、統合ウィザードで指定した DFA アカウント情報に基づいて、DFA Floodlight 設定 ID でこの変数を事前設定します。

**tEvar**：転送変数。Data Connectors は、統合ウィザードでビュースルー変数用に指定した Analytics 変数名でこの変数を事前設定します。アドビエンジニアリングまたはエンジニアリングサービスとの入念な調整なしに、この変数を変更しないでください。

**errorEvar**：エラー変数。Data Connectors は、統合ウィザードで DFA クエリ失敗変数用に指定した Analytics 変数名でこの変数を事前設定します。

**timeoutEvent**：タイムアウトイベント。Data Connectors は、統合ウィザードでタイムアウトイベント変数用に指定した Analytics 変数名でこの変数を事前設定します。

**requestURL**：広告情報をクエリするためのリモート DFA ホスト。アドビによる指示のない限り、この値を変更しないでください。

**maxDelay**：JavaScript データコレクションコードが DFA Floodlight サーバーからの応答を待機する時間を指定します（ミリ秒）。サイトのトラフィックに基づく最適な値を見つけるために、この値をテストしてみることをお勧めします。例えば、この値を増やすと、一般に、より多くの DFA データを収集しますが、遅延の間に訪問者がサイトを離れると、ベースの訪問者データを失うリスクが増加します。この値を減少させると、ヒットデータを失うリスクは低くなりますが、Adobe ヒットデータと一緒に送信される DFA データの量は少なくなります。

**visitCookie**：DFA 呼び出しを訪問あたり 1 回に制限するために使用される cookie の名前。

**clickThroughParam**：Integrate モジュールにクリックが発生したことを知らせるクエリ文字列。通常、すべての広告に含まれます。クエリ文字列にこのパラメーターがあると、訪問者が過去 30 分間に既にクエリされていても、DFA Floodlight サーバーにリクエストが発生します。

**newRsidsProp**：（オプション）未使用のトラフィックプロパティ変数にマッピングされます。DFA 統合は、訪問 cookie にこの値を収集および格納して、特定の訪問者のデータを収集したレポートスイートを特定します。このプロパティは、アドビエンジニアリングサービスによるカスタム実装でのみ必要です。

**統合が必要なプラグイン**

コレクションコードの追加は、DFA 統合の操作を向上させる追加のプラグインを組み込みます。

* DFA クエリを訪問あたり 1 回に制限する
* cookie 名に柔軟性を提供する。ほとんどの組織は s_dfa を使用しますが、DFA 統合に任意の有効な cookie 名を使用できます。
* 不要なリダイレクトの排除。ビュースルーデータはリアルタイムに収集されるので、Adobe コレクションサーバーと DFA は、ページビューのたびにデータを交換する可能性があります。このプラグインは、情報が不要な場合にこれらのデータの交換をブロックします。

>[!CAUTION]
>
>不要なDFAクエリを排除するためにプラグインが使用するメカニズムの1つは、ドメインベースの訪問cookieです。複数のドメインにわたる統合レポートスイートは、DFA が影響を受けるビュースルーまたはクリックスルーの後で訪問者がドメインを横断すると、クリックスルーおよびビュースルーデータを水増しします。

