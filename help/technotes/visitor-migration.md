---
description: 訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。
keywords: Analytics の実装
title: 訪問者の移行
topic-fix: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 77%

---

# 訪問者の移行

訪問者の移行は、訪問者 ID Cookie をドメイン間で移行するプロセスです。

訪問者を移行することで、データ収集ドメインを変更する際に訪問者 ID cookie を保持することができます。データ収集ドメインは、以下の場合に変更される場合があります。

* `2o7.net`から`adobedc.net`に移動します。

* [Experience Cloud訪問者IDサービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を導入しようとしており、CNAME/ファーストパーティデータ収集ドメインを`adobedc.net`、`2o7.net`、または`omtrdc.net`に移行しようとしています

* CNAME/ファーストパーティデータ収集（[ファーストパーティcookie）](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-first-party.html)に移動します。

* 別の CNAME に移行するとき（ドメインの変更）。

訪問者の移行を設定した後で、訪問者 ID cookie を持たないユーザーが新しいドメインを訪問すると、サーバーは前のデータ収集ホスト名にリダイレクトして、使用できる訪問者 ID cookie をすべて取得した後、新しいドメインに再リダイレクトします。前のホスト名で訪問者 ID が見つからない場合、新しい ID が生成されます。この処理は訪問者 1 人につき 1 回のみ実行されます。

## 訪問者の移行のプロセス  {#section_FF0C5C5CAEF343FFA1892B29311F7160}

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
   <td colname="col1"> <p> <b>準備：</b><a href="https://helpx.adobe.com/jp/marketing-cloud/contact-support.html"  >カスタマーケアに連絡して</a>、移行するドメインと、有効にする移行期間（30 日、60日または 90 日）を伝えます。安全性を確保したドメインもそうでないドメインも必ず含めてください。 </p> </td> 
   <td colname="col3"> <p>移行元のドメインと移行先のドメインの<i>正確な</i>構文をリストにまとめます。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>移行ホスト名はアドビのデータ収集サーバーに設定されます。変更が実施され、次の手順を計画できるようになると、カスタマーケアから通知されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>設定変更から 6 時間以上経過後：</b>Analytics の JavaScript コード内の <code> s.trackingServer</code> 変数および <code> s.trackingServerSecure</code> 変数を新しいデータ収集サーバーに変更します。 </p> </td> 
   <td colname="col3"> <p>この変更を行った後、<a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=en">Experience Cloudデバッガー</a>を使用して、Analyticsイメージリクエストが更新されたデータ収集サーバーに送信されることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Analytics コードの更新直後：</b>サイトをテストして、以前のデータ収集ドメインへのリダイレクトがおこなわれていることを確認します。 </p> </td> 
   <td colname="col3"> <p><a href="../implement/validate/packet-monitor.md">パケットモニター</a>を使用して、初めてサイトにアクセスしたとき、またはcookieを消去した後で、200(OK)HTTPステータスコードの前に2つの302（リダイレクト）HTTPステータスコードが表示されることを確認します。 いずれかのリダイレクトに失敗した場合は、すぐにカスタマーケアに問い合わせて、移行が適切に設定されているかどうか確認してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>移行期間全体</b>：前のホスト名の DNS レコードをアクティブに維持します。 </p> </td> 
   <td colname="col3"> <p>前のホスト名が DNS によって解決されなければ、cookie は移行されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>
