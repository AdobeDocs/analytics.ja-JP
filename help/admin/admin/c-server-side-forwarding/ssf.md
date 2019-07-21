---
description: サーバー側転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。
seo-description: サーバー側転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。
seo-title: サーバー側転送の概要
solution: Audience Manager
title: サーバー側転送の概要
uuid: 22ddbde5-6805-4aba-8f82-62772644daa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# サーバー側転送の概要

サーバー側転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバー側転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

以下の点でデータ収集時のサーバー側転送が改善されました。

* ページからの呼び出し回数が減ります。With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. 呼び出し回数が減ることはページの読み込み時間の改善につながり、サイトのカスタマーエクスペリエンスが向上します。
* Experience Cloud ソリューション間でデータ共有を利用できます。
* Audience Manager コードの実装と導入に関するアドビのベストプラクティスに準拠します。

>[!TIP]
>
>Analyticsを使用する現在のAudience Managerユーザーは、サーバー側転送に移行する必要があります。Adobe Analytics と Audience Manager の新しいお客様は、デフォルトのデータ収集および転送方法として（DIL ではなく）サーバー側転送を実装する必要があります。

>[!IMPORTANT]
>EU Cookie コンプライアンス規定により、データ管理者（Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、Adobe Audience Manager（AAM）にサーバー側転送しないようにするオプションが追加されました。新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。この変数を設定すると、同意を受け取るまで、これらのヒットは AAM に送信されません。詳しくは、GDPR_ePrivacy コンプライアンスおよびサーバー側転送を参照してください。

サーバー側転送の実装状況を確認するには、以下の検証ステップを実行してください。

## ![ステップ1_ icon. png画像](assets/step1_icon.png) の検証MIDサービスの実装

[Analytics トラッキングリクエスト](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html)を調べて、Experience Cloud ID（MID）サービスが実装されているかどうかを確認します。

「リクエスト」タブで、MID 値が設定されていることを確認します。これは、IDサービスが正しく実装されていることを示します。これは、サーバー側転送の前提条件です。

* MID 値が表示されている場合は、手順 2 に進みます。
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![ステップ2_ icon. png画像](assets/step2_icon.png) :サーバー側転送の実装バージョンの確認

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](../../../admin/admin/c-server-side-forwarding/ssf-verify.md).

「応答」タブで、応答に Audience Manager データが含まれているかどうかを確認します。以下が表示されます。

* **Audience Manager からの JSON 応答に「postbacks」や「dcs_region」などの項目が含まれている場合**：何らかの形のサーバー側転送が既に有効になっています。手順 3 に進みます。
* **"status":"SUCCESS"**：Audience Management モジュールが実装されていますが、サーバー側転送が適切に設定されていません。手順 3 に進みます。
* **2 x 2 の画像**：サーバー側転送および Audience Management モジュールは実装されていません。修正手順を以下に示します。

   * **DIL を使用している AAM のお客様**：以下の 2 つの項目を緊密に連携および調整します。

      1. DIL コードを削除し、[Audience Management モジュール](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)ページのコードをインストールします。
      1. 手順 3 の説明に従って、Analytics 管理 UI でサーバー側転送を有効にします。DIL コードを削除する前にこの設定を有効にすると、データが複製され、Audience Manager に対する追加の請求対象サーバーコールが作成されます。
   * **AAM の新しいお客様** - Audience [Management モジュール](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)ページのコードをインストールし、手順 3 に進みます。手順 3 でサーバー側転送を有効にするまでは、データは Audience Manager に送信されません。


## ![手順3_ icon. png画像](assets/step3_icon.png) :レポートスイートのサーバー側転送実装の確認

従来のトラッキングサーバーアプローチではなく、サーバー側転送がレポートスイートレベルで実装されているかどうかを確認します。

レポートスイートレベルでのサーバー側転送は、Analytics から共有するデータをより細かく制御できるので、従来のトラッキングサーバーアプローチよりも推奨されます。これは Audience Analytics 統合の前提条件でもあります。

**Analytics** / **管理者** / **レポートスイート** /（レポートスイートを選択 ****）/設定 **を編集** / **一般** / **サーバー側転送**&#x200B;に移動します。このチェックボックスが

* **非アクティブ**&#x200B;の場合（項目を選択できないか、メニューが存在しない場合）：選択されているレポートスイートは IMS Org にマップされていません。[レポートスイートマッピング UI](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html) を使用して、該当するレポートスイートを適切な IMS Org にマップしてください。
* **オフ**&#x200B;の場合：新しいサーバー側転送は有効になっていません。ページのコンテンツを読んで、機能を有効にしてください。
* **オン**&#x200B;の場合：新しいサーバー側転送用にプロビジョニングされています。この Audience Analytics 統合をセットアップすることもできます。

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. 有効にした後、これらの設定が反映されるまでに数時間かかります。

