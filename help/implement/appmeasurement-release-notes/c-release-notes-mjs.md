---
description: JavaScript 版 AppMeasurement のこれまでのリリースノートです。
subtopic: Release notes
title: JavaScript 版 AppMeasurement
topic: Developer and implementation
uuid: 1440013d-d266-4dce-9807-8b9adac73315
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript{#appmeasurement-for-javascript} 版 AppMeasurement

JavaScript 版 [!DNL AppMeasurement] のこれまでのリリースノートです。

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

各ライブラリの最新バージョンは、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL コードマネージャー]**&#x200B;からダウンロードできます。

## バージョン 2.17.0

リリース日：**2019 年 8 月 23 日**

| 機能／修正 | 説明 |
| -----------| ---------- |
| Baidu サポートの追加 | Baidu クエリ文字列の並べ替えのサポートが追加されました。 |
| フィルタリングされたレポートの見出しとして、変数名でなく、「 | オプトインの待機中にキューに登録されたヒットの訪問者の値が更新されない問題を修正しました。 |

## バージョン 2.16.0

リリース日：**2019 年 8 月 16 日**

| 機能 | 説明 |
| -----------| ---------- |
| `sendBeacon` が離脱リンクをサポート | [!UICONTROL AppMeasurement] による離脱リンク計測において、ブラウザーの `sendBeacon` 機能が活用されるようになりました。これにより、離脱リンクトラッキングの精度が向上し、コール数が増加することがあります。`SendBeacon` は、ページのコンテキストではなく、ブラウザーのコンテキストで実行されます。`sendBeacon` ページがでアンロードされても、リクエストは完了します。離脱リンクのリクエストが完了する可能性が高くなるので、離脱リンクで非常に役立ちます。 |
| ECID/fid の値 | ECID/fid の値は、オプトイン設定が変更された場合でも、最初のヒット時にキャッシュされるようになりました。 |
| DIL 9.3 | Audience Management モジュールを DIL 9.3 に更新しました。 |
| リーチトラッキングのスクロール | スクロールリーチのトラッキングをオン／オフするための s.ActivityMap.trackScrollReach の設定が追加されました。 |
| 訪問者 ID サービス 4.4.0 | 訪問者 ID サービス 4.4.0 を使用するようになりました。 |

## バージョン 2.15.0

リリース日：**2019 年 7 月 16 日**

* Activity Map 拡張機能に ActivityMap スクロールリーチトラッキングが追加されました。（AN-172949）
* AppMeasurement に DIL 9.2 が追加されました（AN-182472）

## バージョン 2.14.0

リリース日：**2019 年 5 月 22 日**

* 複数のヒットが保留中の場合のトラッカーパラメーターの状態の管理の問題を修正しました。（AN-176931、AN-176629、DTM-12758）
* AppMeasurement を更新し、Visitor.js 4.3.0 が含まれるようになりました（AN-180049）

## バージョン 2.13.0

リリース日：**2019 年 4 月 11 日**

clearVars で報告された多くの問題を修正しました。この問題は、トラッカーの準備が整う前にヒットが送信された場合に発生します。トラッカーの準備が整うと、ライブラリは、既にクリアまたは変更された変数を設定できます。（AN-176931、AN-176629、DTM-12758）

## バージョン 2.12.0

リリース日：**2019 年 2 月 23 日**

* Audience Management モジュールを DIL 9.1 に更新しました。（AN-175255）
* GTM セキュリティポリシーにより Activity Map モジュールが許可されない問題を解決しました。（AN-174679）
* オプトインで ID サービスが承認されない場合、オプトアウトを受け入れるよう AppMeasurement を改善しました。（AN-175259）

## バージョン 2.11.0

リリース日：**2019 年 2 月 12 日**

* AppMeasurement に新しい Adobe オプトインサービス機能のサポートが追加されました。（AN-163546）
* セッションストレージにリンクトラッキングデータを保存するためのサポートが追加されました。（AN-162272）
* Audio Analytics にメディアストリームタイプのサポートが追加されました。（AN-173265）

