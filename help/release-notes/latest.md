---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 73%

---

# 現在の Adobe Analytics リリースノート (2023年7月)

**最終更新日**：2023年7月10日

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **分類データを取り込むためのクラウドアカウントのストレージの場所の設定** | 分類セットの自動化に使用するクラウドアカウントのストレージの場所を管理できるようになりました。 [詳細情報](/help/components/locations/configure-import-accounts.md)<p> | 該当なし | 2023年7月10日（PT） |
| **データ修復フィルターの強化** | データ修復に 3 つのフィルター機能が追加されました。<ul><li>1 つの変数でフィルターし、2 つ目の変数を変更します。 例えば、 `eVar2` 「@」を含み、次に「削除」を含む `eVar3`.</li><li>数値または数値以外の値のフィルター</li><li>AND を使用して複数のフィルターを適用できます。 例： `eVar2="a"` および `eVar3="b"`</li></ul>[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 2023年6月21日（PT） | 2023年7月12日（PT） |
| **データフィード書き出しの安全な宛先** | データフィードを次のクラウドストレージの宛先に送信できるようになりました。<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>以前に使用可能だった宛先（FTP、SFTP、S3、Azure Blob）は、推奨されなくなりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=ja) | 2023年6月12日（PT） | 2023年7月13日（PT） |
| **新しい AppMeasurement 変数** | 変数 `decodeLinkParameters` は、実装がリンクトラッキング変数でマルチバイト文字をエンコードするというエッジケースに対応しています。ほとんどの実装では、この変数を定義する必要はありません。[詳細情報](../implement/vars/config-vars/decodelinkparameters.md) |  | 2023年7月17日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

AN-307816;AN-318111;AN-318584;AN-318828;AN-320440;AN-320568;AN-320616;AN-321013;AN-321513;AN-321520;AN-321757;AN-321820;AN-321917;AN-322034;AN-322135;AN-322140;AN-322142;AN-322251;AN-322353;AN-322378;AN-322383;AN-322427;AN-322458;AN-322543;AN-322630;AN-322637;AN-322638;AN-322647;AN-322728;AN-322732;AN-322777;AN-322817;AN-322957;AN-322958;AN-323035;AN-323074;AN-323150;AN-323196;AN-323197;AN-323205;AN-323206;AN-323217;AN-323224;AN-323225;AN-323244;AN-323257;AN-323277;AN-323280;AN-323293;AN-323309;AN-323318;AN-323468;AN-323476;AN-323514;AN-323572;AN-323592;AN-323782;AN-323835

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **購入 ID とイベント ID の 37 か月の有効期限（イベントのシリアル化）** | 10,2023年7月 | のリリースをターゲットとした、Analytics のヒット処理エンジンの今後のリリース **2023 年 7 月 14 日**&#x200B;は、購入 ID とイベント ID（イベントのシリアル化）の 37 ヶ月間の有効期限の適用を開始します。 現在、Adobe Analytics では購入 ID とイベント ID に有効期限がありません。購入 ID またはイベント ID が確認／使用されると、その後のヒットは、いつであっても、その購入またはイベントが重複としてマークされます。新しい処理エンジンのリリースでは、次のようになります。<ul><li>購入 ID とイベント ID は常に 37 か月後に有効期限が切れます。</li><li>購入 ID またはイベント ID が確認されてから 37 か月が経過している場合、重複した購入またはイベントとは見なされなくなります。</li><li> 37 か月以上前の購入 ID またはイベント ID を「再利用」している場合、重複と見なされなくなります。</li></ul> |
| **Adobe I/OOAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/OJWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順でAdobe I/OOAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. 詳細とタイムラインについては、以下の表に記載されている提供終了の通知を参照してください。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/OOAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/OJWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順でAdobe I/OOAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. Adobe I/Oでは、2024 年 5 月 1 日以降、新しい JWT 資格情報の作成は許可されません。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に有効期限が切れるように戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、[!UICONTROL パブリッシュリスト]は **2023年12月** に提供終了になる予定です。新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
