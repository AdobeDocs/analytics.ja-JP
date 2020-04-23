---
description: 訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。
keywords: Analytics Implementation
title: 訪問者の移行
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 訪問者の移行

訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。

訪問者の移行により、訪問者ID cookieをデータ収集ドメインの変更時に保持できます。 データ収集ドメインは、次の理由で変更される場合があります。

* `2o7.net` から `omtrdc.net` に移行するとき（[Regional Data Collection](https://marketing.adobe.com/resources/help/ja_JP/whitepapers/rdc/)）。

* [Experience Cloud の訪問者 ID サービス](https://marketing.adobe.com/resources/help/ja_JP/mcvid/)を導入しようとしており、CNAME／ファーストパーティデータ収集ドメインを `2o7.net` または `omtrdc.net` に移行するとき（[Regional Data Collection](https://marketing.adobe.com/resources/help/ja_JP/whitepapers/rdc/)）。

* `2o7.net` または `omtrdc.net` から CNAME ／ファーストパーティデータ収集に移行するとき（[ファーストパーティ cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-first-party.translate.html)）。

* CNAME間の移動（ドメインの変更）

訪問者移行の設定後、訪問者ID cookieを使用しないで新しいドメインを訪問すると、サーバーは以前のデータ収集ホスト名にリダイレクトし、使用可能な訪問者ID cookieを取得してから、新しいドメインにリダイレクトします。 以前の訪問者でホストIDが見つからない場合は、新しいIDが生成されます。 これは、1回の訪問者で1回のみ発生します。

## 訪問者移行プロセス {#section_FF0C5C5CAEF343FFA1892B29311F7160}

次の表に、リストの移行に必要なタスクを示します。

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タスク </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>準備：</b><a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html"  >カスタマーケアに連絡して</a>、移行するドメインと、有効にする移行期間（30 日、60日または 90 日）を伝えます。安全でないドメインと安全でないドメインを含めてください。 </p> </td> 
   <td colname="col3"> <p>移行元のリスト <i>の正確</i> な構文でドメインを作成します。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>移行ホスト名は、Adobeデータ収集サーバーで設定されます。 変更が行われたら、次の手順の計画を立てるために、カスタマーケアからお知らせします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>設定変更から 6 時間以上経過後：</b>Analytics の JavaScript コード内の <code> s.trackingServer</code> 変数および <code> s.trackingServerSecure</code> 変数を新しいデータ収集サーバーに変更します。 </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Analytics コードの更新直後：</b>サイトをテストして、以前のデータ収集ドメインへのリダイレクトがおこなわれていることを確認します。 </p> </td> 
   <td colname="col3"> <p>Use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. これらのリダイレクトが失敗した場合は、すぐにカスタマーケアに連絡して、移行が正しく設定されていることを確認してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>移行期間全体</b>:前のホスト名のDNSレコードをアクティブなままにします。 </p> </td> 
   <td colname="col3"> <p>以前のホスト名はDNSを通じて解決する必要があります。解決しないと、cookieの移行は行われません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## visitorMigrationKey変数とvisitorMigrationServer変数の廃止 {#section_32FCEE2575944D039EA0FEBFB5814259}

2013 年 3 月をもって、`visitorMigrationKey`、`visitorMigrationServer`、`visitorMigrationServerSecure` の各データ収集変数は廃止され、使用されなくなります。この変数に保存されていたデータは、現在、より安全なアドビサーバーに保存されています。