## バージョン 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

リリース日：**2019 年 9 月 21 日**

このリリースでは、[!DNL AppMeasurement] ライブラリがすべての接続タイプに対して Cookie を適切に送信するようになります。

* [!DNL AppMeasurement] は、POST 中の Cookie の送信をブロックします。（AN-165538）
* XドメインRequest のドロップをサポートします。（AN-165733）
* [!DNL AppMeasurement] のデフォルトの Cookie の有効期間を 5 年から 2 年に短縮します。（AN-158572）
* コードマネージャー（[!DNL AppMeasurement]）からメディアモジュールを削除します。（AN-166590）

## バージョン 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

リリース日：**2018 年 5 月 25 日**

> [!NOTE][!DNL Experience Cloud] ID サービスを使用している場合、訪問者 API 3.0 以降が必要です。関連付けられたコードライブラリ（[!DNL at.js] など）が更新された場合は常に、訪問者 API を最新バージョンにアップグレードすることをお勧めします。[!DNL AppMeasurement.js]

* [!DNL AppMeasurement] を更新し、ID のリクエストに更新された Visitor インターフェイスを使用します。（AN-151483）
* リンクトラッキングがオフになるとリンクトラッキング Cookie が書き込みを継続していた問題を修正しました。（AN-156332）
* `registerPreTrackCallback` および `registerPostTrackCallback` が複数回呼び出されるとコールバック関数シグネチャが壊れていた問題を修正しました。（AN-158566）

## バージョン 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

リリース日：**2018 年 4 月 13 日**

* [!DNL AppMeasurement] を更新し、ID のリクエストに更新された Visitor インターフェイスを使用します。（AN-151483）
* リンクトラッキングがオフになるとリンクトラッキングクッキーが書き込みを継続します。（AN-156332）
* [!DNL AppMeasurement] のデフォルトの Cookie の有効期間を 5 年から 2 年に短縮します。（AN-158572）

## バージョン 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

リリース日：**2018 年 3 月 30 日**

訪問者 API 3.1.0（AN-159524）を再びバンドルします。これには、ホットフィックス（CORE-11390、CORE-10634）が含まれます。

## バージョン 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

リリース日：**2018 年 3 月 16 日**

訪問者 API 3.1.0（AN-159524）を再びバンドルします。これには、ホットフィックス（CORE-11390、CORE-10634）が含まれます。

* [!DNL AppMeasurement] v2.8 に VAPI v3.1 をバンドルします。（AN-158353）
* 共有を促進するために、データ収集エンドポイントをリファクタリンクビルドしました。（AN-156647）
* [!DNL AppMeasurement] に要求の往復時間指標を追加しました。（AN-158343）

## バージョン 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

リリース日：**2018 年 1 月 19 日**

* IE 6 ～ 9 のサポートを廃止
* 訪問者 API v3.0.0 を同梱
* DIL v7.00 を同梱

## バージョン 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

リリース日：**2017 年 11 月 10 日**

s_gl が呼び出されると、 ライブラリで正しい[!DNL AppMeasurement]アカウントの組み合わせを設定されないことがあった問題を修正しました。（AN-152153）

## バージョン 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

リリース日：**2017 年 9 月 22 日**

* [!DNL dil.js 6.12]（[!DNL Audience Manager] モジュール）を同梱しました。

* 訪問者 API 2.5.0 を同梱しました。

## バージョン 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

リリース日：**2017 年 8 月 18 日**

* dil.js v6.11 が含まれています。
* 訪問者 API 2.4.0 が含まれています。

## バージョン 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

リリース日：**2017 年 7 月 21 日**

* [!DNL s.Util.getQueryParam] が # を取得していた問題を修正しました。
* [!DNL dil.js] のバージョン 6.10 を追加しました。（AN-145701）

## バージョン 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

リリース日：**2017 年 6 月 9 日**

