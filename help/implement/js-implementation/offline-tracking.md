---
description: 以下の変数と関数を使用して、アプリケーションがオフラインの間に実行された測定コールを格納できます。
keywords: Analytics の導入
seo-description: 以下の変数と関数を使用して、アプリケーションがオフラインの間に実行された測定コールを格納できます。
seo-title: オフライン追跡
solution: Analytics
title: オフライン追跡
topic: 開発者と導入
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# オフライン追跡

以下の変数と関数を使用して、アプリケーションがオフラインの間に実行された測定コールを格納できます。

>[!NOTE]
>
>オフライン追跡を有効にするには、レポートスイートでタイムスタンプを有効にする必要があります。レポートスイートでタイムスタンプが有効になっている場合、`trackOffline` 設定プロパティを&#x200B;*必ず* true に設定してください。レポートスイートでタイムスタンプが有効になっていない場合、`trackOffline` 設定プロパティを&#x200B;*必ず* false に設定してください。このプロパティを適切に設定しなければ、データが失われます。レポートスイートのタイムスタンプが有効になっているかどうか判断できない場合は、[カスタマーケアにお問い合わせください](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

オフラインでの AppMeasurement を有効にすると、次のような動作になります。

* アプリケーションによりサーバーコールが送信されますが、データの送信が失敗します。
* AppMeasurement により、現在のヒットのタイムスタンプが生成されます。
* AppMeasurement ではヒットデータがバッファーされ、データの消失を防ぐために、バッファーされたヒットデータが永続的なストレージにバックアップされます。

後続のヒットがあるたびに、または `offlineThrottleDelay` で定義された間隔で、AppMeasurement により、元のヒット順を維持しながら、バッファーされたヒットデータの送信が試行されます。データの送信に失敗すると、引き続きヒットデータがバッファーされます（この動作は、デバイスがオフラインの間継続します）。

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> プロパティまたはメソッド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>デフォルト：false </p> <p>測定ライブラリのオフライン追跡を有効または無効にします。 </p> <p> <b>例：</b> </p> 
    <code class="syntax c">s. trackOffline= true; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>デフォルト：no limit </p> <p>キューに格納されるオフラインヒットの最大数。 </p> <p> <b>例：</b> </p> 
    <code class="syntax c">s. offlineHitLimit=100; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>デフォルト：0 </p> <p>AppMeasurement がアクティブなネットワーク接続を検出したときにバッファ内のヒットデータを送信するサイクル（遅延時間）をミリ秒単位で指定します。これにより、複数のヒットを送信することで生じるアプリケーションのパフォーマンス低下を緩和します。 </p> <p>例えば、offlineThrottleDelay=1000 のとき、ヒットデータの送信に 300ms かかった場合、AppMeasurement はバッファ内の次のヒットを送信する前に 700ms 待機します。 </p> 
    <code class="syntax c">s. offlineThrottleDelay=1000; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> 測定オブジェクトのオンライン状態またはオフライン状態を手動で設定します。デバイスがオフラインであるかオンラインであるかは、ライブラリで自動的に検出されます。したがって、これらのメソッドは、測定を強制的にオフラインにする場合にのみ必要になります。<code>forceOnline</code> は、手動でオフラインにした後にオンライン状態に戻す場合にのみ使用します。 </p> <p>測定がオフラインの場合： </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> <code>trackOffline</code> が true の場合：ヒットは測定がオンラインになるまで保存されます。 </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> <code>trackOffline</code> が false の場合：ヒットは破棄されます。 </li> 
    </ul> <p> <b>例：</b> </p> 
    <code class="syntax c">s. forceOffline（）;

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
