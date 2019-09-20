---
description: iOS のこれまでのリリースノートです。
seo-description: iOS のこれまでのリリースノートです。
seo-title: iOS
solution: Analytics,Experience Cloud
subtopic: リリースノート
title: iOS
topic: 開発者と実装
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# iOS{#ios}

iOS のこれまでのリリースノートです。

>[!NOTE]
>
>現在のライブラリバージョンを検索するには、デバッグログをオンにします。

モバイルライブラリのダウンロードは、[GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) と [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios) で入手できます。

[4.x のドキュメント](https://marketing.adobe.com/resources/help/en_US/mobile/ios/)

[3.x のドキュメント](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/)

## バージョン 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

The [!DNL iOS] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>アプリ内メッセージ </p> </td> 
   <td colname="2"> <p> オーディエンスを決定する際に、適切なアプリバージョンが使用されなかった問題を修正しました。この問題は、ユーザーが新しいライフサイクルを開始せずにアプリバージョンをアップグレードした場合に発生していました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 獲得 </p> </td> 
   <td colname="2"> <p> （ドキュメントの推奨により）アプリインストール時の Apple Search Ads データの API 呼び出しをおこなう前に、3 秒の遅延を追加しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

The [!DNL iOS] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>アプリ内メッセージ </p> </td> 
   <td colname="2"> <p> VoiceOver の実行時にフルスクリーンメッセージを無効にできるようになりました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> データベースへの読み取り専用アクセスの処理を改善しました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>一般 </p> </td> 
   <td colname="2"> <p> アプリグループの使用中にバックグラウンドからトラッキングメソッドを呼び出すとクラッシュすることがある問題を修正しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

The [!DNL iOS] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 訪問者 ID サービス </p> </td> 
   <td colname="2"> <p> Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 設定 </p> </td> 
   <td colname="2"> <p> <code>setAdvertisingIdentifier:</code> を介して SDK に渡される無効な IDFA（00000000-0000-0000-0000-000000000000）は無視されます。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> ディープリンク </p> </td> 
   <td colname="2"> <p><code>trackAdobeDeepLink</code> を呼び出す際に、「<code>adb</code>」および「<code>ctx</code>」のプレフィックスが付いた変数が適切に処理されるようになりました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 獲得 </p> </td> 
   <td colname="2"> <p>Apple Search Ads からのデータが、獲得データとともに送信されるようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

The [!DNL iOS] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 獲得 </p> </td> 
   <td colname="2"> <p> カスタム獲得データが <code>AdobeDataCallback</code> の呼び出しによって適切に返されるようになりました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p><span class="keyword">訪問者 ID サービス</span>のパラメーターが、<span class="keyword">Target</span> リクエストで <code>mboxParams</code> を介して渡されるようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**バグの修正**

* [!DNL Adobe Analytics] にトラッキングヒットを送信するのと同時に新しい ID を訪問者 ID サービスと同期しようとするとクラッシュが発生する問題を修正しました。
* Fixed an issue that was causing build warnings when targeting [!DNL iOS] versions older than 8.

## バージョン 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

The [!DNL iOS] SDK version 4.13.0 (Sep 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>アプリ内メッセージ </p> </td> 
   <td colname="2"> <p>新機能：ディープリンク URI を開く、新しいメッセージタイプが追加されました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

The [!DNL iOS] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>訪問者 ID サービス </p> </td> 
   <td colname="2"> <p> 特定の URL に訪問者 ID を追加して、Web ベースの実装に ID を転送する新しい方法が追加されました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>アプリ内メッセージ </p> </td> 
   <td colname="2"> <p>カスタムのフルスクリーンメッセージの HTML タグで「target」属性を「_blank」に設定したときにクラッシュが発生する問題を修正しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

The [!DNL iOS] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target メソッド </p> </td> 
   <td colname="2"> <p>次の新しい <span class="keyword">Target</span> メソッドを使用できます。 </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

The [!DNL iOS] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target メソッド </p> </td> 
   <td colname="2"> <p>次の新しい <span class="keyword">Target</span> メソッドを使用できます。 </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code> targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>TVJS メソッド </p> </td> 
   <td colname="2"> <p>次の新しい <span class="keyword">Target</span> TVJS メソッドを使用できます。 </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code> targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>TVML／TVJS 対応の Adobe Target </p> </td> 
   <td colname="2"> <p><code>ADBTarget</code> 要素を設定する際に、次のプロパティ名を使用できます。 </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code>purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

The [!DNL iOS] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>ディープリンク </p> </td> 
   <td colname="2"> <p>アプリケーションにディープリンクを実装すると、アプリや Web 内の特定のページにユーザーを誘導することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

The [!DNL iOS] SDK version 4.8.6 (March 9, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>アプリのクラッシュを追跡 </p> </td> 
   <td colname="2"> <p>The <span class="keyword"> iOS</span> SDK version 4.8.6 contains critical changes that prevent false crashes from being reported. バージョン 4.8.6 に更新することを強くお勧めします。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

The [!DNL iOS] SDK version 4.8.5 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>オプトアウトおよびプライバシー設定 </p> </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> SDK 4.8.5, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span>, and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

The [!DNL iOS] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新しいExperience cloud訪問者IDサービスのメソッド </td> 
   <td colname="2"> <p>次の新しいメソッドが追加されました。 </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p><code>visitorSyncIdentifiers:identifiers</code> メソッドが <code>visitorSyncIdentifiers:</code> に変更されました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新しい TVJS メソッド </td> 
   <td colname="2"> <p>次の新しいメソッドが追加されました。 </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新しい ADBMobile JSON 設定変数 </td> 
   <td colname="2"> <p>次の変数が追加されました。 </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

The [!DNL iOS] SDK version 4.7.0 (October 15, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> tvOS のサポート </td> 
   <td colname="2"> <p>tvOS は、Apple TV 用にサポートされています。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> App Transport Security のサポート </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> 9, Apple introduced App Transport Security, a set of requirements that conforms to best practices for secure connections. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap プラグインのメソッド</span> </p> </td> 
   <td colname="2"> <p>次の新しいメソッドが追加されました。 </p> <p><b>設定メソッド</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>トラッキングメソッド</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>新しい Target メソッド： </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>獲得メソッド</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Audience Manager メソッド</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>訪問者 ID サービスメソッド</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>App Extensions と Apple Watch メソッド</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

The [!DNL iOS] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> <span class="keyword">Adobe Mobile Services</span> および <span class="keyword">Adobe Mobile</span> SDK を使用すると、<span class="keyword">Analytics</span> セグメントにプッシュメッセージを送信できます。また、SDK では、プッシュメッセージを開いた結果としてアプリを開いたユーザーを簡単にレポートできます。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>獲得メソッド </p> </td> 
   <td colname="2"> <p>開発者は、ユーザーが獲得計測用リンクをクリックしていない場合でも、クリックした場合と同じようにデータを計測することで、アプリ獲得キャンペーンを開始できます。これは、手動で獲得リンクを作成し、自身でアプリストアへのリダイレクトを処理する場合に便利です。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>ポストバック </p> </td> 
   <td colname="2"> <p>ポストバックを使用すると、SDK によって収集されたデータを別のサードパーティサーバーに送信できます。アプリ内メッセージを表示するために設定するのと同じ条件を活用して、カスタマイズしたデータをサードパーティのサーバーに送信するように SDK を設定できます。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>識別子 </p> </td> 
   <td colname="2"> <p>次の新しい識別子を追加しました。 </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E"><code>trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>WatchOS 2 向けの WatchKit サポート </p> </td> 
   <td colname="2"> <p>WatchOS 2 向けの WatchKit サポートが追加されました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

The [!DNL iOS] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> iOS 拡張機能</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> iOS</span> SDK version 4.5, a new <span class="keyword"> iOS</span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS</span> extension apps. </p> <p>We strongly recommend that you use the <span class="keyword"> iOS</span> SDK rather than using your own wrapper. </p> <p>Apple は、Watch アプリと収容アプリとの通信を可能にする API のセット（収容アプリにリクエストを送信し、応答を受信する）を提供しています。 </p> <p>Watch アプリから収容アプリに辞書としてトラッキングデータを送信し、収容アプリに対してトラッキングメソッドを呼び出してデータを送信することは可能ですが、この方法には限界があります。 </p> <p>ほとんどの場合、Watch アプリの使用時には収容アプリがバックグラウンドで実行されているため、安全に呼び出せるメソッドは <code>TrackActionInBackground</code>、<code>TrackLocation</code>、<code>TrackBeacon</code> の 3 つのみとなります。他のトラッキングメソッドはライフサイクルデータに干渉するので、Watch アプリからデータを送信する際には使用できません。 </p> <p>Even if these three tracking methods meet your requirements, we recommend using the <span class="keyword"> iOS</span> SDK because the SDK for watch app includes all <span class="keyword"> Mobile</span> features except in-app messaging. </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> ライフサイクル指標を含むカスタムデータ </p> </td> 
   <td colname="2"> <p>ライフサイクル指標を含むカスタムコンテキストデータ変数を含めることができるようになりました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon</code> and <code> clearCurrentBeacon</code> calls are now available in <span class="keyword"> PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

リリース日：**2014 年 11 月 25 日**

* 新機能 — Adobe Experience Cloud IDの統合
* デバッグログを改良して明確化しました。

## バージョン 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

リリース日：**2014 年 10 月 17 日**

* 新機能 - アプリ内メッセージング機能。
* 新機能 - 設定ファイルの場所をアプリの起動時に指定できるようになりました。
* 新機能 - 新しい設定ファイルを必要とせずに、目標点を自動的に更新できるようになりました。
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* debugLogging が有効な場合、ログメッセージがクリアされ、より詳細なログが追加されます。
* パフォーマンスと安定性に関する強化をいくつかおこないました。

## バージョン 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

リリース日：**2014 年 9 月 19 日**

* Resolved potential crash that could occur if Audience Manager Submit Signal call or [!DNL Target] Load Request call failed due to an unknown network error.

## バージョン 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

リリース日：**2014 年 8 月 6 日**

* privacyStatus:optunknown と offlineEnabled:false という特定の設定で発生する可能性があるデッドロックの問題を解決しました。

リリース日：**2014 年 8 月 5 日**

* リファラーのタイムアウトが 5 秒以下で、オフライントラッキングが無効な場合に、ライフサイクルヒットが送信されなくなる可能性がある問題を解決しました。

リリース日：**2014 年 4 月 18 日**

* Bluetooth ビーコントラッキング。
* アプリ獲得分析。
* タイムスタンプが有効なアプリで、クラッシュのヒットの日付を正しいセッションまで遡ることができます。
* タイムスタンプが有効なアプリで、正しいセッションまで日付を遡ったヒットに含めて以前のセッションを送信できます（以前のセッションではなくなります）。
* ヒットのバッチ処理。

## バージョン 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

リリース日：**2014 年 2 月 21 日**

* 以前のメディアを閉じることなく、連続して同じメディアを開いた場合に不正な動作が発生する問題を解決しました。

## バージョン 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

リリース日：**2014 年 1 月 31 日**

* データベースが破損すると複数のヒットが送信される可能性がある問題を解決しました。
* デバイスの時間設定が正しくない場合に、セッション長の平均が大きくなる可能性がある問題を解決しました。

## バージョン 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

リリース日：**2014 年 1 月 31 日**

* デバイスの時間設定が正しくない場合に、セッション長の平均が大きくなる可能性がある問題を解決しました。

## バージョン 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

リリース日：**2013 年 9 月 28 日**

[!DNL iOS] Experience cloudソリューション用SDK 4.xが、次の新機能を提供できるようになりました。

* 大幅なパフォーマンス強化。すべての処理をバックグラウンドスレッドで実行します。SDK は完全にスレッドセーフです。
* 位置情報と目標点
* ライフタイム値
* 経過時間イベント
* オプトイン／オプトアウト管理
* Audience Manager サポート
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* コンテキストデータおよび処理ルールを標準化

## バージョン 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

リリース日：**2013 年 9 月 24 日**

* ARM64 および X64 シミュレーターアーキテクチャ（iPhone 5s）用のサポートが追加されました。

## バージョン 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

リリース日：**2013 年 8 月 17 日**

* 使用しないコードを削除することによって最適化しました。
* clearVars をスレッド化シナリオで使用する場合に発生する可能性がある潜在的なクラッシュを修正しました。

## バージョン 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

リリース日：**2013 年 8 月 7 日**

* Adobe Audience Manager のサポートを追加しました。
* Lifecycle data is now sent with [!DNL Target] Mbox requests when lifecycle tracking is enabled.

## バージョン 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

リリース日：**2013 年 6 月 21 日**

* Fixed a bug introduced in 3.1.7 that was causing issues with lifecycle on devices below [!DNL iOS] 5.0.

## バージョン 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

リリース日：**2013 年 5 月 24 日**

* 位置通知とアプリを起動するニューススタンド通知を介してライフサイクルヒットが送信されすぎないようにするためのコードが追加されました。

## バージョン 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

リリース日：**2013 年 4 月 19 日**

* 以前のセッションの長さが誤って計算されることがある問題を修正しました。

## バージョン 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

リリース日：**2013 年 3 月 22 日**

* `ADMS_Measurement.visitorID` がデフォルト値で事前設定されるようになりました。

## バージョン 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

リリース日：**2013 年 2 月 22 日**

* 非推奨だった `offlineThrottleDelay` の設定は、スレッドの最適化によって不要になりました。この設定は後方互換性のために引き続き保持されますが、効果は何もありません。

## バージョン 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

リリース日：**2012 年 11 月**

* Products 変数を手動で設定した場合に発生する可能性がある EXEC_BAD_Access の問題を修正しました。
* mbox タイムアウト時に発生する可能性がある無効なセレクターのクラッシュを修正しました。
* 広告トラッキングサポートがメディア測定に追加されました。

## バージョン 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

リリース日：**2012 年 10 月**

* `lifecycleSessionTimeout` 設定変数を追加しました。この変数によって、アプリケーションを再起動する際に、新しいセッションが認識されるのに必要な経過時間を秒単位で指定できます。
* 測定オブジェクトに設定されたイベントによって、メディアモジュールで設定されたイベントが上書きされる問題を修正しました。
* Fixed an issue that caused an exception when allocating an mbox through the [!DNL Target] integration.

## バージョン 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

リリース日：**2012 年 9 月**

* armv7 アーキテクチャのサポートを追加しました。
* armv6 アーキテクチャのサポートを廃止しました。
* Minimum supported [!DNL iOS] SDK is now 4.3

## バージョン 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

リリース日：**2012 年 8 月**

* メディアモニターの delegate を使用したときに、終了イベントが 2 つ表示されることがなくなりました。
* 終了ヒットによってメディアモニターがループ状態になる問題が解決されました。

## バージョン 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

リリース日：**2012 年 7 月**

初回リリース。

**機能強化**

* 「自動追跡」の機能を追加しました。
* ライブラリのサイズを、最終ビルドで約 90K に縮小しました。
* 「trackEvents」メソッドと「trackAppState」メソッドを追加しました。
* コンテキストデータのサポートと機能を改善しました（送信されたすべての情報にコンテキストデータを使用することをお勧めします）。
* トラッキングが簡素化され、基本的なトラッキングの実装を 5 分で完了できるようになりました。

**変更点**

* [!DNL AppMeasurement] クラスが ADMS_Measurement になりました。
* ADMS_Measurement は固有の Singleton として機能します。
* eVar、prop、list、hier、pev の getter と setter を変更しました。
* "track" コールに渡される変数は、すべてこのコールの間だけ存続します。

**次の変数を変更しました。**

| 以前（バージョン 2.x） | 現在（バージョン 3.x） |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| server | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**次の変数を再利用しました。**

* linkURL（trackLinkURL: と共に送信される）
* linkName（trackLinkURL: と共に送信される）
* linkType（trackLinkURL: と共に送信される）
* lightProfileID（trackLight: と共に送信される）
* lightStoreForSeconds（trackLight: と共に送信される）
* lightIncrementBy（trackLight: と共に送信される）
* trackingServerSecure（SSL がオンのときに trackingServer が使用される）

**次の変数を削除しました。**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referrer
* linkLeaveQueryString
* usePlugins
* useBestPractices（AutoTracking で処理される）
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## 以前の iOS バージョン（2.x） {#section_5F76C3DA854D4BAEA636A68B3811142B}

The following release notes apply to the 2.x version of [!DNL AppMeasurement] for [!DNL iOS]. できれば、3.x のバージョンにアップグレードすることをお勧めします。

## バージョン 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

リリース日：**2012 年 4 月**

*  のビデオ測定のサポートを追加しました。
* linktrackvars と コンテキストデータに関する問題を解決しました。
* その他のパフォーマンス強化をいくつか行いました。

## バージョン 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

リリース日：**2012 年 3 月**

* 状況によって、オフラインデータが一部送信されなくなることがある問題を修正しました。

## バージョン 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

リリース日：**2012 年 2 月**

* トラッキングコールを複数のスレッドから同時に実行しようとすると、状況によっては EXC_BAD_ACCESS 例外が発生することがありましたが、この問題は修正されました。
* Light Server Call（trackLight）で使用できる変数にタイムスタンプを追加しました。

## バージョン 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

リリース日：**2012 年 1 月**

* スレッド処理の改善によりパフォーマンスが大幅に向上されました。
* iCloud のベストプラクティスに準拠するように、オフラインヒットのストレージを iCloud に同期されない場所に移動しました。
* ライブラリを Apple FAT バイナリ形式に変更しました。これにより、ビルドアーキテクチャで特定のライブラリを含める必要がなくなりました。

## バージョン 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

リリース日：**2011 年 11 月**

* Added support for [!DNL iOS] 5.
* [!DNL AppMeasurement] for では、非推奨の UDID の値が訪問者 ID のデフォルト値として使用されなくなりました。[!DNL iOS]アプリケーションでオリジナルの訪問者 ID を設定する場合（例：`s.visitorID = @12345`）、この変更による影響はありません。オリジナルの訪問者 ID を設定しない場合、訪問者 ID は初回起動時に生成され、その後 User Defaults データベースに格納されます。This key is used by [!DNL AppMeasurement] from that point forward. また、このキーはアプリケーションの標準的なバックアッププロセスでも保存、復元されます。

* Updated calls from the [!DNL iOS] Best Practices plug-in that are not associated with a page view to send hits using trackLink. これにより、trackLink 測定時にページビューがデフォルト値の「アプリケーションの名前／バージョン」で記録されなくなりました。

## バージョン 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

リリース日：**2011 年 10 月**

* delegate 処理を改善しました。This fixes an issue that caused the [!DNL iOS] Best Practices Plug-in to crash when bringing the application out of the background.

## バージョン 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

リリース日：**2011 年 9 月**

* header での prop と eVar 51 ～ 75 の使用を有効にしました。

## バージョン 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

リリース日：**2011 年 8 月**

* レポートの実行時にレポートスイートおよび指標を検索できる機能を追加しました。
* サーバー側の処理ルールを駆動する contextData のサポートを追加しました（v15 のみ）。
* Light Server Call のサポートを追加しました（現在ベータ版のみ）。