* 複数の [!DNL AppMeasurement] インスタンス化のサポートが追加されました。（AN-138237）
* 訪問者 API バージョン 2.2.0 を同梱しました。（AN-144042）

## バージョン 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* 最新版の [!DNL dil.js] が含まれています。（AN-140396）
* ページリファラーをオーバーライドする `adobe_mc_ref` パラメーターがサポートされるようになりました。（AN-131920）
* 訪問者 API 2.1.0 が再び含まれました。（AN-140873）
* `mcorgid`パラメーターを追加しました。（AN-139586）
* cp（customerPerspective）パラメーターを追加しました。（AN-140897）

## バージョン 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

リリース日：**2017 年 9 月 3 日**

* 新しいビルドプロセスに移行したので、バージョン番号を 2.0.0 に更新しました。（AN-137878）
* トラッキングの呼び出しがおこなわれる正しいセクションの場所に mboxMCSDID 処理を移動しました。（AN-138483）

## バージョン 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

リリース日：**2017 年 1 月 20 日**

* Visitor API 2.0.0 を含めました。
* Abort のチェックが完了してから SDID が使用されるように、関数の呼び出しとチェックの順序が変更されました。（AN-134364）
* 次のトラッキングコール前フックおよびトラッキングコール後フックが追加されました。（AN-134567）

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   これらの関数は、コールバック（関数）およびそのパラメーターをパラメーターとして取ります。次に例を示します。

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   コールバックは、`requestUrl` およびコールバックの登録時に渡されたパラメーターとともに呼び出されます。コールバックの登録に使用されたメソッドにより、この呼び出しはトラッキングコールの前または後に発生します。これらのコールバックが呼び出される順序は保証されていません。トラッキングコール前フックで登録されるコールバックは、最終トラッキング URL の作成後に呼び出されます。トラッキングコール後フックのコールバックは、トラッキングコールの成功後に呼び出されます（トラッキングコールが失敗すると、コールバックは呼び出されません）。`registerPreTrackCallback` で登録されたコールバックは、トラッキングコールには影響しません。また、登録されたコールバックでいずれかのトラッキングメソッドを呼び出すことは、無限ループの原因となるおそれがあるため、推奨されていません。

## バージョン 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

更新：**2016 年 11 月 11 日**

* 訪問者 API 1.10.1 が含まれています。

## バージョン 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

更新：**2016 年 10 月 21 日**

* [!DNL Audience Manager] モジュールを Demdex 統合ライブラリ（DIL） 6.6 に更新しました。（AN-132065）
* Visitor API 1.9.0 を同梱しました。（AN-132072）

## バージョン 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

更新：**2016 年 9 月 16 日**

* [!DNL AppMeasurement] [!DNL Audience Manager]モジュールが DIL 6.5 と追加設定で更新されました。（AN-129411）

* 訪問者 API 1.8.0 が同梱されました。（AN-129887）

## バージョン 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

更新：**2016 年 8 月 19 日**

* [!DNL AppMeasurement] が更新され、AMCV cookie を読み書きするようになりました。（AN-127098）
* Visitor API 1.7.0 を同梱しました。

> [!NOTE][!DNL JavaScript] バージョン 1.6.3 について次のリリースノートも参照してください。Experience Cloud ID サービスの更新された要件が記載されています。

## バージョン 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

更新：**2016 年 8 月 5 日**

* リクエストの接続が [!DNL AppMeasurement] によって途中で切断される問題を修正しました。（AN-126448）

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Experience Cloud] ID サービスのバージョン 1.6.0 には、[!DNL JavaScript] 版 [!DNL AppMeasurement] のバージョン 1.6.3 以降が&#x200B;*必要です*。Experience Cloud ID サービスのバージョン 1.6.0 にアップグレードする場合は、バージョン 1.6.3 以降の [!DNL AppMeasurement] コードを使用してください。

## バージョン 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

リリース日：**2016 年 7 月 22 日**

