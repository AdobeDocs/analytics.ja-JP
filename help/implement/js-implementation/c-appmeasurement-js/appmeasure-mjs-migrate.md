---
description: 現在導入している環境を移行するために実行する必要のあるタスクの一覧について、表に示します。
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
subtopic: JavaScript AppMeasurement
title: JavaScript 版 AppMeasurement への移行
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 版 AppMeasurement への移行

現在導入している環境を移行するために実行する必要のあるタスクの一覧について、表に示します。

>[!NOTE]
>
>JavaScript 版 [!DNL AppMeasurement] に移行する場合は、[ID サービス](/help/implement/js-implementation/c-unique-visitors/visid-service.md) に移行することをお勧めします。

![](assets/step1_icon.png) プラグインの互換性のチェック

次の場合：s\_code.js

一部のプラグインはサポートされなくなりました。「[AppMeasurement プラグインのサポート](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)」を参照してください。

![](assets/step2_icon.png) 新しい AppMeasurement のダウンロード

ここで、Analytics／管理者／コードマネージャー

ダウンロードする zip ファイルには、圧縮された AppMeasurement.js ファイルと、メディアモジュールおよび統合モジュール向けの Javascript ファイルが含まれています。

![](assets/step3_icon.png)s\_code.js のカスタマイズを `AppMeasurement.js` に貼り付けます。

次の場合：s\_code.js と AppMeasurement.js

s\_code.js で `DO NOT ALTER ANYTHING BELOW THIS LINE` セクションの前に表示されたべてのコードを、AppMeasurement.js の先頭に移動します。

![](assets/step4_icon.png)（オプション）プラグインの更新

次の場合：AppMeasurement.js

getQueryParam プラグインを使用している場合は、このプラグインの呼び出し部分で、新しいユーティリティ [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md) を使用するように更新します。

![](assets/step5_icon.png)（オプション）メディアモジュールおよび統合モジュールの更新

次の場合：AppMeasurement.js

これらのモジュールのいずれかを使用している場合は、AppMeasurement\_Module\_Media.js と AppMeasurement\_Module\_Integrate.js のコードをコピーして、AppMeasurement.js の`DO NOT ALTER ANYTHING BELOW THIS LINE` の AppMeasurement.js の直前に貼り付けます。

![](assets/step6_icon.png) 新しい JavaScript の導入

次の場合：Web サイト

社内の標準プロセスに従って、新しい JavaScript ファイルを導入します。既存のページコードはこのバージョンと互換性があります。
