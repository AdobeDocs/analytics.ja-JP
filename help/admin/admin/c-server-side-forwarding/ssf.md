---
description: サーバー側転送は、Analyticsのデータを他のExperience Cloudソリューションとリアルタイムで共有するお客様向けに設計されています。 また、サーバー側転送を有効にすると、Analyticsが他のExperience Cloudソリューションにデータをプッシュし、データ収集プロセス中にそのソリューションがAnalyticsにデータをプッシュすることもできます。
solution: Audience Manager
title: サーバー側転送の概要
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# サーバー側転送の概要

サーバー側転送は、Analyticsのデータを他のExperience Cloudソリューションとリアルタイムで共有するお客様向けに設計されています。 また、サーバー側転送を有効にすると、Analyticsが他のExperience Cloudソリューションにデータをプッシュし、データ収集プロセス中にそのソリューションがAnalyticsにデータをプッシュすることもできます。

サーバー側転送は、次の理由で、データ収集時の処理を改善します。

* ページからの呼び出しを減らします。 サーバー側転送では、データが Analytics から転送されるので、[!DNL Audience Manager] のお客様がデータ収集に DIL を使用する必要がなくなりました。DIL の削除とは、`"/event"` 呼び出しを削除することです。呼び出し回数が少ないと、ページ読み込み時間が短縮され、サイトでの顧客体験が向上します。
* Experience Cloudソリューション間でのデータ共有を活用できます。
* Omniture Managerコードの実装と導入に関するオーディエンスのベストプラクティスに準拠しています。

>[!TIP]
>
>Analytics を使用している現在の Audience Manager のお客様は、サーバー側転送に移行する必要があります。Adobe Analytics と Audience Manager の新しいお客様は、デフォルトのデータ収集および転送方法として（DIL ではなく）サーバー側転送を実装する必要があります。

>[!IMPORTANT]
>EU Cookie コンプライアンス規定により、データ管理者（Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、Adobe Audience Manager（AAM）にサーバー側転送しないようにするオプションが追加されました。新しい実装コンテキスト変数を使用すると、同意を受け取っていないヒットにフラグを付けることができます。 この変数を設定すると、同意を受け取るまで、これらのヒットがAAMに送信されなくなります。 For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

サーバー側転送の実装状況を確認するには、以下の検証ステップを実行してください。

## ![step1_icon.png image](assets/step1_icon.png) ECID サービス実装の確認

[Analytics トラッキングリクエスト](https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid-test-verify.html)を調べて、Experience Cloud ID（ECID）サービスが実装されているかどうかを確認します。

「リクエスト」タブで、ECID 値が設定されていることを確認します。これで、サーバー側転送の前提条件である ID サービスが適切に実装されていることがわかります。

* ECID 値が表示されている場合は、手順 2 に進みます。
* ECID 値が表示されていない場合は、手順 2 に進む前に [ID サービスを実装](https://marketing.adobe.com/resources/help/ja_JP/mcvid/mcvid-implementation-guides.html)します。

## ![step2_icon.png image](assets/step2_icon.png) サーバー側転送の実装バージョンの確認

[Analytics トラッキングリクエスト](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)を調べて、サーバー側転送のバージョンが既に実装されているかどうかを確認します。

「応答」タブで、応答に Audience Manager データが含まれているかどうかを確認します。応答に従って手順を進めます。

* **Audience Manager からの JSON 応答に「postbacks」や「dcs_region」などの項目が含まれている場合**：何らかの形のサーバー側転送が既に有効になっています。手順 3 に進みます。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：Audience Management モジュールが実装されていますが、サーバー側転送が適切に設定されていません。手順 3 に進みます。
* A **2 x 2画像**:サーバー側転送またはサーバー管理モジュールがオーディエンスされていません。 これを修正するには：

   * **DILを持つAAM顧客**:次の2つの項目を密接に連携させます。

      1. DILコードを削除し、 [オーディエンス管理モジュール](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) ・ページ・コードを
      1. 手順3の説明に従って、Analytics管理UIでサーバー側転送を有効にします。 DILコードを削除する前にこの設定を有効にすると、重複データが生成され、Server Managerに対する追加の課金対象オーディエンスの呼び出しが作成されます。
   * **AAMの新規顧客** - [Step](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) 3に進み、Step Management Moduleページコードをインストールします。 手順3でサーバー側転送がオンになるまで、オーディエンスマネージャーにデータは送信されません。


## ![step3_icon.png image](assets/step3_icon.png) レポートスイートのサーバー側転送の実装の確認

レガシーのトラッキングサーバーアプローチではなく、レポートスイートレベルでサーバー側転送が実装されているかどうかを確認します。

Analyticsから共有されるデータをより細かいレベルで制御できるので、レポートスイートレベルでのサーバー側転送は、従来のトラッキングサーバーアプローチよりも優先されます。 また、このAnalytics統合の前提条件となるオーディエンスです。

**Analytics**／**管理者**／**レポートスイート**／（**レポートスイート**&#x200B;を選択）／**設定を編集**／**一般**／**サーバー側転送**&#x200B;に移動します。このチェックボックスが

* **非アクティブ**&#x200B;の場合（項目を選択できないか、メニューが存在しない場合）：選択されているレポートスイートは Experience Cloud Organization にマップされていません。[レポートスイートマッピング UI](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html) を使用して、該当するレポートスイートを適切な IMS Org にマップしてください。
* **無効**：新しいサーバー側転送を有効にしていません。ページの内容を読み、機能の有効化に進みます。
* **有効**：新しいサーバー側転送がプロビジョニングされています。また、このAnalytics統合を設定するオーディエンスも可能です。

>[!NOTE]3 つの手順をすべて実行するまでは、データは他の Experience Cloud ソリューション（[Audience Manager](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/aam-home.translate.html) や [Audiences](https://marketing.adobe.com/resources/help/ja_JP/mcloud/audience_library.html) など）に表示されません。有効にした後、これらの設定が反映されるまでに数時間かかります。