* 訪問者 API 1.6.0 を同梱しました。
* [!DNL AppMeasurement] が訪問者 API の不適切な不明化されたメソッドを呼び出してしまう問題を修正しました。（AN-126006）
* 「属性は v:image でのみ有効です」という [!DNL JavaScript] エラーが発生する問題を修正しました。（AN-124009）

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa.
</note>

 -->

## バージョン 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

リリース日：**2016 年 6 月 17 日**

Visitor API 1.5.7 を同梱しました。

## バージョン 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

リリース日：**2016 年 5 月 20 日**

[!DNL JavaScript] バージョン 1.5.6

* Visitor API 1.5.6 を同梱しました。
* Firefox で、完了イベントを発生させないリンククリックのトラッキング処理を修正しました。

## バージョン 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

リリース日：**2016 年 4 月 22 日**

* The [!DNL AppMeasurement] Activity Map module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. Activity Map トラッキングはデフォルトで有効化されます。(AN-112689)

* [!DNL AppMeasurement] 内で、*`pageURLRest`* が最後になるよう、クエリ文字列変数の並び順で発生していた切り捨て問題を修正しました。（AN-114647）

## バージョン 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

リリース日：**2016 年 3 月 18 日**

* Visitor API 1.5.4 を同梱しました。
* Visitor API 1.5.4 以降のオプトアウトがサポートされます。

## バージョン 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

リリース日：**2016 年 1 月 22 日**

* トラッキングコールに POST が使用されている場合の [!DNL Audience Manager] モジュールの処理を修正しました。（AN-115381）
* ページ URL の残り（「-g」）をトラッキングリクエストクエリ文字列の最後に移動しました。（AN-114647）

## バージョン 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

リリース日：**2015 年 11 月 6 日**

* Visitor API 1.5.3 を同梱しました。
* IE11 での URL の文字切れ（2047）の検出を修正しました（AN-114914）。

## バージョン 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

リリース日：**2015 年 9 月 18 日**

* Visitor API 1.5.2 を同梱しました。

## バージョン 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

リリース日：**2015 年 8 月 30 日**

* Visitor API 1.5.1 を同梱しました。

## バージョン 1.5.1 {#section_3C9637EDB058479184731067897E857C}

リリース日：**2015 年 7 月 17 日**

* [!DNL Audience Manager] モジュールが更新され、AAM DIL 6.2 を使用できるようになりました。VisitorAPI.js から getCustomerIDs を実行し、/event 呼び出しで AAM に渡します。（AN-104978）

## バージョン 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

リリース日：**2015 年 6 月 19 日**

* 訪問者 API 1.5（*`getCustomerIDs`* メソッドを使用して顧客 ID および認証済み状態を収集し、データ収集リクエストとともにそれらの ID を送付）のサポート。
* **[!UICONTROL AudienceManagement]** モジュール（DIL 6.1）での重複する送信先 iFrame の作成が修正されました。
* リリース 1.4.5 で説明されている既知の問題を修正しました。

## バージョン 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

リリース日：**2015 年 5 月 22 日**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> iOS 拡張機能</span> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">iOS</span> SDK バージョン 4.5 から、新しい <span class="keyword">iOS</span> 拡張機能によって Apple Watch アプリ、Today ウィジェット、Photo Editing ウィジェットなどの <span class="keyword">iOS</span> 拡張機能アプリから使用データを収集できるようになりました。 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/ios_ext.html">iOS 拡張機能の実装</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android ウェアラブル拡張機能</span> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Android</span> SDK バージョン 4.5 から、新しい <span class="keyword">Android</span> 拡張機能によって <span class="keyword">Android</span> ウェアラブルアプリからデータを収集できるようになりました。 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/android_wearable.html">Android ウェアラブル拡張機能</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

* Visitor API 1.4 を同梱しました。
* AudienceManagement モジュールが更新され、DIL バージョン 6.0 を使用できるようになりました。

**既知の問題**

