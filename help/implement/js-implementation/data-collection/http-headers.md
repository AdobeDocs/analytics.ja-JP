---
description: HTTP リクエストヘッダーと HTTP 応答ヘッダーは、AppMeasurement によって収集されるデータ以外の追加データを収集するために使用します。この節では、データ収集中に使用するこれらのヘッダーについて説明します。
keywords: Analytics の導入
seo-description: HTTP リクエストヘッダーと HTTP 応答ヘッダーは、AppMeasurement によって収集されるデータ以外の追加データを収集するために使用します。この節では、データ収集中に使用するこれらのヘッダーについて説明します。
seo-title: データ収集HTTPヘッダー
solution: Analytics
title: データ収集HTTPヘッダー
topic: 開発者と導入
uuid: 3325e13c- b300-46e4- a592-3a83ED59718b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データ収集HTTPヘッダー

HTTP リクエストヘッダーと HTTP 応答ヘッダーは、AppMeasurement によって収集されるデータ以外の追加データを収集するために使用します。この節では、データ収集中に使用するこれらのヘッダーについて説明します。

## HTTP リクエストヘッダー {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>ヘッダー</b> </td> 
   <td> <b>使用方法</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>データ収集サーバーによって以前に作成された Cookie を読み取ります。 </p> <p> 2014 年以降、アドビのサーバーでは、アドビが設定した Cookie を除き、サーバーコールに伴うすべての Cookie が破棄されます。アドビの Cookie の一覧については、<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external">Experience Cloud で使用される cookie</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> ブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> OperaMini などの一部のブラウザー向けに正しいブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために、User-Agent の代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> OperaMini などの一部のブラウザー向けに正しいブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために、User-Agent の代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> OperaMini などの一部のブラウザー向けに正しいブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために、User-Agent の代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> OperaMini などの一部のブラウザー向けに正しいブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために、User-Agent の代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> OperaMini などの一部のブラウザー向けに正しいブラウザー、オペレーティングシステムおよびモバイルデバイスを検出するために、User-Agent の代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> オペレーティングシステムを識別するための代替ヘッダーとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> クライアント画面の画面解像度設定の代替ソースとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> クライアント画面の色設定の代替ソースとして使用します。 </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> データ収集リクエストが Web ページのプリフェッチの一部として実行されたことを検出します。 </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> データ収集リクエストが、ブラウザーで Web ページのプレビューの表示中に実行されたことを検出します。 </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> GIF または WBMP イメージを送り返す必要があるかを把握できるように、ブラウザーでサポートされるイメージ形式を識別するために使用します。 </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> データ収集リクエストの送信元のページ URL に関する情報を取得するためのフォールバックとして使用します（クエリ文字列でページ URL が渡されなかった場合、またはクエリ文字列内の値と異なる場合）。 </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> データ収集リクエストをおこなったクライアントの正しい IP アドレスを把握するために使用します。この IP アドレスは、地域、携帯電話会社およびその他のレポートを生成するために使用します。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>動的変数を使用した実装には、上記に挙げられていない他のHTTPリクエストヘッダーで読み取るオプションがあります。

## HTTP 応答ヘッダー {#section_A9C7035198C84037A21A8033CC408F0E}

| **ヘッダー** | **使用方法** |
|---|---|
| Access-Control-Allow-Origin | サーバーに対して、クロスオリジンリソース共有スタイルのデータ収集リクエストのサポートを有効化するために使用します。 |
| Expires | ブラウザーのキャッシュ制御に使用します。 |
| Last-Modified | ブラウザーのキャッシュ制御に使用します。 |
| Cache-Control | ブラウザーのキャッシュ制御に使用します。 |
| Pragma | ブラウザーのキャッシュ制御に使用します。 |
| ETag | ブラウザーのキャッシュ制御に使用します。 |
| Vary | ブラウザーのキャッシュ制御に使用します。 |
| P3P | データ収集リクエストに対するデフォルトまたはカスタムの P3P ポリシーを示します。 |
| Status | コンテンツなしのリクエストの場合に、「SUCCESS」または「FAILURE」のステータスが含まれます。リクエストでコンテンツを返さないように指定されている場合にのみ使用されます。 |
| Reason | コンテンツなしのリクエストの場合に、failure ステータスの理由が含まれます。リクエストでコンテンツを返さないように指定されている場合にのみ使用されます。 |
| Location | データ収集リクエストをおこなっているクライアントを別の URL にリダイレクトするために使用します。例として、訪問者 ID cookie を設定できるかを検出するための cookie ハンドシェイクが挙げられます。 |
| Content-Type | クライアントに送り返すコンテンツのタイプを示します（GIF、テキスト、Javascript など）。 |
| Content-Length | クライアントに送り返すコンテンツのサイズを示します。 |

>[!NOTE]
>
>内部ステータス監視の応答には、その他のHTTPヘッダーを設定できます。これらのヘッダーの一部はブラウザーに返される可能性がありますが、ブラウザーがそのヘッダーを受け取る必要はありません。
