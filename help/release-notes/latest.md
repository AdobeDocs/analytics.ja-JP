---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 81f30a16fce33350aaf02fd8c6cf5011489c8250
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 69%

---

# 現在の Adobe Analytics リリースノート (2023年9月)

**最終更新日**：2023年9月13日（PT）

9 月のリリースノートは、2023 年 9 月 13 日のリリース期間を 2023 年 10 月 3 日にカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0 の分類セット** | 分類セットデータの保存、削除、取得、読み込み、書き出しを行うための Adobe Analytics API 2.0 メソッドが用意されています。[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | 該当なし | 2023年9月13日（PT） |
| **新規のサポート `correlationID` A4T 分類のフィールド** | The `_experience.decisioning.propositions.scopeDetails.correlationID` フィールドがAdobe Analyticsソースコネクタスキーマで使用できるようになりました。 この ID を追加して、Adobe Targetのアクティビティやエクスペリエンスイベントの分類データを簡単に結合できるようにします。 | 該当なし | 2023年9月13日（PT） |
| **Data Warehouse の機能強化** | Data Warehouseリクエストを作成する際に、をレポートの宛先として使用するようにクラウドアカウントを設定できるようになりました。 データを送信する際には、次のクラウドアカウントタイプを使用できます。<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>E メール（このオプションは以前から使用可能でした）</li></ul>FTP、SFTP、Azure Blob、S3 は、引き続きレポートの宛先として使用できますが、非推奨になりました。<p>また、ユーザーリクエストを作成および管理する際のData Warehouseエクスペリエンスも改善されました。 詳しくは、 [Data Warehouseリクエストの作成](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) および [Data Warehouseリクエストの管理](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=ja). | 2023年9月13日（PT） | 2023 年 10 月 5 日 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 分類データが Workspace に表示されない問題を修正しました。 （AN-326827）

## その他の修正点

AN-314882、AN-315591、AN-318165、AN-318559、AN-319031、AN-321657、AN-321759、AN-323099、AN-323596、AN-323640、AN-324442、AN-AN-324977AN-AN-ANAN 、AN 、AN 、AN 、AN 、AN 、AN 、AN AN 、AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN     AN AN AN AN AN      ANAN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN AN AN AN AN AN    AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN;AN-AN-CE; AN-CHE; AN-CHE-CHE; AN-CHE-CHE-CHE; AN-CHE-CHE-CHE-CHE

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| 該当なし | 該当なし | 該当なし |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 In **2023 年 4 月**&#x200B;に設定されている場合、2023 年 12 月 31 日以降に期限が切れる予定のレポートは自動的に更新され、2023 年 12 月 31 日に期限切れに戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、[!UICONTROL パブリッシュリスト]は **2023年12月** に提供終了になる予定です。新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.24.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
