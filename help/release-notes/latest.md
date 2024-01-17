---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c3f59a07d51f5e6a73fa87aed573450c133d5bd6
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 39%

---

# 最新のAdobe Analyticsリリースノート（2024 年 1 月）

**最終更新日**：2024年1月10日

これらのリリースノートでは、2024 年 1 月のリリース期間を 2024 年 2 月 13 日にカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouseの更新** | 次のData Warehouseが強化されました。<ul><li>Data Warehouseリクエストを作成する際に、組織内のすべてのユーザーがリクエストを使用できるようにするために、新しい切り替え ( [!UICONTROL **組織内のユーザーが利用できるようにする**].<p>詳しくは、 [Data Warehouseリクエストの一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Data Warehouseレポートの宛先を作成または管理する際に、組織内のユーザーが作成したアカウントおよび場所をシステム管理者が表示できるようになりました。そのためには、 [!UICONTROL **すべての宛先を表示**].<p>詳しくは、 [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | 該当なし | 2024年1月10日（PT） |
| **主要指標の概要ビジュアライゼーションの更新** | 主要指標の概要ビジュアライゼーションを使用する場合、選択した比較日付範囲オプションが主日付範囲に対するものか固定のものかに応じて、比較日付範囲が自動的に更新されるようになりました。 [詳細情報](/help/analyze/analysis-workspace/visualizations/key-metric.md)。 | 該当なし | 2024年1月17日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 次の分類の問題を修正しました。AN-314821、AN-326839、AN-332079、AN-332704、AN-332902、AN-332975、AN-333300、AN-333174333033、AN-333910、AN-334097、AN-、AN-、AN-334373、AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN AN  AN AN AN AN AN AN AN AN AN    AN-AN-AN-GE;AN-GEE;AN-GEE;AN-GEE-GEE;AN-GEE-GEE-GEE-GE-GE-GE-GE-GE
* 分類ルールビルダーでの問題 AN-332390、AN-332573、AN-332718、AN-332927、AN-333248、AN-333953、AN-334647、AN-334910、AN-335642、AN-335683、AN-335811;AN-AN-;AN-AN-AN336852;; AN-GEN; AN-GEN-GEN; AN-GEN-GEN;
* 次の A4T の問題を修正しました。AN-334564、AN-336178、
* サーバーコールの使用に関する次の問題を修正しました。AN-332568、AN-333105、AN-333167、AN-333983、AN-334209、AN-334278
* 次のData Warehouseの問題を修正しました。AN-333010、AN-333076、AN-330227、AN-331580、AN-334291、AN-334283、AN-334287、AN-334453334301、AN-334385、AN-334977、AN-、AN-AN-335245;AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN
* 次のデータフィードの問題を修正しました。AN-332241、AN-332366、AN-332617、AN-332654、AN-332702、AN-332723、AN-333014、AN-334037、AN-334125、334211AN-334216;AN-334235;AN-; 335158;AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN;AN-AN-CHA;AN-CHA;AN-CHA-CHA;AN-CHA-CHA-CHA-CHA-CHA-CHA-CHA-CHA-CHA
* 次のReport Builderの問題を修正しました。AN-335246、AN-336311、
* Analysis Workspaceの次の問題を修正しました。AN-323760、AN-324191、AN-324913、AN-330126、AN-332808、AN-333168、AN-333382、AN-334839、AN-336040、AN-337043;

### その他の修正点

AN-323975、AN-325383、AN-325809、AN-326787、AN-331611、AN-332124、AN-332272、AN-332911、AN-333070、AN-333302、AN-333377、AN-AN-333968AN-AN-AN;AN-AN-;AN-AN-CHA;AN-CHA;AN-CHA;AN-CHA;AN-CHA;AN-CHA;AN-CHA;AN-CH;A

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| AdobeAPI オブジェクトメンバーの追加 | 2024年1月17日（PT） | Adobeは、オプションの要求および応答メンバー（名前と値のペア）を既存の API オブジェクトに追加できますが、バージョン管理に関する通知や変更はありません。 このような追加は、実装に対する重大でない変更である必要があります。 Adobeでは、わからない場合に処理時に追加内容が無視されるように、API と統合するサードパーティツールの API ドキュメントを参照することをお勧めします。 Adobeは、リリースノートから標準通知を受け取らない限り、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |
| `getPageLoadTime` プラグインが廃止されました | 2024年1月10日（PT） | このプラグインはサポートされなくなりました。 このコードでは、（MDN に従って）performance.timing メソッドを使用します。 [非推奨](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). 更新されたプラグインの動作が開始しました。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** のサポート終了 | 2024年1月10日（PT） | **2024年1月17日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に期限切れとなるように戻されます。また、2023年12月31日（PT）以降のレポートをスケジュールできなくなりました。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2024年1月10日（PT） | Reports &amp; Analytics のサポート終了の一環として、 [!UICONTROL 発行リスト] は、の提供終了に達する予定です **2024 年 1 月 18 日**. 新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2024年1月2日（PT） | Adobeの提供終了Data Workbench効果 **2023 年 12 月 31 日**. 詳しくは、[Data Workbench の提供終了のお知らせ](https://express.adobe.com/page/GSu6oKOD88GAj/)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.25.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2023年の以前のリリースノート](/help/release-notes/2023.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
