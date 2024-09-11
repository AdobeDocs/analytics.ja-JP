---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 56%

---

# 現在の Adobe Analytics リリースノート（2024年9月）


**最終更新日**：2024年9月11日（PT）

これらのリリースノートは、2024 年 9 月 11 日（PT）から 10 月上旬のリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
|--- | --- | --- | --- |
| **計算指標マネージャーとセグメントマネージャーの「使用されている場所」列の追加情報** | 計算指標マネージャーとセグメントマネージャーの「使用されている場所」列には、次の新しいレポート領域が含まれています。<ul><li>**Report Builder**:Report Builderで使用されている計算指標または計算指標セグメントの数が表示されます。</li><li>**アドホックコンポーネント**：プロジェクトで使用されているアドホック計算指標またはアドホックセグメントの数を表示します。 これらのアドホック計算指標およびセグメント（別名「クイック計算指標」および「クイックセグメント」）は、作成されたプロジェクトでのみ使用できるので、「使用されている場所」列の「プロジェクト」レポート領域とは別にレポートされます。</li></ul>詳しくは、[ 計算指標マネージャー ](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager) および [ セグメントマネージャー ](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage) を参照してください。 |  | 2024 年 9 月 11 日（Pt） |
| **Activity Map v3 拡張機能** | Activity Map v3 拡張機能が利用できるようになりました。 v2 拡張機能がインストールされている場合は、v3 拡張機能をインストールする前にアンインストールします。 **[!UICONTROL ツール]** / **[!UICONTROL 拡張機能]** に移動して、Activity Mapの最新バージョンを取得します。 |  | 2024 年 9 月 3 日（Pt） |


## Adobe Analytics の修正点

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
Analytics モバイルアプリ：AN-352645
分類：AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
クロスデバイス分析：AN-355138
データフィード：AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
書き出し場所：AN-356912
プライバシー API:AN-352420
Report Builder: AN-352555; AN-354316
スケジュールされたプロジェクト：AN-355971
セグメント化：AN-352095;
Target レポート：AN-355748

その他の修正点：AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年8月20日（PT） | **2024年8月20日（PT）**&#x200B;の Analytics のヒット処理エンジンのリリースでは、保存された `cust_visids` に 13 か月の有効期限が適用されます。レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。以前は、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありませんでした。このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |
| **自動的にマッピングされる追加の実装詳細 XDM フィールド** | 2024年9月11日（PT） | Adobe Experience Platform Edge Networkを使用してAdobe Analyticsにデータを送信する際に、XDM フィールド `xdm.implementationdetails.name` および `xdm.implementationdetails.environment` が常にコンテキストデータ変数 `c.a.x.implementationdetails.name` および `c.a.x.implementationdetails.environment` にマッピングされるようになりました。 以前は、一部のシナリオでこれらの値が入力されませんでした。 これらの値を使用できるように、関連する処理ルールを調整してください。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションアドオンのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
