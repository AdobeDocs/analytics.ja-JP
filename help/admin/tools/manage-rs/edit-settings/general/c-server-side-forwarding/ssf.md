---
description: サーバーサイド転送は、Adobe Analyticsのデータをリアルタイムで他のCXM （顧客体験管理）ソリューションと共有したい顧客向けに設計されています。 サーバーサイド転送を有効にすると、Analyticsはデータを他のCX Enterprise ソリューションにプッシュし、それらのソリューションではデータ収集プロセス中にデータをAnalyticsにプッシュできます。
solution: Analytics
title: サーバーサイド転送の概要
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
TQID: https://experienceleague.adobe.com/O03-5Ovxy3Lq-LZjPOseTpOlCXaS1kwD8n2ZM1yJuxY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 887
ht-degree: 73%

---

# サーバーサイド転送の概要

サーバーサイド転送は、Adobe Analyticsのデータをリアルタイムで他のCXM （顧客体験管理）ソリューションと共有したい顧客向けに設計されています。 サーバーサイド転送を有効にすると、Analyticsはデータを他のCX Enterprise ソリューションにプッシュし、それらのソリューションではデータ収集プロセス中にデータをAnalyticsにプッシュできます。

以下の点でデータ収集時のサーバーサイド転送が改善されました。

* ページからの通話を減らします。 サーバーサイド転送では、データが Analytics から転送されるので、[!DNL Audience Manager] のお客様がデータ収集に DIL を使用する必要がなくなりました。 DIL の削除とは、`"/event"` 呼び出しを削除することです。 呼び出し数を減らすことで、ページの読み込み時間を短縮し、サイトの顧客体験を向上できます。
* CX エンタープライズソリューション間のデータ共有を活用できます。
* Audience Managerのコードの実装とデプロイメントに関するベストプラクティスに準拠します。

>[!TIP]
>
>Analytics を使用している現在の Audience Manager のお客様は、サーバーサイド転送に移行する必要があります。 Adobe Analytics と Audience Manager の新しいお客様は、デフォルトのデータ収集および転送方法として（DIL ではなく）サーバーサイド転送を実装する必要があります。

>[!IMPORTANT]
>EU Cookie コンプライアンス規定により、データ管理者（Analytics のお客様）には、同意前のデータを Adobe Analytics に限定して、Adobe Audience Manager にサーバーサイド転送しないようにするオプションが追加されました。 新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。 この変数を設定すると、同意を受け取るまで、これらのヒットは Adobe Audience Manager に送信されません。 詳しくは、[GDPR_ePrivacy コンプライアンスおよびサーバーサイド転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)を参照してください。

サーバーサイド転送の実装状況を確認するには、以下の検証ステップを実行してください。

## ![step1_icon.png image](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step1_icon.png) ECID サービス実装の確認

[Analytics トラッキングリクエスト](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=ja)を調べて、Experience Cloud ID（ECID）サービスが実装されているかどうかを確認します。

「リクエスト」タブで、ECID 値が設定されていることを確認します。 これで、サーバーサイド転送の前提条件である ID サービスが適切に実装されていることがわかります。

* ECID 値が表示されている場合は、手順 2 に進みます。
* ECID 値が表示されていない場合は、手順 2 に進む前に [ID サービスを実装](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=ja)します。

## ![step2_icon.png image](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step2_icon.png) サーバーサイド転送の実装バージョンの確認

[Analytics トラッキングリクエスト](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)を調べて、サーバーサイド転送のバージョンが既に実装されているかどうかを確認します。

「応答」タブで、応答に Audience Manager データが含まれているかどうかを確認します。 応答に従って手順を進めます。

* **Audience Manager からの JSON 応答に「postbacks」や「dcs_region」などの項目が含まれている場合**：何らかの形のサーバーサイド転送が既に有効になっています。 手順 3 に進みます。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：Audience Management モジュールが実装されていますが、サーバー側転送が適切に設定されていません。 手順 3 に進みます。
* **2 x 2 の画像**：サーバーサイド転送および Audience Management モジュールは実装されていません。 これを修正するには：

   * **DIL を使用している Adobe Audience Manage のお客様**：以下の 2 つの項目を緊密に連携および調整します。

      1. DIL コードを削除し、[Audience Management Module](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja) ページコードをインストールします。
      1. 手順 3 の説明に従って、Analytics 管理 UI でサーバーサイド転送を有効にします。 DIL コードを削除する前にこの設定を有効にすると、データが複製され、Audience Managerに対する課金サーバーコールが追加されます。

   * **Adobe Audience Manager の新しいお客様** - [Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja)ページのコードをインストールし、手順 3 に進みます。 手順 3 でサーバーサイド転送を有効にするまでは、データは Audience Manager に送信されません。

## ![step3_icon.png image](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step3_icon.png) レポートスイートのサーバーサイド転送の実装の確認

従来のトラッキングサーバーアプローチではなく、サーバーサイド転送がレポートスイートレベルで実装されているかどうかを確認します。

レポートスイートレベルでのサーバーサイド転送は、Analytics から共有するデータをより細かく制御できるので、従来のトラッキングサーバーアプローチよりも推奨されます。 また、このAudience Analyticsとの連携の前提条件でもあります。

**Analytics**／**管理者**／**レポートスイート**／（**レポートスイート**&#x200B;を選択）／**設定を編集**／**一般**／**サーバー側転送**&#x200B;に移動します。 このチェックボックスが

* **非アクティブ**（選択できないか、メニューが存在しない）：組織 ID にマッピングされたレポートスイートが選択されていません。 レポートスイートが正しくマッピングされていることを確認するには、カスタマーケアにお問い合わせください。
* **無効**：新しいサーバーサイド転送を有効にしていません。 ページ上のコンテンツを読み、機能の有効化に進みます。
* **有効**：新しいサーバーサイド転送がプロビジョニングされています。 Audience Analyticsとの連携も設定できます。

>[!NOTE]
>
>3つの手順がすべて完了するまで、[Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=ja)や[Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja)などの他のCX Enterprise ソリューションにはデータは表示されません。 有効にした後、これらの設定が反映されるまでに数時間かかります。
