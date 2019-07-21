---
description: Android モバイルライブラリのこれまでのリリースノートです。
seo-description: Android モバイルライブラリのこれまでのリリースノートです。
seo-title: Android
solution: Analytics、Marketing Cloud
subtopic: リリースノート
title: Android
topic: 開発者と導入
uuid: 32232d28-3459-4f78- bb00- ca3163c63461
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Android{#android}

Android モバイルライブラリのこれまでのリリースノートです。

>[!NOTE]
>
>現在のライブラリバージョンを検索するには、デバッグログを有効にします。

モバイルライブラリのダウンロードは、[GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) と [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1) で入手できます。

## バージョン 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

[!DNL Android] SDKバージョン4.13.4（2017年2月17日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> アプリ内メッセージ </p> </td> 
   <td colname="2"> <p> オーディエンスを決定する際に、適切なアプリバージョンが使用されなかった問題を修正しました。この問題は、ユーザーが新しいライフサイクルを開始せずにアプリバージョンをアップグレードした場合に発生していました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>ライフサイクル </p> </td> 
   <td colname="2"> <p> アプリバージョンのアップグレードが適切にレポートされない場合があった問題を修正しました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>獲得 </p> </td> 
   <td colname="2"> <p> 最初の起動時にディファードディープリンクがトリガーされない原因となっていたバグを修正しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

[!DNL Android] SDKバージョン4.13.3（2017年1月20日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> アプリ内メッセージ </p> </td> 
   <td colname="2"> <p> クリックスルーボタンがないとアラートメッセージが表示されない問題を修正しました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> データベースへの読み取り専用アクセスの処理を改善しました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>ユニバーサルリンク </p> </td> 
   <td colname="2"> <p> 獲得データに関連付けられたディファードディープリンクが連続起動時に実行される原因となっていたバグを修正しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

[!DNL Android] SDKバージョン4.13.2（2016年11月11日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 訪問者 ID サービス </p> </td> 
   <td colname="2"> <p><code>adobe_mc</code> パラメーターにタイムスタンプと Marketing Cloud 組織 ID が追加されました。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> ディープリンク </p> </td> 
   <td colname="2"> <p><code>trackAdobeDeepLink</code> を呼び出す際に、「<code>adb</code>」および「<code>ctx</code>」のプレフィックスが付いた変数が適切に処理されるようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

[!DNL Android] SDKバージョン4.13.1（2016年10月21日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>獲得 </p> </td> 
   <td colname="2"> カスタム獲得データが <code>AdobeDataCallback</code> の呼び出しによって適切に返されるようになりました。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>獲得 </p> </td> 
   <td colname="2"> Google Play リファラー変数とカスタム変数が格納され、<code>AdobeDataCallback</code> の呼び出しによって適切に返されるようになりました。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target  </p> </td> 
   <td colname="2"> 訪問者 ID サービスのパラメーターが、<span class="keyword">Target</span> リクエストで <code>mboxParams</code> を介して渡されるようになりました。 </td> 
  </tr> 
 </tbody> 
</table>

**バグの修正**

* 電話に対するデータリクエストが時折タイムアウトになるバグを修正しました。

## バージョン 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

[!DNL Android] SDKバージョン4.13.0（2016年9月16日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>ディープリンクの追跡 </p> </td> 
   <td colname="2"> <p>新機能：サードパーティのディファードディープリンクの追跡を有効化する機能が追加されました。 </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

[!DNL Android] SDKバージョン4.12.0（2016年8月19日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
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
 </tbody> 
</table>

## バージョン 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

[!DNL Android] SDKバージョン4.11.0（2016年6月23日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

[!DNL Android] SDKバージョン4.10.0（2016年5月21日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Target メソッド </td> 
   <td colname="2"> <p><code>loadRequest</code> メソッドの新しい構文と例を追加しました。 </p> <p>次の新しい <span class="keyword">Target</span> メソッドを追加しました。 </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

[!DNL Android] SDKバージョン4.9.0（2016年5月6日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> オプトアウトおよびプライバシー設定 </td> 
   <td colname="2"> <p>アプリケーションにディープリンクを実装すると、アプリや Web 内の特定のページにユーザーを誘導することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

[!DNL Android] SDKバージョン4.8.3（2016年2月19日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> オプトアウトおよびプライバシー設定 </td> 
   <td colname="2"> <p><span class="keyword"> Android</span> SDK4.8.3以降、 <code> setPrivacyStatus</code> メソッドを使用したプライバシー設定は <span class="keyword"> 、Analytics</span>、 <span class="keyword"> Target</span> および <span class="keyword"> Audience Managerのアクティビティに影響</span>します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

[!DNL Android] SDKバージョン4.8.0（2015年11月3日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新しい Marketing Cloud 訪問者 ID サービスメソッド </td> 
   <td colname="2"> <p>次のメソッドが追加されました。 </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新しい ADBMobile JSON 設定変数 </td> 
   <td colname="2"> <p>次の変数が追加されました。 </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> PhoneGap プラグインのメソッド</span> </td> 
   <td colname="2"> <p>次の新しいメソッドを追加しました。 </p> <p><b>設定メソッド</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Target メソッド</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

[!DNL Android] SDKバージョン4.6.1（2015年9月25日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android SDK バージョン 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

[!DNL Android] SDKバージョン4.6（2015年9月18日）には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> セグメントへのプッシュメッセージ </p> </td> 
   <td colname="2"> <p><span class="keyword">Adobe Mobile Services</span> および <span class="keyword">Adobe Mobile</span> SDK を使用すると、<span class="keyword">Analytics</span> セグメントにプッシュメッセージを送信できます。また、SDK では、プッシュメッセージを開いた結果としてアプリを開いたユーザーを簡単にレポートできます。 </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

[!DNL Android] SDKバージョン4.5には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 機能 </th> 
   <th colname="2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android ウェアラブル拡張機能</span> </p> </td> 
   <td colname="2"> <p><span class="keyword"> Android</span> SDKバージョン4.5以降、Android <span class="keyword"></span> の <span class="keyword"></span> ウェアラブルアプリからデータを収集することができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

[!DNL Android] SDKバージョン4.4には、次の変更が含まれています。

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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
   <td colname="2"> <p><code> trackBeacon</code> 呼び出しと <code> clearCurrentBeacon</code> 呼び出しがPhoneGapで <span class="keyword"> 使用できる</span>ようになりました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## バージョン 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

リリース日：**2014 年 11 月 25 日**

* 新機能 - Adobe Marketing Cloud ID 統合
* デバッグログを改良して明確化しました。
* アプリ内メッセージ確認時の潜在的なクラッシュを解決しました。

## バージョン 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

リリース日：**2014 年 10 月 17 日**

* 新機能 - アプリ内メッセージング機能。
* 新機能 - 設定ファイルの場所をアプリの起動時に指定できるようになりました。
* 新機能 - 新しい設定ファイルを必要とせずに、目標点を自動的に更新できるようになりました。
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* 特定のシナリオで、アプリのクラッシュがトラッキングされない可能性がある問題を解決しました。
* debugLogging が有効な場合、ログメッセージがクリアされ、より詳細なログが追加されます。
* パフォーマンスと安定性に関する強化をいくつかおこないました。

## バージョン 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

リリース日：**2014 年 8 月 5 日**

* リファラーのタイムアウトが 5 秒以下で、オフライントラッキングが無効な場合に、ライフサイクルヒットが送信されなくなる可能性がある問題を解決しました。

## バージョン 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

リリース日：**2014 年 7 月 18 日**

* データベースが破損した場合または作成できなかった場合に発生する例外に対する保護を強化しました。
* （一般的には null のコンテキストによって）設定を読み込めない場合に発生する可能性がある問題に対する保護を強化しました。
* 時間指定アクションのコンテキストデータ更新時に発生する可能性がある例外に対する保護を強化しました。

## バージョン 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

リリース日：**2014 年 4 月 24 日**

* リファラートラッキングが有効で、ライフサイクルより前にトラッキングコールがおこなわれる場合に発生する可能性がある潜在的な問題を修正しました。

## バージョン 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

リリース日：**2014 年 4 月 18 日**

* 新機能- Bluetoothビーコントラッキング。
* 新機能-タイムスタンプが有効なアプリで、クラッシュのヒットは正しいセッションまで遡ります。
* 新機能-タイムスタンプが有効なアプリで、以前のセッションが正しいセッションまで遡ったヒットに送信されます。（以前のセッションではなくなります）。
* 新機能-ヒットのバッチ処理。
* Google Playリファラートラッキングを設定可能なタイムアウトで修正し、Googleリファラーデータが遅延できるように修正。
* 特定のシナリオで発生する可能性のあるStrictModeの警告を解決しました。
* 特定のメソッドが特定の順序で呼び出された場合に、ごくまれにライブラリがロックされる可能性がある問題を解決しました。

## バージョン 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

リリース日：**2014 年 2 月 25 日**

* 停止を呼び出した後、他の呼び出しを挟まずに終了を呼び出した場合に、メディアの再生時間が延長される可能性がある問題を解決しました。
* メディアがまったく再生されていない場合でもメディアの終了ヒットが送信される問題を解決しました。

## バージョン 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

リリース日：**2014 年 2 月 21 日**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## バージョン 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

リリース日：**2014 年 1 月 31 日**

* データベースが破損すると複数のヒットが送信される可能性がある問題を解決しました。
* デバイスの時間設定が正しくない場合に、セッション長の平均が大きくなる可能性がある問題を解決しました。

## バージョン 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

リリース日：**2014 年 1 月 31 日**

* ヒットを繰り返し発生させる、破損したデータベースに対する保護を強化しました。
* デバイスの時刻が正しくない場合にセッションが非常に大きくならないように、最大セッション長制限を追加しました。

## バージョン 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

リリース日：**2013 年 11 月 15 日**

* 特定のロケールでの trackLocation データの不正なフォーマットを解決しました。

## バージョン 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

リリース日：**2013 年 9 月 28 日**

[!DNL Android]Marketing Cloud ソリューション用の SDK 4.x を使用して、以下の新機能を提供できるようになりました。

* 大幅なパフォーマンス強化。すべての処理をバックグラウンドスレッドで実行します。SDK は完全にスレッドセーフです。
* 位置情報と目標点
* ライフタイム値
* 経過時間イベント
* オプトイン／オプトアウト管理
* Audience Manager サポート
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* コンテキストデータおよび処理ルールを標準化

## バージョン 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

リリース日：**2013 年 9 月 24 日**

* パラメーターに null の値またはキーを許可しないという Audience Manager のバグを修正しました。

## バージョン 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

リリース日：**2013 年 9 月 13 日**

* linkTrackEvents のメディアイベントがリクエストに追加されないというバグを修正しました。
* ContextData がトラッキングコールに渡された後に変更されることに関連する潜在的な例外を修正しました。

## バージョン 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

リリース日：**2013 年 8 月 17 日**

* SSL 接続で厳密なホスト検証を使用するようになりました。
* ネットワーク接続が失われ、offlineTracking が無効な場合、直ちにヒットが数秒間再試行されるというバグを修正しました。

## バージョン 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

リリース日：**2013 年 8 月 7 日**

* Adobe Audience Manager のサポートを追加しました。
* ライフサイクル追跡が有効な場合、Target の mbox リクエストとともにライフサイクルデータを送信するようになりました。
* SQLite でカーソルが強制的に終了し、結果的に不必要なログエントリが作成される可能性がある問題を解決しました。

## バージョン 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

リリース日：**2013 年 6 月 14 日**

* SQLite を使用するためにオフラインストレージを更新しました。
* オフライン制限がデフォルト（1000）にリセットされることがあるというバグを修正しました。
* アクティビティまたはアプリケーションコンテキストを承認するように startActivity を更新しました。
* lifecycleSessionTimeout を 0 に設定するとアプリ全体で複数の起動イベントが発生するというバグを修正しました。

## バージョン 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

リリース日：**2013 年 4 月 19 日**

* いくつかの UTF8 文字に関するエンコードの問題を修正しました。

## バージョン 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

リリース日：**2013 年 4 月 19 日**

* 以前のセッションの長さの計算が間違っていることがある問題を修正しました。
* 新しい訪問者 ID は deviceID または subscriberID に基づかなくなります。
* 変数内の特殊文字エンコード時の潜在的なクラッシュを修正しました。

## バージョン 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

リリース日：**2013 年 3 月 22 日**

* 先に設定しておかないと visitorID を読み取れない問題を修正しました。
* いくつかのエラーログメッセージにおける命名規則を変更して明確化しました。
* 混乱を避けるため、いくつかのベースクラスのアクセシビリティを変更しました。
* いくつかの点でパフォーマンスを強化しました。

## バージョン 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

リリース日：**2013 年 2 月 22 日**

* 非推奨だった `offlineThrottleDelay` の設定は、スレッドの最適化によって不要になりました。この設定は後方互換性のために引き続き保持されますが、効果は何もありません。
* オフラインヒットのキャッシュでの同期の潜在的な問題を修正しました。
* #6 以上のヒエラルキー変数を設定したときに表示される警告メッセージをわかりやすくしました。
* [!DNL Android] バージョン4.0でOSVersionが誤ってレポートされる可能性がある問題を修正しました。
* パフォーマンスの強化をいくつか行いました。
* 間違った形式の URL による潜在的な例外の問題を解決しました。

## バージョン 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

リリース日：**2012 年 11 月**

* `lifecycleSessionTimeout` 設定変数を追加しました。この変数によって、アプリケーションを再起動する際に、新しいセッションが認識されるのに必要な経過時間を秒単位で指定できます。
* `lifecycleSessionTimeout` を追加しました。これによって、セッションの長さを計算するときのタイムアウト値を設定できるようになりました。
* セキュリティの問題を修正しました。

## バージョン 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

リリース日：**2012 年 10 月**

* [Google Play キャンペーントラッキング](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/index.html?f=referrer)のサポートを追加しました。

## バージョン 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

リリース日：**2012 年 9 月**

* 終了ヒットによってメディアモニターがループ状態になる問題が解決されました。

## バージョン 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

リリース日：**2012 年 8 月**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## バージョン 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

リリース日：**2012 年 7 月**

初回リリース。

## 以前の Android バージョン（1.x） {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. できれば、3.x のバージョンにアップグレードすることをお勧めします。

## バージョン 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

リリース日：**2012 年 3 月**

* 状況によって、コンテキストデータを使用したデータの受け渡し時に例外が発生することがある問題を修正しました。

## バージョン 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

リリース日：**2012 年 2 月**

リンクトラッキングのコールで pev1 ～ pev3 の値が二重に URL エンコードされる問題を修正しました。

Light Server Call（trackLight）で使用できる変数にタイムスタンプを追加しました。

## バージョン 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

リリース日：**2012 年 1 月**

* [!DNL Android] 3. xと4. xの互換性を追加しました。
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## バージョン 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

リリース日：**2011 年 6 月**

* デバイスに SIM カードが挿入されていない場合は、 の訪問者 ID の値にデバイス ID を使用するようにライブラリを更新しました。デフォルトのライブラリでは購読者 ID が訪問者 ID として使用されますが、SIM カードが挿入されていない場合は購読者 ID が存在しません。

## バージョン 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

リリース日：**2011 年 4 月**

* すべてのタブレット（Xoom を含む）のサポートを追加しました。
* レポートの実行時にレポートスイートおよび指標を検索できる機能を追加しました。
* サーバー側の処理ルールを駆動する contextData のサポートを追加しました（v15 のみ）。
* Light Server Call のサポートを追加しました（現在ベータ版のみ）。
