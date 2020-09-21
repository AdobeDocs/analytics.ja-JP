---
description: データソースには、オフラインで発生するイベントをオンラインデータに統合する方法がさらに 2 つ用意されています。
subtopic: Data sources
title: トランザクションの統合と顧客の統合
topic: Developer and implementation
uuid: 71f73a47-3436-4314-a182-36de4bd935ba
translation-type: ht
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: ht
source-wordcount: '327'
ht-degree: 100%

---


# トランザクションの統合と顧客の統合

データソースには、オフラインで発生するイベントをオンラインデータに統合する方法がさらに 2 つ用意されています。

* [トランザクション ID の記録の有効化](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C)
* [トランザクションの統合](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_B3F281CEFF9B47E9A07F9851D61D415D)
* [顧客の統合](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_9F4AAD710D2543BDA834090A98115FBF)

これらの統合によって、オフラインデータが特定のオンライントランザクションやオンライン訪問者と関連付けられます。

## トランザクション ID の記録の有効化 {#section_30D6D47AEC0F4A36B87EBFE4C858F20C}

トランザクション ID は、ClientCare にお問い合わせいただかなくても、UI で次の手順を実行して有効／無効にできます。

**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／レポートスイートを選択&#x200B;**[!UICONTROL ／設定を編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 一般的なアカウント設定]**&#x200B;に移動します。

<!-- 

<p>When contacting Customer Care, be prepared to provide the following information: </p> 
<ul id="ul_C425C7A074484650AFCCF0425E8E3F47"> 
 <li id="li_7640C0C4DF0C49749A3C37E5461DC22F">Report Suite ID of the data source for which you need transaction ID recording enabled. <p>In Data Sources, the report suite ID is the first part of the login appended by a random number that identifies the specific data source that was set up. For example, <code> RSID-drmossdev5 Login-drmossdev5_0001343430</code>. </p> </li> 
 <li id="li_4FB0E3EC7BE94A2DBEE9063365A71C9C">The Transaction ID expiration window (described in <a href="/help/import/c-data-sources/datasrc-tid-visitor-profile.md"  > Transaction ID and Visitor Profiles</a>). By default this is 90 days, but it can be extended to up to 2 years. </li> 
</ul>

 -->

トランザクション ID の記録が有効かどうかを確認するには、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL データソース]**&#x200B;に移動します。

![](assets/transaction-ID-recording-active.png)

「[!UICONTROL 管理]」タブにトランザクション ID の記録の状態が表示されます。

## 顧客の統合 {#section_9F4AAD710D2543BDA834090A98115FBF}

顧客 ID を使用すると、顧客のオフラインアクティビティを指定し、このアクティビティをオンラインアクティビティに関連付けることができます。この ID は次のような場合に使用します。

* 顧客 ID が&#x200B;*`visitorID`* 変数にも取り込まれます。
* 顧客のアクティビティがオフラインに移行する（リードの送信、購入など）明確な時点が存在しない。

このタイプのデータソースを設定するには、次を参照してください。[訪問者 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)

## トランザクションの統合 {#section_B3F281CEFF9B47E9A07F9851D61D415D}

トランザクション ID を使用して、ある時点での訪問者の状態を記録することができます。この ID は、顧客が通常エクスペリエンスをオンラインからオフラインに移動する時点がある場合に使用します。例えば次のような場合があります。

* 販売員が顧客と連絡を取れるようにリードを送信する。
* 購入後に店頭での返品が可能なオンライン購入を行う。
* 後でサポートへの問い合わせが発生する可能性がある製品を購入する。

オンラインからオフラインに移行する際、顧客は匿名であることが少なくありません。

トランザクション ID イベントは、（マーケティングレポートに表示される）訪問パーティシペーション指標には含まれませんが、（ad hoc analysis でのみ参照できる）訪問者パーティシペーション指標には含まれます。

これは、トランザクション ID データが訪問とは関連付けられておらず（通常、オフラインイベントはオンラインイベントに含まれないため）、訪問者と関連付けられているからです。

参照：[トランザクション ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)。
