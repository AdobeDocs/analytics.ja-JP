---
description: 現在導入している環境を移行するために実行する必要のあるタスクの一覧について、表に示します。
keywords: Analyticsの導入;appMeasurement;移行;移行、javascript
seo-description: 現在導入している環境を移行するために実行する必要のあるタスクの一覧について、表に示します。
seo-title: JavaScript 版 AppMeasurement への移行
solution: Analytics
subtopic: JavaScript AppMeasurement
title: JavaScript 版 AppMeasurement への移行
topic: 開発者と導入
uuid: 5be345a8-5a95-4176- a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# JavaScript 版 AppMeasurement への移行

現在導入している環境を移行するために実行する必要のあるタスクの一覧について、表に示します。

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) プラグインの互換性のチェック

場所:s\_ code. js

一部のプラグインはサポートされなくなりました。[AppMeasurementプラグインのサポート](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) を参照してください。

![](assets/step2_icon.png) 新しい AppMeasurement のダウンロード

場所:管理者/コードマネージャー

ダウンロードする zip ファイルには、圧縮された AppMeasurement.js ファイルと、メディアモジュールおよび統合モジュール向けの Javascript ファイルが含まれています。

![](assets/step3_icon.png) s\_ code. jsのカスタマイズをコピー `AppMeasurement.js`します。

場所:s\_ code. jsおよびAppMeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) （オプション）プラグインの更新

場所:AppMeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) （オプション）メディアモジュールと統合モジュールの更新

場所:AppMeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) 新しい JavaScript の導入

場所:Webサイト

社内の標準プロセスに従って、新しい JavaScript ファイルを導入します。既存のページコードはこのバージョンと互換性があります。