訪問者 API／[!DNL AppMeasurement] [!DNL Audience Manager]モジュールの統合では、IE6-9 で `//fast.<subdomain>.demdex.net/dest5.html` と `//fast.<subdomain>.demdex.net/dest4.html` の 2つの宛先パブリッシング iFrame リクエストがおこなわれます。正しい動作は、他のブラウザーのように `//fast.<subdomain>.demdex.net/dest5.html` のみを読み込むことです。

## バージョン 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

リリース日：**2015 年 4 月 17 日**

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
   <td colname="1"> <p><span class="keyword">PhoneGap</span> でのビーコントラッキングサポート  </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

`trackLight` 呼び出し後に Light Server Call のプロファイル ID をクリアするように若干の修正をおこないました。

## バージョン 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

リリース日：**2015 年 2 月 20 日**

* 遅延したトラッキングコールのすべての処理を一貫させるようにしました。これにより、クリックされたオブジェクトなど、遅延中のバックアップ変数の問題を修正しました。
* 最初のトラッキングコールの後、自動リファラートラッキングを行わないように変更されました。これにより、最初のトラッキングコールの前に  *`s.referrer`* が手動で設定された場合に、2 回目、3 回目などのトラッキングコール（通常はリンクトラッキング）で、リファラーを二重にカウントしなくなります。
* 配布 zip を更新して Visitor API 1.3.5 を含めました。

## バージョン 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

リリース日：**2015 年 1 月 16 日**

* 非表示のプリレンダリングページを追跡していなかった WebKit プリレンダリング処理を修正しました。
* 配布 zip を更新して Visitor API 1.3.4 を含めました。同梱の最新の **[!UICONTROL AudienceManagement]** モジュールには DIL バージョン 5.5 が含まれています。

## バージョン 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

リリース日：**2014 年 9 月 19 日**

