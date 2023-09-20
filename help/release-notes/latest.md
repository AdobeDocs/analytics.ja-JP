---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2998ab3ecb83e14be38333a2836f863667babfee
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 88%

---

# 現在の Adobe Analytics リリースノート（2023年9月）

**最終更新日**：2023年9月13日（PT）

9月のリリースノートは、2023年9月13日（PT）から 2023年10月3日（PT）までのリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0 での分類** | 分類セットデータの保存、削除、取得、読み込み、書き出しを行うための Adobe Analytics API 2.0 メソッドが用意されています。[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | 該当なし | 2023年9月13日（PT） |
| **A4T 分類に対する新しい `correlationID` フィールドのサポート** | `_experience.decisioning.propositions.scopeDetails.correlationID` フィールドが Adobe Analytics ソースコネクタスキーマで使用できるようになりました。Adobe Target のアクティビティとエクスペリエンスイベントの分類データを簡単に結合できるように、この ID を追加しています。 | 該当なし | 2023年9月13日（PT） |
| **Data Warehouse の機能強化** | Data Warehouse リクエストを作成する際に、レポートの宛先として使用するクラウドアカウントを設定できるようになりました。データの送信には、次のクラウドアカウントタイプを使用できます。<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>メール（このオプションは、以前は利用できました）</li></ul>FTP、SFTP、Azure BLOB および S3 は引き続きレポートの宛先として使用できますが、非推奨になりました。<p>また、Data Warehouse リクエストを作成および管理する際のユーザーエクスペリエンスも向上しました。詳しくは、[Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)および [Data Warehouse リクエストの管理](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=ja)を参照してください。 | 2023年9月13日（PT） | 2023年10月4日（PT） |
| **コンポーネントを管理する際に使用できる新しい列** | コンポーネントを管理する際に、次の新しい列を使用できるようになりました。<ul><li>使用場所<p>この列は、 [計算指標マネージャー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) そして [セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>前回の使用<p>この列は、 [計算指標マネージャー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)、 [セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md)、および [アラートマネージャー](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、および削除または変更する必要があるかどうかを判断するのに役立ちます。 この情報と共にデータディクショナリを使用すると、組織でのコンポーネントの使用方法を追跡し、より深く理解することができます。</p> | 2023年9月20日（PT） | 2023年10月4日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 分類データが Workspace に表示されない問題を修正しました。（AN-326827）

## その他の修正点

AN-314882、AN-315591、AN-318165、AN-318559、AN-319031、AN-319244、AN-321657、AN-321759、AN-323099、AN-323596、AN-323640、AN-324442、AN-324921、AN-324953、AN-324977、AN-324979、AN-325124、AN-325395、AN-325433、AN-325535、AN-325693、AN-325720、AN-325835、AN-325880、AN-325957、AN-325984、AN-326054、AN-326065、AN-326136、AN-326155、AN-326162、AN-326235、AN-326317、AN-326344、AN-326357、AN-326359、AN-326433、AN-326438、AN-326440、AN-326461、AN-326464、AN-326523、AN-326553、AN-326606、AN-326635、AN-326642、AN-326652、AN-326678、AN-326769、AN-326777、AN-326830、AN-326938、AN-326949、AN-327081、AN-327082、AN-327085、AN-327103、AN-327198、AN-327225、AN-327275、AN-327358、AN-327423、AN-327561、AN-327755、AN-327896、AN-327922、AN-328128、AN-328300、AN-328428、AN-328518、AN-328554

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| 該当なし | 該当なし | 該当なし |

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

AppMeasurement リリース（バージョン 2.24.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
