---
description: 訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。
keywords: Analytics の実装
seo-description: 訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。
seo-title: 訪問者の移行
solution: Analytics
title: 訪問者の移行
topic: 開発者と実装
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 訪問者の移行

訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。

訪問者を移行することで、データ収集ドメインを変更する際に訪問者 ID cookie を保持することができます。データ収集ドメインは、以下の場合に変更される場合があります。

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* [Experience cloud訪問者IDサービスを導入していて](https://marketing.adobe.com/resources/help/en_US/mcvid/) 、CNAME/ファーストパーティのデータ収集ドメインをまたは `2o7.net` (地域データ収集 `omtrdc.net`[](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))に移行しようとしている。

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* 別の CNAME に移行するとき（ドメインの変更）。

訪問者の移行を設定した後で、訪問者 ID cookie を持たないユーザーが新しいドメインを訪問すると、サーバーは前のデータ収集ホスト名にリダイレクトして、使用できる訪問者 ID cookie をすべて取得した後、新しいドメインに再リダイレクトします。前のホスト名で訪問者 ID が見つからない場合、新しい ID が生成されます。この処理は訪問者 1 人につき 1 回のみ実行されます。

## 訪問者の移行のプロセス {#section_FF0C5C5CAEF343FFA1892B29311F7160}

以下の表に、訪問者の移行に必要なタスクを示します。

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タスク </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>準備：</b><a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external">カスタマーケアに連絡して</a>、移行するドメインと、有効にする移行期間（30 日、60日または 90 日）を伝えます。安全性を確保したドメインもそうでないドメインも必ず含めてください。 </p> </td> 
   <td colname="col3"> <p>移行元のドメインと移行先のドメインの<i>正確な</i>構文をリストにまとめます。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>移行ホスト名はアドビのデータ収集サーバーに設定されます。変更が実施され、次の手順を計画できるようになると、カスタマーケアから通知されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>設定変更から 6 時間以上経過後：</b>Analytics の JavaScript コード内の <code> s.trackingServer</code> 変数および <code> s.trackingServerSecure</code> 変数を新しいデータ収集サーバーに変更します。 </p> </td> 
   <td colname="col3"> <p>この変更をおこなった後、<a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local">パケットアナライザー</a>を使用して、Analytics イメージリクエストが更新されたデータ収集サーバーに送信されることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Analytics コードの更新直後：</b>サイトをテストして、以前のデータ収集ドメインへのリダイレクトがおこなわれていることを確認します。 </p> </td> 
   <td colname="col3"> <p><a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local">パケットアナライザー</a>を使用して、初めてサイトにアクセスしたときや cookie を消去した後に、200（OK）HTTP ステータスコードの前に 2 つの 302（リダイレクト）HTTP ステータスコードが表示されていることを確認してください。いずれかのリダイレクトに失敗した場合は、すぐにカスタマーケアに問い合わせて、移行が適切に設定されているかどうか確認してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>移行期間全体</b>：前のホスト名の DNS レコードをアクティブに維持します。 </p> </td> 
   <td colname="col3"> <p>前のホスト名が DNS によって解決されなければ、cookie は移行されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## visitorMigrationKey 変数と visitorMigrationServer 変数の廃止 {#section_32FCEE2575944D039EA0FEBFB5814259}

2013 年 3 月をもって、`visitorMigrationKey`、`visitorMigrationServer`、`visitorMigrationServerSecure` の各データ収集変数は廃止され、使用されなくなります。この変数に保存されていたデータは、現在、より安全なアドビサーバーに保存されています。
