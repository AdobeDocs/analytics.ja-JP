---
description: Flash のこれまでのリリースノートです。ActionScript を使用した Flash アプリはデスクトップ上と Web 上で測定できます。
seo-description: Flash のこれまでのリリースノートです。ActionScript を使用した Flash アプリはデスクトップ上と Web 上で測定できます。
seo-title: Flash-Flex
solution: Analytics
subtopic: リリースノート
title: Flash-Flex
topic: 開発者と実装
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Flash-Flex{#flash-flex}

Flash のこれまでのリリースノートです。ActionScript を使用した Flash アプリはデスクトップ上と Web 上で測定できます。

>[!NOTE]
>
>現在のライブラリバージョンを検索するには、デバッグログをオンにします。

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**バージョン 4.0.3 **

* 訪問者 API 1.6.1 を同梱しました。

## 2016 年 8 月 19 日 {#section_D72EF20672174249B864997905D7552A}

** 4.0.2 — アップデート**

訪問者 API 1.6.0 を同梱しました。

## May 19, 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

** 4.0.1 — アップデート**

Visitor API 1.5.6 を同梱しました。

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

アドビは[セキュリティアップデート APSB16-13](https://helpx.adobe.com/security/products/analytics/apsb16-13.html) を、[!DNL AppMeasurement]Flash 版   ライブラリ用にリリースしました。この更新により、`debugTracking` が有効になっているとライブラリが [DOM-based XSS 攻撃](https://www.owasp.org/index.php/DOM_Based_XSS)の実行に悪用されうるという重大な脆弱性が解決されました。

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **影響する場合、`debugTracking`をただちに無効にすることをお勧めします。**&#x200B;以下にサンプルコードを示します。

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 
```

影響を受けるバージョンは、すべてのプラットフォーム向けの すべ [!DNL AppMeasurement] てのプラットフォームでFlashバージョン4.0以前の場合。

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. 既存の AS2 ベースのプロジェクトからのデータ収集は、引き続きサポートされます。ただし、実装を AS3 にアップグレードして [!DNL AppMeasurement]Flash 版   の最新のセキュリティ機能を取り入れることを強くお勧めします。

[!DNL AppMeasurement] この問題の影響を受けるFlashユーザーは、更新されたライブラリを使用してプロジェクトを再構築する必要があります。詳細情報… [!DNL Analytics][](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

バージョン4.0 — アップデート：

* Visitor API 1.5.3 を同梱しました。

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

バージョン4.0 — アップデート：

* Visitor API 1.5.2 を同梱しました。

## August 20, 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

バージョン4.0 — アップデート：

* Visitor API 1.5.1 を同梱しました。

## 2015 年 6 月 18 日 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

バージョン4.0 — アップデート

* Visitor API 1.5 を同梱しました。
* 顧客 ID および認証済み状態を収集し、データ収集リクエストとともにそれらの ID を送付するには、Visitor API 1.5 以降の getCustomerIDs メソッドを使用してください（AN-102131）。

## 2015 年 5 月 22 日 {#section_F5EFCC451F13499F9AA53326AE5926F1}

バージョン3.9.2 — アップデート：

* Visitor API 1.4 を同梱しました。

## 2015 年 2 月 19 日 {#section_95ADF1725CE7415D956944A28182E69B}

バージョン 3.9.2:

* Visitor API 1.3.5 を同梱しました。
* 最初のトラッキングコールの後、自動リファラートラッキングを実行しないように変更されました。これにより、最初のトラッキングコールの前に *`s.referrer`* が手動で設定された場合に、2 回目、3 回目などのトラッキングコール（通常はリンクトラッキング）で、リファラーを二重にカウントしなくなります。（AN-92647）
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

バージョン 3.9.1:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access).
* 訪問者 ID サービス 1.3.2 の新機能がサポートされました。

## 2014 年 8 月 22 日 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

バージョン 3.9:

* 緯度および経度変数が追加されました。
* 訪問者 ID サービス 1.3.1 の新機能がサポートされました。

## バージョン 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

リリース日：**2014 年 6 月 20 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 訪問者 ID サービス 1.3 の新機能がサポートされました。

## バージョン 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

リリース日：**2014 年 4 月 18 日**

* [Experience cloud訪問者IDサービスのサポート](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## バージョン 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

リリース日：**2014 年 3 月 14 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## バージョン 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

リリース日：**2014 年 2 月 7 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## バージョン 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

リリース日：**2013 年 11 月 15 日**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## バージョン 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

リリース日：**2013 年 10 月 18 日**

* [ハートビートビデオトラッキング](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)がサポートされます。
* [訪問者 ID サービス](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)をサポートするため、VisitorAPI.swc を同梱しました。
* ActionScript 3 を使用した Flash Player 9 のサポートが廃止されました。ActionScript 3 の最小 Flash Player バージョンは 10 です。

## バージョン 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

リリース日：**2013 年 9 月 19 日**

* 今後のベータ版リリースをサポートするために、コードの内容を一部変更しました。

## バージョン 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

リリース日：**2013 年 8 月 16 日**

* オフライントラッキングが無効の場合、失敗したリクエストのキューへの再格納が無効になります。

## バージョン 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

リリース日：**2013 年 2 月 22 日**

* ActionScript 2 での URL のエンコードとデコードの問題を修正しました。

## バージョン 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

リリース日：**2013 年 2 月 1 日**

* アドビのデータ収集サーバーのページ URL フィールドのサイズ拡大に対応するために、255 バイトを超える URL の送信のサポートを追加しました。Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. これにより、ブラウザーを切り捨てる場合に長い URL が他のデータより優先されないようにする一方、長い URL の収集を引き続き有効にすることができます。

* 訪問者の新たな識別方法が追加されました。[個別訪問者の識別](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)を参照してください。
* `abort` フラグを新しく追加しました。このフラグは `doPlugins` 内で設定できます。このフラグを true に設定すると、対象のトラッキング呼び出しで [!DNL AppMeasurement] ライブラリが続行しません。abort フラグはあらゆるトラッキング呼び出しによってリセットされるので、後続のトラッキング呼び出しも中止する必要がある場合は、このフラグを再度 `doPlugins` 内に設定する必要があります。

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   これにより、追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。

## バージョン 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

リリース日：**2012 年 11 月 9 日**

* Internal updates for [!DNL Audience Manager] integration.

## バージョン 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

リリース日：**2012 年 10 月 23 日**

* ActionScript 3 ビルドでは常に UTF-8 が使用されるようになったので、`s.charSet` の設定がすべて無視されるようになりました。

## バージョン 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012**
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. 波括弧を使った変数のバインディングは、主に次のような XML タグを使って OSMF ビデオプレイヤーを設定する場合に使います。

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

`autoBind` という新しい属性が追加されました。これを使用して、次のように XML タグで囲まれたデフォルトの動作を上書きすることができます。

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

`autoBind` を `false` に設定すると、XML タグで囲まれた値がリテラル文字列であると認識され、変数のバインディングが使用されません。この属性が `false` に設定されていない場合は、XML タグで囲まれた部分の動作は変わりません。

**ActionScript コードへの影響**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. 次に例を示します。

```
s.eVar1 = "{source}";
```

変数のバインディングを使用している場合は、このコードで新しい `bindVariable` メソッドを使用するよう変更する必要があります。

```
s.bindVariable("eVar1","source");
```

場所ごとに変更する代わりに、`autoBindVariablesByValue` を true に設定してバージョン 3.5 よりも前のバージョンの動作に戻すこともできます。

```
s.autoBindVariablesByValue = true;
```

**その他の修正点：**

* カスタムの `media.monitor` メソッドを使ってメディア終了イベントを追跡すると、ビデオ完了イベントが送信されないことがありましたが、この問題が修正されました。

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## バージョン 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

リリース日：**2012 年 7 月 20 日**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## バージョン 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

リリース日：**2012 年 6 月 22 日**

* AS3 ビルドでは常に UTF-8 が使用されるよう変更されました。これにより、一部の 2 バイト言語での文字列の問題が解消されます。

## バージョン 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

リリース日：**2012 年 4 月 27 日**

ビデオ測定：Brightcove プレイヤー API から異なる完了オフセットが報告された場合の処理を追加しました。オフセットがゼロと報告された場合、完了に対して長さをオフセットとして使用します。これにより、オフセット値を使用して完了を追跡する新しいメソッドに伴う問題が修正されました。

## バージョン 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

リリース日：**2012 年 1 月 20 日**

* v15 の新しいビデオトラッキングで、再生完了（Video Completes）を手動または自動で計測するための新しい s.Media.complete() メソッドが利用できるようになりました。

## バージョン 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

リリース日：**2011 年 9 月 9 日**

* prop にリテラルのゼロ値（「0」）を含めることができるようになりました。以前は、リテラルのゼロ値を含む prop は送信されませんでした。

## バージョン 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

リリース日：**2011 年 5 月**

* OSMF で、OSMF ビデオプレイヤーの追跡時にプロキシプラグインを使用したときの問題を修正しました。これにより、OSMF の ProxyElements がプロキシしている要素が追跡されていない場合も、この ProxyElements を追跡できるようになります。
* Flash Player 9.0.16 上のビデオの測定時にエラーが発生する問題を修正しました。

