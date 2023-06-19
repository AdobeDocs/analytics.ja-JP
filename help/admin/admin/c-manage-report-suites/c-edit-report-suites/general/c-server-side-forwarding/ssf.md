---
description: サーバーサイド転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバーサイド転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。
solution: Analytics
title: サーバーサイド転送の概要
feature: Server-Side Forwarding
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# サーバーサイド転送の概要

サーバーサイド転送は、Analytics のデータを他の Experience Cloud ソリューションとリアルタイムで共有したいと考えるお客様向けに設計されています。サーバーサイド転送が有効な場合、Analytics が他の Experience Cloud ソリューションにデータをプッシュできるほか、データ収集プロセス中にこれらのソリューションから Analytics にデータをプッシュできます。

以下の点でデータ収集時のサーバーサイド転送が改善されました。

* ページからの呼び出し回数が減ります。サーバーサイド転送では、データが Analytics から転送されるので、[!DNL Audience Manager] のお客様がデータ収集に DIL を使用する必要がなくなりました。DIL の削除とは、`"/event"` 呼び出しを削除することです。呼び出し回数が減ることはページの読み込み時間の改善につながり、サイトのカスタマーエクスペリエンスが向上します。
* Experience Cloud ソリューション間でデータ共有を利用できます。
* Audience Manager コードの実装と導入に関するアドビのベストプラクティスに準拠します。

>[!TIP]
>
>Analytics を使用している現在の Audience Manager のお客様は、サーバーサイド転送に移行する必要があります。Adobe Analytics と Audience Manager の新しいお客様は、デフォルトのデータ収集および転送方法として（DIL ではなく）サーバーサイド転送を実装する必要があります。

>[!IMPORTANT]
>EU Cookie コンプライアンス規則により、データ管理者（Analytics のお客様）には、同意前のデータをAdobe Analyticsに制限し、Adobe Audience Managerにサーバー側転送しないようにするオプションが追加されました。 新しい実装コンテキスト変数を使用すると、同意を受けていないヒットにフラグを設定できます。変数は、設定されている場合、同意を受け取るまで、これらのヒットがAdobe Audience Managerに送信されないようにします。 詳しくは、[GDPR_ePrivacy コンプライアンスおよびサーバーサイド転送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)を参照してください。

サーバーサイド転送の実装状況を確認するには、以下の検証ステップを実行してください。

## ![step1_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) ECID サービス実装の確認

[Analytics トラッキングリクエスト](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=ja)を調べて、Experience Cloud ID（ECID）サービスが実装されているかどうかを確認します。

「リクエスト」タブで、ECID 値が設定されていることを確認します。これで、サーバーサイド転送の前提条件である ID サービスが適切に実装されていることがわかります。

* ECID 値が表示されている場合は、手順 2 に進みます。
* ECID 値が表示されていない場合は、手順 2 に進む前に [ID サービスを実装](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=ja)します。

## ![step2_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) サーバーサイド転送の実装バージョンの確認

[Analytics トラッキングリクエスト](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)を調べて、サーバーサイド転送のバージョンが既に実装されているかどうかを確認します。

「応答」タブで、応答に Audience Manager データが含まれているかどうかを確認します。応答に従って手順を進めます。

* **Audience Manager からの JSON 応答に「postbacks」や「dcs_region」などの項目が含まれている場合**：何らかの形のサーバーサイド転送が既に有効になっています。手順 3 に進みます。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：Audience Management モジュールが実装されていますが、サーバー側転送が適切に設定されていません。手順 3 に進みます。
* **2 x 2 の画像**：サーバーサイド転送および Audience Management モジュールは実装されていません。修正手順を以下に示します。

   * **Adobe Audience ManagerDILのお客様**:以下の 2 つの項目を密接に連携させます。

      1. DIL コードを削除し、[Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja)ページのコードをインストールします。
      1. 手順 3 の説明に従って、Analytics 管理 UI でサーバーサイド転送を有効にします。DIL コードを削除する前にこの設定を有効にすると、データが複製され、Audience Manager に対する追加の請求対象サーバーコールが作成されます。

   * **新しいAdobe Audience Managerのお客様**  — インストール [Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja) ページコードを参照して、手順 3 に進みます。 手順 3 でサーバーサイド転送を有効にするまでは、データは Audience Manager に送信されません。

## ![step3_icon.png image](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) レポートスイートのサーバーサイド転送の実装の確認

従来のトラッキングサーバーアプローチではなく、サーバーサイド転送がレポートスイートレベルで実装されているかどうかを確認します。

レポートスイートレベルでのサーバーサイド転送は、Analytics から共有するデータをより細かく制御できるので、従来のトラッキングサーバーアプローチよりも推奨されます。これは Audience Analytics 統合の前提条件でもあります。

**Analytics**／**管理者**／**レポートスイート**／（**レポートスイート**&#x200B;を選択）／**設定を編集**／**一般**／**サーバー側転送**&#x200B;に移動します。このチェックボックスが

* **非アクティブ**（選択できないか、メニューが存在しない）：組織 ID にマッピングされたレポートスイートが選択されていません。レポートスイートが正しくマッピングされていることを確認するには、カスタマーケアにお問い合わせください。
* **無効**：新しいサーバーサイド転送を有効にしていません。ページのコンテンツを読んで、機能を有効にしてください。
* **有効**：新しいサーバーサイド転送がプロビジョニングされています。この Audience Analytics 統合をセットアップすることもできます。

>[!NOTE]
>
>3 つの手順をすべて実行するまでは、データは他の Experience Cloud ソリューション（[Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=ja) や [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja) など）に表示されません。有効にした後、これらの設定が反映されるまでに数時間かかります。
