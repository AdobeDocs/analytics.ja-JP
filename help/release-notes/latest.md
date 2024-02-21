---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bb2b0f715941135d119d862b64c02f05800b3fdd
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 40%

---

# 現在の Adobe Analytics リリースノート（2024年2月）

**最終更新日**：2024年2月21日（PT）

これらのリリースノートでは、2024 年 2 月 14 日のリリース期間を 2024 年 3 月 11 日まで対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data WarehouseAPI ドキュメント** | 詳しくは、 [Adobe AnalyticsData WarehouseAPI 2.0](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Warehouse%20APIs#/Data%20Warehouse%20Scheduled%20Requests%20API) を参照してください。 に移動します。 [!UICONTROL 定義を選択] を選択し、 [!UICONTROL Data WarehouseAPI]. | | 2024年2月19日（PT） |
| **追加費用なしの Web SDK のActivity Map** | 現在、Activity Mapリンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。 この機能強化では、AppMeasurementでのイベントの処理と同様に、一部のリンクイベントを取得し、それらを次のヒットにパッケージ化します。 |  | 2024年3月6日（PT） |
| **デフォルトの低トラフィックしきい値の増加** | In **2024 年 4 月中旬**&#x200B;に設定すると、Adobeは、次のように、デフォルトのレポートスイートの低トラフィックしきい値を増やし始めます。 ![低トラフィックしきい値](assets/thresholds.png) これは、現在新しいしきい値を下回って設定されている変数にのみ影響します。 これらの変更は段階的におこなわれ、作業は **5 月末**. これらの増加がロールアウトされると、大基数変数の変更に気付く場合があります。<ul><li>レポートには、より多くのディメンション値を使用できる場合があります。</li><li>セグメントと計算指標に含まれるデータの量が多くなる場合があります。</li><li>セグメントに基づく仮想レポートスイートには、より多くのデータが含まれる場合があります。</li><li>分類の書き出しには、より多くのデータが含まれる場合があります。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月末 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 次の分類の問題を修正しました。AN-319515、AN-337559、AN-338149、AN-338702、AN-338891、AN-339327、AN-339649、AN-339776339669、AN-339822、AN-340017、AN-; AN-、AN-340476;
* 分類ルールビルダーでの問題を修正しました。AN-338385、AN-338399、AN-338592、AN-338810、AN-338893、AN-339431、AN-339894、AN-339933、AN-340201、AN-340309、
* 次の A4T の問題を修正しました。AN-334830、AN-336194、AN-338309、AN-338650;
* 次のデータ収集の問題を修正しました。AN-339323
* 次のData Warehouseの問題を修正しました。AN-335542、AN-331425、AN-337215、AN-338445、AN-338643、AN-338651、AN-339461、AN-340066、AN-340207、AN-340460
* 次のデータフィードの問題を修正しました。AN-335952、AN-338653、AN-339508、AN-339681、AN-340418
* 次のデータソースの問題を修正しました。AN-338648
* Analysis Workspaceの次の問題を修正しました。AN-326509、AN-336186、AN-336190、AN-336309、AN-337922、AN-338094、AN-338323、AN-338556、AN-339600、AN-340445

### Analytics のその他の修正

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336128; AN-338088; AN-338270; AN-338494 338393; AN-339326; AN-339742; AN-339883; AN-; 340419; AN-;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| Adobe API オブジェクトメンバーの追加 | 2024年1月17日（PT） | Adobeは、オプションの要求および応答メンバー（名前と値のペア）を既存の API オブジェクトにいつでも、通知やバージョン管理の変更なしに追加できます。 Adobeでは、わからない場合に処理時に追加内容を無視するよう、API と統合するサードパーティツールの API ドキュメントを参照することをお勧めします。 適切に実装されている場合、そのような追加は実装に対する重大でない変更です。 アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |
| `getPageLoadTime` プラグインの廃止 | 2024年1月10日（PT） | このプラグインはサポートされなくなりました。そのコードは、（MDN に従って）[廃止](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)となった Performance.timing メソッドを利用しています。更新されたプラグインの動作が開始しました。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.25.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2023年の以前のリリースノート](/help/release-notes/2023.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
