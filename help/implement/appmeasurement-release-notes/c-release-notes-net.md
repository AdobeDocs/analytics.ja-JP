---
description: 'null'
seo-description: 'null'
seo-title: Windows Silverlight、NET、IIS、XBOX
solution: Analytics
subtopic: リリースノート
title: Windows Silverlight、NET、IIS、XBOX
topic: 開発者と導入
uuid: 15c20bca-4886-4d57-9957- fe99743851ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Windows Silverlight、NET、IIS、XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>これらのSDKは、パッケージ化されており、アドビがサポートまたは配布することはできません。

>[!NOTE]
>
>現在のライブラリバージョンを検索するには、デバッグログを有効にします。

## バージョン 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

リリース日：**2014 年 8 月**

* Removed support for the [!DNL Microsoft Silverlight Analytics Framework]. Adobe is no longer supporting or distributing the [!DNL Microsoft Silverlight Analytics Framework] integration for [!DNL AppMeasurement].

* 今後追加される機能をサポートするために、コードの内容を一部変更しました。

## バージョン 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

リリース日：**2013 年 3 月**

* Fixed exception with getting default referrer in [!DNL Silverlight] outside of a browser context and properly exposed SSL property in the [!DNL Microsoft Silverlight Analytics Framework] component.

## バージョン 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

リリース日：**2013 年 2 月**

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

## バージョン 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

リリース日：**2012 年 9 月**

* カスタムの `media.monitor` メソッドを使ってメディア終了イベントを追跡すると、ビデオ完了イベントが送信されないことがありましたが、この問題が修正されました。

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## バージョン 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

リリース日：**2012 年 4 月**

*  [!DNL XBOX].

## バージョン 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

リリース日：**2012 年 2 月**

* [!DNL iOS] Phone 7：offlineThrottleDelay が正しく適用されない問題を修正しました。
* Light Server Call（trackLight）で使用できる変数にタイムスタンプを追加しました。

## バージョン 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

リリース日：**2012 年 1 月**

* v15 の新しいビデオトラッキングで、再生完了（Video Completes）を手動または自動で計測するための新しい s.Media.complete() メソッドが利用できるようになりました。詳しくは、[Adobe Analytics でのビデオの測定](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html)を参照してください。

## バージョン 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* New support and build for [!DNL iOS] Phone platform including offline tracking.
* 追跡データにリクエストを送信する方法を上書きするための doRequest delegate のサポートを追加しました。
* サーバー側の処理ルールを駆動する contextData のサポートを追加しました（v15 のみ）。
* Light Server Call のサポートを追加しました（現在ベータ版のみ）。
* イベントリスト内のカウンターイベントに「1」以外の値を割り当てられるようになりました。
* コンバージョン eVar とコンバージョンイベントを使用してビデオを追跡する新しいメソッドのサポートを追加しました（現在ベータ版のみ）。

