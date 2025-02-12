---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: ht
source-wordcount: '882'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2025年1月リリース）

**最終更新日**：2024年1月22日（PT）

このリリースノートは、2024年1月15日（PT）～2024年2月中旬のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **新しい Report Builder でのスケジュール** | スケジュールすると、新しい Report Builder ワークブックをスケジュールできるだけではありません。さらに、従来のワークブックを変換する際に、古いスケジュールされたタスクのメタデータを取得することもできます。この方法では、従来のワークブックを新しいワークブックに変換してスケジュールする際、従来のワークブックと同じメールに、同じ頻度でワークブックを送信することになります。[詳細情報](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 2025年1月22日（PT） |
| **Analysis Workspace でのレポート（テンプレートとも呼ばれる）の改善** | レポート（テンプレートとも呼ばれる）で様々な改善が行われました。<ul><li>現在は、（[!UICONTROL レポート]ではなく）[!UICONTROL テンプレート]と呼ばれるようになりました。</li><li>列表示またはカードビューでテンプレートを表示するオプションなど、テンプレートの表示と検索に関するユーザーエクスペリエンスが向上しました。</li><li>会社テンプレートの場所が新しく、より直感的になりました（**[!UICONTROL ワークスペース]**／**[!UICONTROL テンプレート]**&#x200B;の下にあります）。</li><li>以前は、プロジェクトを作成する際にダイアログボックスから会社テンプレートにアクセスしていました。</li><li>追加の事前定義済みテンプレートを使用できます。</li></ul>[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/templates/use-templates)。<p>管理者はテンプレートを作成し、ログイン会社内の他のユーザーが使用できるように保存できます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 2025年1月15日（PT） | 2025年1月30日（PT） |
| **トランザクション ID の保持期間** | トランザクション ID の保持期間である 90 日は、2025年2月に 25 か月に延長されます。`transactionID` 変数はトランザクションを一意に識別し、ヒットがデータソースを介してアップロードされたデータに結び付けられるようにします。（ドキュメントへのリンクを添付） |  | 2025年2月11日（PT） |

## Adobe Analytics の修正点

**A4T**：AN-355602、AN-365988
**Activity Map**：AN-365320
**Admin Console**：AN-363884
**管理ツール**：AN-356747、AN-358776
**Advertising Analytics**：AN-355488
**Analysis Workspace**：AN-345318、AN-354801、AN-357052、AN-358975、AN-362886、AN-363831、AN-364124、AN-365257、AN-365319、AN-365462、AN-366194
**Analytics 1.4 API**：AN-358059
**分類**：AN-360049、AN-360424、AN-360745、AN-362208、AN-362345、AN-362560、AN-362576、AN-362633、AN-362653、AN-362762、AN-362815、AN-362881; AN-362885、AN-362973、AN-363343、AN-363558、AN-363860、AN-364239、AN-364480、AN-364451、AN-364528、AN-364548、AN-364552、AN-364585、AN-364598、AN-364643、AN-364715、AN-364912、AN-364997、AN-365081、AN-365189、AN-365197、AN-365203、AN-365431、AN-365647、AN-365794、AN-366546
**コンポーネントの移行**：AN-362236、AN-365429
**貢献度分析**：AN-360146
**データフィード**：AN-356997、AN-362470、AN-362498、AN-362775、AN-363323、AN-363413、AN-363569、AN-364063、AN-364142、AN-364294、AN-364298、AN-364325、AN-364367、AN-364594、AN-364995、AN-365127、AN-365272、AN-365519、AN-365760、AN-366152;
**Data Repair API**：AN-362773、AN-362874
**データソース**：AN-360745、AN-362202、AN-364566
**Data Warehouse**：AN-361447、AN-362616、AN-364524、AN-365108
**モバイルアプリ**：AN-362856、AN-365270
**超過アラート**：AN-355594、AN-364547
**Platform**：AN-358914、AN-360205、AN-362990、AN-364550、AN-365454、AN-365485
**Report Builder**：AN-363478、AN-364433、AN-365610
**レポートアクティビティマネージャー**：AN-362440
**セグメント化**：AN-359921
**VISTA ルール**：AN-362927

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Campaign 以外のお客様は、トリガーにアクセスできなくなる** | 2023年10月16日（PT） | 2025年1月30日（PT）に、Adobe Campaign ライセンスを持たない Adobe Analytics のお客様は、[トリガー](https://experienceleague.adobe.com/ja/docs/core-services/interface/services/triggers)を設定および使用できなくなります。お客様は、Campaign を購入、またはトリガーの使用を中止するか、トリガー機能を提供する他の Adobe ツールを検討する必要があります。 |

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
