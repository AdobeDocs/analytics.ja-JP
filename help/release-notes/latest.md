---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00fd63b7486382da5506d16540bb949c52541c6d
workflow-type: ht
source-wordcount: '895'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2023年8月）

**最終更新日**：2023年8月9日（PT）

このリリースノートは、2023年8月9日～9月13日（PT）のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0 の分類セット** | 分類セットデータの保存、削除、取得、読み込み、書き出しを行うための Adobe Analytics API 2.0 メソッドが用意されています。 | 該当なし | 2023年8月31日（PT） |
| **レポートアクティビティマネージャー** | レポートアクティビティマネージャーでは、管理者は各レポートスイートのレポートの使用状況を詳細に把握できるので、ピーク時のレポート作成時の処理能力に関する問題を簡単に診断および修正できます。[詳細情報](/help/admin/admin/reporting-activity.md) | 該当なし | 2023年9月6日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* カスタムイベントが読み込まれない問題を修正しました。（AN-324163）
* ビジュアライゼーションの凡例のラベルを編集できない問題を修正しました。（AN-323246）

AN-315605、AN-316306、AN-317494、AN-317844、AN-320424、AN-320597、AN-320680、AN-320869、AN-321624、AN-321693、AN-322009、AN-322244、AN-322380、AN-322432、AN-322466、AN-322556、AN-322669、AN-322735、AN-323151、AN-323220、AN-323380、AN-323492、AN-323595、AN-323755、AN-323854、AN-323916、AN-324044、AN-324200、AN-324213、AN-324238、AN-324347、AN-323598、AN-323625、AN-323631、AN-323638、AN-323641、AN-323755、AN-323767、AN-323777、AN-323825、AN-323846、AN-323972、AN-324113、AN-324170、AN-324197、AN-324273、AN-324275、AN-324345、AN-324384、AN-324433、AN-324511、AN-324513、AN-324521、AN-324524、AN-324531、AN-324532、AN-324534、AN-324537、AN-324569、AN-324618、AN-324635、AN-324688、AN-324704、AN-324712、AN-324721、AN-324745、AN-324792、AN-324793、AN-324794、AN-324795、AN-324824、AN-324905、AN-324918、AN-324932、AN-324934、AN-324947、AN-325003、AN-325073、AN-325143、AN-325148、AN-325153、AN-325177、AN-325187、AN-325252、AN-325305、AN-325363、AN-325401、AN-325439、AN-325431、AN-325491、AN-325495、AN-325508、AN-325594、AN-325601、AN-325660、AN-325779、AN-325857、AN-325883、AN-325885、AN-325886


## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **購入 ID とイベント ID の 37 か月の有効期限（イベントのシリアル化）** | 2023年7月10日（PT） | Analytics のヒット処理エンジンの今後のリリースは、**2023年7月13日（PT）**&#x200B;のリリースを予定しており、購入 ID とイベント ID の 37 か月の有効期限（イベントのシリアル化）の適用が開始されます。現在、Adobe Analytics では購入 ID とイベント ID に有効期限がありません。購入 ID またはイベント ID が確認／使用されると、その後のヒットは、いつであっても、その購入またはイベントが重複としてマークされます。新しい処理エンジンのリリースでは、次のようになります。<ul><li>購入 ID とイベント ID は常に 37 か月後に有効期限が切れます。</li><li>購入 ID またはイベント ID が確認されてから 37 か月が経過している場合、重複した購入またはイベントとは見なされなくなります。</li><li> 37 か月以上前の購入 ID またはイベント ID を「再利用」している場合、重複と見なされなくなります。</li></ul> |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。詳細とタイムラインについては、以下の表に記載されている提供終了の通知を参照してください。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に有効期限が切れるように戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
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
