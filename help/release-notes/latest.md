---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 53175bbf54dd452502e1502b272ebb86c8b133ef
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 64%

---

# 現在の Adobe Analytics リリースノート（2025年3月リリース）

**最終更新日**：2025年3月31日（PT）

このリリースノートは、2025年3月5日（PT）～2025年5月のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics コンテキストデータフィールドの更新`a.locale`** | この更新により、Experience Edge 経由でデータを収集する際の Analytics コンテキストデータフィールド `a.locale` の設定方法が変更されます。Experience Edge を使用してデータを Adobe Analytics に送信すると、XDM フィールドのマッピングに基づいて Analytics フィールドが入力されます。`c.a.locale` のマッピングは、非標準の XDM フィールド `xdm.environment.language` を参照します。このフィールドは、正しいフィールド `xdm.environment._dc.language` を参照するように更新されます。<p>後方互換性のために、マッピングは引き続き `xdm.environment.language` を参照します。継続性のために、両方のフィールドが設定されている場合は、`xdm.environment.language` が優先されます。XDM から標準の Analytics フィールドへのマッピングの完全なリストについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/analytics/implementation/aep-edge/xdm-var-mapping)を参照してください。 | | 2025年3月5日（PT） |
| **Customer Journey Analytics アップグレードガイド** | Adobe Analytics から Customer Journey Analytics にアップグレードするためのステップバイステップガイドを生成できます。このガイドは、組織に合わせて調整されており、現在の Adobe Analytics 環境、Customer Journey Analytics の使用目的、組織が希望する時間節約のトレードオフを考慮しています。<p>カスタムガイドの生成を開始するには、[!DNL Customer Journey Analytics] にログインし、「**[!UICONTROL ワークスペース]**」タブで「**[!UICONTROL Customer Journey Analytics にアップグレード]**」を選択します。<p>[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 2025年3月11日（PT） |
| **Data Warehouse 専用ディメンション** | 2025 年 5 月以降、Adobeは、特定のディメンション（eVar や prop などのカスタム変数）を「Data Warehouseのみ」として設定し始めます。 これは、次の特性を示すディメンションに適用されます。<ul><li> 複数の月の期間にわたって、変数は月の最初の数日以内に低トラフィック制限に達します。</li><li>渡された値の 90% 超は、その月に 1 回だけ表示されます。</li></ul>例えば、タイムスタンプ、UUID、またはその他の非常にカーディナリティの高いデータを含み、月を通じほとんどすべてのヒット（または訪問または訪問者）に対して一意の新しい値が渡されるディメンションがあります。これらのディメンションは、通常、低トラフィックの制限を非常に迅速に超え、Analysis Workspaceでは値のごく一部しかレポートできません。 これにより、これらのディメンションを利用したレポートは、有用で正確な情報を表示しないため、混乱を招きます。 これらのディメンションは、低トラフィック機能の目的に従っていない、またはその利点はありません。これは、ディメンションが月に低トラフィックの制限を超えた後に「人気」になった値に関するレポートを提供する方法を提供することを目的としています。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic.)<p>「Data Warehouseのみ」とマークされたディメンションは、Analysis Workspaceでのレポートには使用できません。 ただし、低トラフィックの制限はここでは適用されないので、Data Warehouseを通じたレポートには引き続き使用できます。<p>これは、低トラフィックの制限に達したすべてのディメンションが「Data Warehouseのみ」とマークされる候補であることを意味するものではありません。 低トラフィックの制限に達するほとんどのディメンションは、実際には低トラフィック機能の意図を満たしています。<ul><li>渡される値のほとんどは一意ではありません。</li><li>1 か月間で低トラフィックの制限に達した後も、共通の値が引き続き入力されます。</li><li>新しい「人気」値は引き続き発生します。</li></ul>渡される値のほとんどが新しく一意のディメンションのみが、「Data Warehouseのみ」とマークされます。 このような状況で収集されるデータの一意性を考慮すると、低トラフィックの制限を増やすことは解決策ではありません。 | | 2025年5月 |


## Adobe Analytics の修正点

**Activity Map**：AN-361038
**管理ツール**：AN-362178、AN-369483
**Analytics API 1.4**：AN-369615
**Analysis Workspace**：AN-353491、AN-363403、AN-367230、AN-367313、AN-368582、AN-369821、AN-370227、
**分類**：AN-369848、AN-370196、AN-370226、AN-370437
**データフィード**：AN-366162、AN-368906、AN-369066、AN-369087、AN-369225、AN-369798
**データガバナンス**：AN-365157
**データソース**：AN-367550
**プラットフォーム**：AN-363931
**Report Builder**：AN-367460、AN-368975

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| 該当なし |  |  |

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新の更新については、[AppMeasurement リリースノート ](https://github.com/adobe/appmeasurement/releases) を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
