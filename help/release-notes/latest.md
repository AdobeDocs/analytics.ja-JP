---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 835b7b07e46de4aa5dc0ae27bc9dee9c083660ad
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 96%

---

# 最新の Adobe Analytics リリースノート（2023年10月／11月）

**最終更新日**：2024年1月8日

これらのリリースノートでは、2023 年 10 月 23 日のリリース期間を 2024 年 1 月中旬にカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **レポートアクティビティマネージャーの機能強化** | レポートアクティビティマネージャーでは、組織内の各レポートスイートのレポート処理能力を確認できます。レポートの使用状況を詳細に把握し、ピーク時のレポート作成時の処理能力に関する問題を簡単に診断および修正できます。レポートアクティビティマネージャーで現在使用できる機能強化の一部を以下に示します。 <ul><li>後続のリクエストを制限：管理者は、現在のリクエストのキャンセルに加えて、定義した期間だけリクエストを制限できるようになりました。管理者は、リクエスト、プロジェクトおよびユーザーごとにリクエストを制限できます。</li><li>稼働率と処理能力の指標に加えて、レポートアクティビティマネージャーには、レポートアクティビティに関するより多くのデータ（複雑度列、ユーザー列、接続列）が含まれるようになりました。</li><li>レポートアクティビティマネージャーで行われたすべてのキャンセルと制限が監査ログに表示されるようになりました。管理者は、監査ログを使用して、現在キャンセルされている内容を表示できます。レポートアクティビティマネージャーまたは監査ログでキャンセルを元に戻すことはできません。</li></ul><p>詳しくは、[レポートアクティビティマネージャーの概要](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)を参照してください</p> | 2023年10月17日（PT） | 2023年10月24日（PT） |
| **Data Warehouse の機能強化** | Data Warehouse リクエストを作成する際に、レポートの宛先として使用するクラウドアカウントを設定できるようになりました。データの送信には、次のクラウドアカウントタイプを使用できます。<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>メール（このオプションは、以前は利用できました）</li></ul>FTP、SFTP、Azure BLOB および S3 は引き続きレポートの宛先として使用できますが、非推奨になりました。<p>また、Data Warehouse リクエストを作成および管理する際のユーザーエクスペリエンスも向上しました。詳しくは、[Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)および [Data Warehouse リクエストの管理](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=ja)を参照してください。 | 2023年9月12日（PT） | 2023年12月15日 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* これらの Analytics の処理およびレポートエンジンの変更は 10月の最終週にデプロイされます。ページまたはリンクのディメンションのラベルが誤って `Unknown` として表示されていた問題が修正されます。修正前は、ヒット時にページ名またはリンク名が渡されなかった場合、`Unknown` ラベルが誤って表示され、デフォルトでそれぞれ[!UICONTROL ページ URL] と[!UICONTROL リンク URL] が表示されることがありました。これらのディメンションは、大文字と小文字を区別しないように設定されています。この修正により、今後のレポートは正しくなります。ただし、履歴データに関するレポートの場合、一部のレポート結果が誤って `Unknown` としてラベル付けされる場合があります。（AN-328030）

### その他の修正点

-315676、AN-、AN-323398、AN-326209、AN-328178、AN-328261、AN-328395、AN-328671、AN-329282、AN-329330、AN-329355、AN-329506、AN-329516、AN-329738、AN-329769、AN-329771、AN-329816、AN-329877、AN-329928、AN-329957、AN-329962、AN-329966、AN-330023、AN-330081、AN-330083、AN-330105、AN-330138、AN-330140、AN-330165、AN-330241、AN-330359、AN-330366、AN-330427、AN-330438、AN-330442、AN-330534、AN-330616、AN-330654、AN-330783、AN-330879、AN-330881、AN-330883、AN-330887、AN-330888、AN-330955、AN-330979、AN-331031、AN-331053、AN-331068、AN-331071、AN-331074、AN-331075、AN-331076、AN-331078、AN-331085、AN-331093、AN-331167、AN-331171、AN-331181、AN-331196、AN-331226、AN-331258、AN-331260、AN-331279、AN-331286、AN-331290、AN-331365、AN-331375、AN-331376、AN-331454、AN-331519、AN-331570、AN-331590、AN-331593、AN-331603、AN-331751、AN-331816、AN-331897、AN-331900、AN-331906、AN-331926、AN-331929、AN-332031、AN-332067、AN-332101、AN-332114、AN-332156、AN-332201、 AN-332225、AN-332253、AN-332277、AN-332361、AN-332370、AN-332386

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Adobe Experience Edge ヒットの完全な IP 不明化** | 2023年9月27日（PT） | Experience Edge からのヒットの IP 不明化は、2023年10月後半に更新する予定です。2023年4月に、Experience Edge に IP アドレスを不明化する機能を追加しました。その時点で、Adobe Analytics は、Analytics が Experience Edge からのヒットを処理する方法により、IP の部分的な不明化のみをサポートしていました。お客様が Experience Edge の完全な不明化を選択した場合、Analytics は部分的に不明化された IP のみを受信しました。この変更を実装すると、Analytics は完全に不明化された IP を受信します。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023年9月27日（PT） | お客様は、以前の場所の 1.4 API ではなく、Adobe Analytics 2.0 API で [Adobe Analytics Livestream のエンドポイントガイド](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)にアクセスできるようになりました。Adobe I/O JWT 資格情報を使用しているお客様は、2025年1月1日（PT）までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。（詳しくは、以下の EOL に関する注意事項を参照してください）。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年12月13日 | **2024年1月17日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に期限切れとなるように戻されます。また、2023年12月31日（PT）以降のレポートをスケジュールできなくなりました。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2023年12月13日 | Reports &amp; Analytics のサポート終了の一環として、 [!UICONTROL 発行リスト] は、の提供終了に達する予定です **2024 年 1 月 18 日**. 新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Data Workbench のサポート終了** | 2024年1月2日（PT） | Adobeの提供終了Data Workbench効果 **2023 年 12 月 31 日**. 詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.25.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
