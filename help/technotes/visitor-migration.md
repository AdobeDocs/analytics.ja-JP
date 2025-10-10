---
description: 訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。
keywords: Analytics の実装
title: 訪問者の移行
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 67%

---

# 訪問者の移行

>[!NOTE]
>
>Experience Cloud訪問者 ID サービスを既に実装している場合は、猶予期間は適用されず、有効にしないでください。

訪問者の移行は、訪問者 ID cookie （s_vi）がドメイン間で移行されるプロセスです。

訪問者を移行することで、データ収集ドメインを変更する際に訪問者 ID cookie を保持することができます。データ収集ドメインは、以下の場合に変更される場合があります。

* `2o7.net` から `adobedc.net` への移行

* [Experience Cloud 訪問者 ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を実装しており、CNAME／ファーストパーティのデータ収集ドメインから `adobedc.net`、`2o7.net` または `omtrdc.net` に移行しています

* cname／ファーストパーティデータコレクション（[ファーストパーティ Cookie）](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja)への移行。

* 別の CNAME に移行するとき（ドメインの変更）。

訪問者の移行を設定した後で、訪問者 ID cookie を持たないユーザーが新しいドメインを訪問すると、サーバーは前のデータ収集ホスト名にリダイレクトして、使用できる訪問者 ID cookie をすべて取得した後、新しいドメインに再リダイレクトします。前のホスト名で訪問者 ID が見つからない場合、新しい ID が生成されます。この処理は訪問者 1 人につき 1 回のみ実行されます。

## 訪問者の移行のプロセス {#process}

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
   <td colname="col1"> <p> <b>準備：</b><a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html"  >カスタマーケアに連絡して</a>、移行するドメインと、有効にする移行期間（30 日、60日または 90 日）を伝えます。非セキュアなドメインとセキュアなドメインを必ず含めてください。 </p> </td> 
   <td colname="col3"> <p>移行元のドメインと移行先のドメインの<i>正確な</i>構文をリストにまとめます。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>移行ホスト名はアドビのデータ収集サーバーに設定されます。変更が実施され、次の手順を計画できるようになると、カスタマーケアから通知されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>設定変更から 6 時間以上経過後：</b>Analytics の JavaScript コード内の <code> s.trackingServer</code> 変数および <code> s.trackingServerSecure</code> 変数を新しいデータ収集サーバーに変更します。 </p> </td> 
   <td colname="col3"> <p>この変更をおこなった後、<a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja">Experience Cloud Debugger</a> を使用して、Analytics 画像リクエストが更新されたデータ収集サーバーに送信されることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Analytics コードの更新直後：</b>サイトをテストして、以前のデータ収集ドメインへのリダイレクトがおこなわれていることを確認します。 </p> </td> 
   <td colname="col3"> <p><a href="../implement/validate/packet-monitor.md">パケットモニター</a>を使用して、初めてサイトにアクセスするとき、または Cookie をクリアした後、200（OK）HTTP ステータスコードの前に 2 つの 302（リダイレクト）HTTP ステータスコードが表示されることを確認します。いずれかのリダイレクトに失敗した場合は、すぐにカスタマーケアに問い合わせて、移行が適切に設定されているかどうか確認してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>移行期間全体</b>：前のホスト名の DNS レコードをアクティブに維持します。 </p> </td> 
   <td colname="col3"> <p>前のホスト名が DNS によって解決されなければ、cookie は移行されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

| タスク | 説明 |
|--- |--- |
| 開始するには：移行するドメインと、有効にする移行期間（30 日、60 日または 90 日）をカスタマーケアにお問い合わせください。 非セキュアなドメインとセキュアなドメインを必ず含めてください。 | 移行先および移行元のドメインの正確な構文でリストを作成します。<ul><li>example.112.2o7.net > metrics.example.com</li><li>example.102.112.2o7.net > smetrics.example.com</li></ul>移行ホスト名はアドビのデータ収集サーバーに設定されます。変更が実施され、次の手順を計画できるようになると、カスタマーケアから通知されます。 |
| 設定変更から 6 時間以上後：新しいデータ収集サーバーを使用するように、Analytics JavaScript コードの `s.trackingServer` 変数と `s.trackingServerSecure` 変数を更新します。 | この変更をおこなった後、[Experience Cloud debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja) を使用して、Analytics イメージリクエストが更新されたデータ収集サーバーに送信されることを確認します。 |
| Analytics コードの更新直後：サイトをテストして、以前のデータ収集ドメインへのリダイレクトがおこなわれていることを確認します。 | [&#x200B; パケットモニター &#x200B;](../implement/validate/packet-monitor.md) を使用して、初めてサイトにアクセスするとき、または Cookie をクリアした後、200 （OK） HTTP ステータスコードの前に 2 つの 302 （リダイレクト） HTTP ステータスコードが表示されることを確認します。 いずれかのリダイレクトに失敗した場合は、すぐにカスタマーケアに問い合わせて、移行が適切に設定されているかどうか確認してください。 |
| 移行期間全体：前のホスト名の DNS レコードをアクティブにしておきます。 | 前のホスト名が DNS によって解決されなければ、cookie は移行されません。 |