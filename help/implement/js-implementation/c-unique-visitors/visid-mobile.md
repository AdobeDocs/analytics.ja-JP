---
description: ほとんどのモバイルデバイスがブラウザー cookie を受け付けます。ただし、デバイスが cookie を受け付けない場合は、別の方法を使用してワイヤレスデバイスを一意に識別します。
keywords: Analytics の導入
seo-description: ほとんどのモバイルデバイスがブラウザー cookie を受け付けます。ただし、デバイスが cookie を受け付けない場合は、別の方法を使用してワイヤレスデバイスを一意に識別します。
seo-title: モバイルデバイスの特定
solution: Analytics
title: モバイルデバイスの特定
topic: 開発者と導入
uuid: 22587dd1- cead-485b- a4d8-94dfb7cd9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# モバイルデバイスの特定

ほとんどのモバイルデバイスがブラウザー cookie を受け付けます。ただし、デバイスが cookie を受け付けない場合は、別の方法を使用してワイヤレスデバイスを一意に識別します。

アドビでは、ほとんどのモバイルデバイスを一意に識別する様々な HTTP [加入者 ID ヘッダー](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D)を識別しています。これらのヘッダーには、デバイスの電話番号（または電話番号をハッシュ化したもの）やその他の識別子が含まれます。現在のほとんどのデバイスには、デバイスを一意に識別する 1 つ以上のヘッダーがあり、アドビのすべてのデータ収集サーバーでは、訪問者 ID の代わりにこれらのヘッダーが自動的に使用されます。

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). ただし、デバイスが HTTP ヘッダーに基づいてモバイルデバイスとして認識される場合は、「1」の代わりに「5」が渡されます。これは、wbmp 形式のイメージを返す必要があることと、認識済みのワイヤレスヘッダーのリスト（cookie ではない）を使用してデバイスを識別する必要があることを示します。

次の表に、パス内の返されるイメージタイプ値（「1」または「5」）に基づいて使用される ID メソッドの順序を示します。

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> ID メソッドの順序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>デフォルト： </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">カスタム訪問者 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">加入者 ID ヘッダー </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP アドレス - ユーザーエージェント - ゲートウェイ IP アドレス </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>デバイスがワイヤレスデバイスとして識別されました。または、<code>/5</code> がイメージリクエストに手動で設定されていました。 </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">カスタム訪問者 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">加入者 ID ヘッダー </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP アドレス - ユーザーエージェント - ゲートウェイ IP アドレス </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

また、「1」または「5」はイメージリクエストに手動で渡すこともできますが、これらのコードは相互に排他的なので、常に「5」を渡すと、cookie がサポートされていても利用されません。デバイスが cookie をサポートしているかを判定できる独自のメカニズムを組み込んで、cookie をサポートしている場合にイメージ内で「5」ではなく「1」を渡すことができます。この状況で改善される精度は、cookie をサポートするモバイルデバイスの数に限られます。

## 加入者 ID ヘッダー {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

cookie には cookie の削除、cookie の承認、ゲートウェイ cookie 管理などに関する問題があるので、一般的に訪問者 ID は cookie よりも信頼性の高いユーザー識別方法です。

モバイル訪問者が使用している携帯電話会社のホワイトリストに追加されると、訪問者識別の変更を改善できます。携帯電話会社の訪問者 ID を利用するには、携帯電話会社に連絡して、ドメインをホワイトリストに追加するように依頼してください。さらに、携帯電話会社のホワイトリストに追加されると、それまでアクセスできなかった加入者 ID ヘッダーにアクセスできるようになります。

以下のヘッダー一覧は、ワイヤレスデバイスを識別するために使用します。ヘッダー処理アルゴリズムは、次の処理をおこないます。

1. HTTP ヘッダーキー（「X-Up-Calling-Line-ID」などのヘッダーの名前）を抽出します。
1. アルファベット（A ～ Z、a ～ z）以外の文字を除去します。
1. ヘッダーキーを小文字に変換します。
1. キーの末尾と次の表の値を比較して一致を見つけます。

| ヘッダー | タイプ | 例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID または IP アドレス | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID または IP アドレス | X-Wap-msisdn: 8032618185 |
| clientip | IP アドレス | Client-ip: 10.9.41.2 |
| wapipaddr | IP アドレス | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | IP アドレス | x-huawei-NASIP: 211.139.172.70 |
| userip | IP アドレス | UserIP: 70.214.81.241 |
| ipaddress | IP アドレス | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | IP アドレス | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

例えば、「callinglineid」は、「X-Up-Calling-Line-ID」および「nokia-callinglineid」に一致します。ヘッダータイプは、ヘッダーの内容を示します。ヘッダーの優先順位はこの表の並びのとおりです（「callinglineid」ヘッダーが存在する場合、そのヘッダーが「subno」の代わりに使用されます）。

次のいずれかを使用できます[動的変数](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)を使用すると、ヘッダーから特定の値を抽出できます。