* `tagContainerMarker` 変数が追加されました。これにより、区切りのダッシュ文字と共にバージョン文字列に追加される最大 4 文字を指定して導入できます。これは、Dynamic Tag Management で使用されます。

   ```js
   // JavaScript 
   s.tagContainerMarker = "D1.0"; 
   
   // Data Collection request 
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   この 4 文字は、英数字とピリオドなど、URL ファイルパスで許可される文字に制限されます。

* H コードの 2 重タグのあるページで、強制のリンクトラッキングが有効の場合（Webkit ブラウザーのデフォルト）、自動リンクトラッキング（ダウンロードおよび出口）中に発生していたループを修正しました。また、同様のループを防ぐために、自動リンクトラッキングに一般的な保護を追加しました。この保護は、同じ&#x200B;**&#x200B;オブジェクトに対する 10 秒に 1 回の繰り返しクリックの自動リンクトラッキングに限定されます。この保護は、自動リンクトラッキングにのみ適用されるので、手動リンクトラッキング（s.tl）呼び出しは制限されません。別のオブジェクトへのクリックも、この保護の影響は受けず、トラッキングされます。
* 遅延が必要な場合のクリックされたオブジェクトの処理を修正しました。
* s.t がリンク onclick 関数から呼び出されて、訪問者 API が必要な値をまだ持っていない場合、ページビューカウントが倍になる問題を修正しました。
* HTTP POST をサポートします。

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_implement.html) implementation for Experience Cloud.

## バージョン 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

リリース日：**2014 年 8 月 22 日**

* バージョン 15 ではプラグインのレポートは存在しないため、ブラウザープラグインの追跡（`p` クエリパラメーター）は削除されました。
* ダウンロード用 zip に **[!UICONTROL AudienceManagement]** モジュールが追加されました。

[追加された eVar](https://marketing.adobe.com/resources/help/en_US/sc/implement/evars_events.html)（76 ～ 250）およびイベント（101 ～ 1000）のサポートが追加されました。

> [!NOTE]H コード は、追加の eVar およびイベントをサポートしていません。

[!DNL JavaScript]

## バージョン 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

リリース日：**2014 年 6 月 20 日**

* 訪問者関連の API フィールド（従来の [!DNL Analytics] 訪問者 ID など）の done および waiting フラグの取り扱いでエラーが生じる問題を修正しました。
* 訪問者 ID サービス 1.3 の新機能がサポートされました。

## バージョン 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

リリース日：**2014 年 5 月 23 日**

* [!DNL JavaScript] 版 [!DNL AppMeasurement] の `s_gi` 関数が、H コードの `s_gi` を使用して作成されたインスタンスを正しく検索できない問題を修正しました。この問題は、[!DNL JavaScript] 版 [!DNL AppMeasurement] および H コードが同じページの別のインスタンスで存在し、インスタンスの検索にレポートスイートで `s_gi` が使用されているデュアルタグ実装にのみ影響します。

## バージョン 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

リリース日：**2014 年 4 月 18 日**

* [Experience cloud訪問者IDサービスのサポート](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## バージョン 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

リリース日：**2014 年 3 月 14 日**

* ハートビートビデオのバグを修正しました。

## バージョン 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

リリース日：**2014 年 2 月 21 日**

* ハートビートビデオのバグを修正しました。

## バージョン 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

リリース日：**2014 年 2 月 7 日**

* [!DNL Audience Manager] の DIL モジュールとの互換性の問題を修正しました。[!DNL Audience Manager] ユーザーは、DIL モジュールのバージョン 4.8 にアップデートする必要もあります。

## バージョン 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

リリース日：**2013 年 11 月 16 日**

* [ハートビートビデオ測定](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)に使用するページイベントを修正しました。

## バージョン 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

リリース日：**2013 年 11 月 15 日**

* [ハードビートビデオ指標](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)のサポートが追加されました。
* [!DNL VisitorAPI.js] 訪問者IDサービスをサポートす [るために追加されました](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html)。

## バージョン 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* 「opera:」で始まるリンクについて（「opera:」は他のブラザーの「about:」および「chrome:」と同じ）、リンクトラッキング呼び出しが Opera ブラウザーから送信されませんでした。
* Accessible Video and Communications Act に準拠するために、すべての画像オブジェクトに `alt=""` が追加されました。

## バージョン 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

リリース日：**2013 年 9 月 19 日**

* ライブラリとページコードを `head` タグに配置できない不具合を修正しました。
* `onLoad` のサポートを追加しました。

## バージョン 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

リリース日：**2013 年 8 月 16 日**

* Adobe Tag Management を使用したデプロイメントのサポートを追加しました。
* 階層変数が [!DNL AppMeasurement] オブジェクトで設定されない問題を修正しました。

## バージョン 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

リリース日：**2013 年 7 月 19 日**

* 自動リンク追跡でハッシュ／フラグメントが無視されるようになりました。以前は、次の URL が自動的にダウンロードリンクとして追跡されていました。これは、`href` 全体が `.pdf` で終わるためです。

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   現在はハッシュ／フラグメントが無視されるので、ファイル名の拡張子が一致する場合にのみリンクが追跡されます。

## バージョン 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

リリース日：**2013 年 5 月 24 日**

新しい [!DNL JavaScript] 版 [!DNL AppMeasurement] ライブラリがコードマネージャーで使用できるようになりました。このライブラリは [!DNL s_code.js] と同じ機能を提供しますが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。

* H.25 コードと比較して 3 倍 ～ 7 倍も高速
* わずか 21K の非圧縮コード、8K の gzip 圧縮コード（H.25 コードでは、33K もの非圧縮コード、13K の gzip 圧縮コード）
* クエリパラメーターの取得、Cookie の読み取り／書き込み、高度なリンクトラッキングの実行をネイティブサポート。
* モバイルサイトで使用できるほど軽量かつ高速で、フルデスクトップ Web で使用できるほど堅牢。1 つのライブラリを Web 環境全体で活用できます。

詳しくは、 導入ガイドの [JavaScript 版 AppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html) を参照してください。[!DNL Analytics]

> [!NOTE]一部のプラグインは今回の新しいバージョンではサポートされていません。詳しくは、[プラグインのサポート](https://marketing.adobe.com/resources/help/en_US/sc/implement/plugins_support.html)を参照してください。
