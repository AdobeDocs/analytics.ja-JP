---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69cffe2bc97a81cb9e4b989f2193dc2deb6e8d22
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 65%

---

# 現在の Adobe Analytics リリースノート（2023年10月）

**最終更新日**：2023年10月19日（PT）

リリースノートの 10 月は、2023 年 10 月 4 日から 2023 年 10 月 25 日までのリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **コンポーネントを管理する際に使用できる新しい列** | コンポーネントを管理する際に、次の新しい列を使用できるようになりました。<ul><li>使用場所<p>この列は、 [計算指標マネージャー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) そして [セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>前回の使用<p>この列は、 [計算指標マネージャー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)、 [セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md)、および [アラートマネージャー](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。この情報と共にデータ辞書を使用すると、組織内でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> | 2023年9月20日（PT） | 2023年10月4日（PT） |
| **Activity Manager のレポート機能の強化** | レポートアクティビティマネージャーでは、組織内の各レポートスイートのレポート処理能力を確認できます。レポートの使用状況を詳細に把握し、ピーク時のレポート作成時の処理能力に関する問題を簡単に診断および修正できます。レポートアクティビティマネージャーで使用できる機能強化の一部を次に示します。 <ul><li>以降のリクエストを制限：管理者は、現在のリクエストのキャンセルに加えて、定義した期間だけリクエストを制限できるようになりました。 管理者は、リクエスト、プロジェクト、ユーザーによってリクエストを制限できます。</li><li>使用率および容量の指標に加えて、レポートアクティビティマネージャーには、レポートアクティビティに関するより多くのデータ（複雑度列、ユーザー列、接続列）が含まれるようになりました。</li><li>レポートアクティビティマネージャーで行われたすべてのキャンセルと制限が監査ログに表示されるようになりました。 管理者は、監査ログを使用して、現在キャンセルされている内容を表示できます。 レポートアクティビティマネージャーまたは監査ログでキャンセルを元に戻すことはできません。</li></ul><p>詳しくは、 [Activity Manager のレポートの概要](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 2023年10月17日（PT） | 2023年10月24日（PT） |
| **Data Warehouse の機能強化** | Data Warehouse リクエストを作成する際に、レポートの宛先として使用するクラウドアカウントを設定できるようになりました。データの送信には、次のクラウドアカウントタイプを使用できます。<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>メール（このオプションは、以前は利用できました）</li></ul>FTP、SFTP、Azure BLOB および S3 は引き続きレポートの宛先として使用できますが、非推奨になりました。<p>また、Data Warehouse リクエストを作成および管理する際のユーザーエクスペリエンスも向上しました。詳しくは、[Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)および [Data Warehouse リクエストの管理](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=ja)を参照してください。 | 2023年9月12日（PT） | 2023 年 11 月 8 日以前 |
| **Adobe Analytics プロジェクトと含まれるコンポーネントを Customer Journey Analytics に移行** | Adobe Analyticsプロジェクトを Customer Journey Analytics に移行できるようになりました。このプロセスにより、Adobe Analytics から Customer Journey Analytics への移行が簡単になります。 <p>プロジェクトを Customer Journey Analytics に移行すると、アセットは Adobe Analytics レポートスイートから Customer Journey Analytics データビューにマッピングされます。</p> <p>Adobe Analytics インターフェイスから Customer Journey Analytics にプロジェクトを移行します。[詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=ja)</p> | 該当なし | 2023年10月9日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* Target/Analytics UI に A4T レポートが表示されない問題を修正しました。 (AN-329375、AN-329745、AN-330026)

AN-313983、AN-324189、AN-325095、AN-325677、AN-325886、AN-326360、AN-326458、AN-327290、AN-327315、AN-327353、AN-327505、AN-AN-327922AN-AN-ANAN 、AN 、AN 、AN 、AN 、AN 、AN 、AN AN 、AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN     AN AN AN AN AN      ANAN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN AN AN AN AN AN    AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-ANAN 、AN 、AN 、AN 、AN 、AN 、AN 、AN AN 、AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN     AN AN AN AN AN      ANAN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **AdobeExperience Edge ヒットの完全な IP 難読化** | 2023年9月27日（PT） | Experience Edge からのヒットの IP 難読化は、2023 年 10 月後半に更新されます。 4 月に、Experience Edge は IP アドレスを難読化する機能を追加しました。 その時点で、Adobe Analyticsは、Experience Edge からのヒットを Analytics で処理する方法が原因で、IP の部分的な難読化のみをサポートしていました。 お客様が Experience Edge の完全な不明化を選択した場合、Analytics は部分的に不明化された IP のみを受け取りました。 この変更が実装されると、Analytics は、完全に不明化された IP を受け取ります。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023年9月27日（PT） | これで、 [Adobe Analytics Livestream のエンドポイントガイド](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) （1.4 API を使用）の代わりに、Adobe Analytics 2.0 API を以前の場所に追加しました。 Adobe I/Oの JWT 資格情報を使用するお客様は、2025 年 1 月 1 日までにAdobe I/Oの OAuth サーバー間資格情報に移行する必要があります。 （詳しくは、以下の EOL に関する注意事項を参照してください）。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に期限切れとなるように戻されます。また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、[!UICONTROL パブリッシュリスト]は **2023年12月** に提供終了になる予定です。新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.25.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
