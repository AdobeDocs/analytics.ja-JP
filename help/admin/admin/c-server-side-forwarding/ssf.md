---
description: サーバー側転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。
solution: Audience Manager
title: サーバー側転送の概要
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 100%

---


# サーバー側転送の概要

サーバー側転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

以下の点でデータ収集時のサーバー側転送が改善されました。

* ページからの呼び出し回数が減ります。サーバー側転送では、データが Analytics から転送されるので、[!DNL Audience Manager] のお客様がデータ収集に DIL を使用する必要がなくなりました。DIL の削除とは、`"/event"` 呼び出しを削除することです。呼び出し回数が減ることはページの読み込み時間の改善につながり、サイトのカスタマーエクスペリエンスが向上します。
* Experience Cloud ソリューション間でデータ共有を利用できます。
* Audience Manager コードの実装と導入に関するアドビのベストプラクティスに準拠します。

>[!TIP]
>
>Analytics を使用している現在の Audience Manager のお客様は、サーバー側転送に移行する必要があります。Adobe Analytics と Audience Manager の新しいお客様は、デフォルトのデータ収集および転送方法として（DIL ではなく）サーバー側転送を実装する必要があります。

>[!IMPORTANT]
>EU Cookie コンプライアンス規定により、データ管理者（Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、Adobe Audience Manager（AAM）にサーバー側転送しないようにするオプションが追加されました。新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。この変数を設定すると、同意を受け取るまで、これらのヒットは AAM に送信されません。詳しくは、[GDPR_ePrivacy コンプライアンスおよびサーバー側転送](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md)を参照してください。

サーバー側転送の実装状況を確認するには、以下の検証ステップを実行してください。

## ![step1_icon.png image](assets/step1_icon.png) ECID サービス実装の確認

[Analytics トラッキングリクエスト](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/test-verify.html)を調べて、Experience Cloud ID（ECID）サービスが実装されているかどうかを確認します。

「リクエスト」タブで、ECID 値が設定されていることを確認します。これで、サーバー側転送の前提条件である ID サービスが適切に実装されていることがわかります。

* ECID 値が表示されている場合は、手順 2 に進みます。
* ECID 値が表示されていない場合は、手順 2 に進む前に [ID サービスを実装](https://docs.adobe.com/content/help/ja-JP/id-service/using/implementation/implementation-guides.html)します。

## ![step2_icon.png image](assets/step2_icon.png) サーバー側転送の実装バージョンの確認

[Analytics トラッキングリクエスト](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)を調べて、サーバー側転送のバージョンが既に実装されているかどうかを確認します。

「応答」タブで、応答に Audience Manager データが含まれているかどうかを確認します。応答に従って手順を進めます。

* **Audience Manager からの JSON 応答に「postbacks」や「dcs_region」などの項目が含まれている場合**：何らかの形のサーバー側転送が既に有効になっています。手順 3 に進みます。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：Audience Management モジュールが実装されていますが、サーバー側転送が適切に設定されていません。手順 3 に進みます。
* **2 x 2 の画像**：サーバー側転送および Audience Management モジュールは実装されていません。修正手順を以下に示します。

   * **DIL を使用している AAM のお客様**：以下の 2 つの項目を緊密に連携および調整します。

      1. DIL コードを削除し、[Audience Management モジュール](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)ページのコードをインストールします。
      1. 手順 3 の説明に従って、Analytics 管理 UI でサーバー側転送を有効にします。DIL コードを削除する前にこの設定を有効にすると、データが複製され、Audience Manager に対する追加の請求対象サーバーコールが作成されます。
   * **AAM の新しいお客様** - Audience [Management モジュール](https://docs.adobe.com/content/help/en/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)ページのコードをインストールし、手順 3 に進みます。手順 3 でサーバー側転送を有効にするまでは、データは Audience Manager に送信されません。


## ![step3_icon.png image](assets/step3_icon.png) レポートスイートのサーバー側転送の実装の確認

従来のトラッキングサーバーアプローチではなく、サーバー側転送がレポートスイートレベルで実装されているかどうかを確認します。

レポートスイートレベルでのサーバー側転送は、Analytics から共有するデータをより細かく制御できるので、従来のトラッキングサーバーアプローチよりも推奨されます。これは Audience Analytics 統合の前提条件でもあります。

**Analytics**／**管理者**／**レポートスイート**／（**レポートスイート**&#x200B;を選択）／**設定を編集**／**一般**／**サーバー側転送**&#x200B;に移動します。このチェックボックスが

* **非アクティブ**&#x200B;の場合（項目を選択できないか、メニューが存在しない場合）：選択されているレポートスイートは Experience Cloud Organization にマップされていません。[レポートスイートマッピング UI](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html) を使用して、該当するレポートスイートを適切な IMS Org にマップしてください。
* **無効**：新しいサーバー側転送を有効にしていません。ページのコンテンツを読んで、機能を有効にしてください。
* **有効**：新しいサーバー側転送がプロビジョニングされています。この Audience Analytics 統合をセットアップすることもできます。

>[!NOTE]
>
>3 つの手順をすべて実行するまでは、データは他の Experience Cloud ソリューション（[Audience Manager](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/aam-home.html) や [Audiences](https://docs.adobe.com/content/help/ja-JP/core-services/interface/audiences/audience-library.html) など）に表示されません。有効にした後、これらの設定が反映されるまでに数時間かかります。

