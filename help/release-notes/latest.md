---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 55%

---

# 現在の Adobe Analytics リリースノート（2024年6月）

**最終更新日**：2024年6月13日（PT）

これらのリリースノートは、2024 年 6 月 12 日（PT）から 7 月までのリリース期間に対応しています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ドロップダウンフィルターでの複数フィールドの選択** | ドロップダウンフィルターに複数のフィールドが追加された場合、ユーザーは一度に複数のフィールドを選択できるようになりました。 パネルがフィルタリングされ、選択したフィールドのいずれかが含まれます。 <p>以前は、ユーザーはドロップダウンフィルターで一度に 1 つのフィールドのみを選択できました。</p><p>詳しくは、を参照してください [静的ドロップダウンセグメント](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments) 。対象： [パネルの概要](/help/analyze/analysis-workspace/c-panels/panels.md).</p> |  | 2024年6月19日（PT） |
| **ワークスペースプロジェクトの目次** | プロジェクトで新しい目次が使用できるようになりました。 目次には、プロジェクト内のパネルやビジュアライゼーションにすばやくジャンプできるリンクがあります。 目次は、個々のプロジェクトに対して、または特定のユーザーのすべてのプロジェクトに対して有効にできます。<p>詳しくは、を参照してください [プロジェクトの目次](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p> |  | 2024年6月19日（PT） |
| **フリーフォームテーブルでのディメンション項目のハイパーリンクの作成** | 1 つ以上のディメンション項目にハイパーリンクを作成して、Analysis Workspaceのフリーフォームテーブル内でクリックできるようにします。 <p>URL 値を持つディメンション項目のハイパーリンクを作成したり、非 URL 値を持つディメンション項目のカスタム URL を作成したりできます。</p><p>変数を使用して、複数のディメンション項目の動的カスタム URL を作成できます。 変数は、ディメンション項目の値を参照することも、分類ディメンションを参照することもできます。</p><p>詳しくは、を参照してください [フリーフォームテーブルでのディメンションのハイパーリンクの作成](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p> |  | 2024年6月19日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所を制御するための管理者設定** | 新品 [ロケーションマネージャーの「管理者設定」タブ](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) ユーザーがアカウントと場所を作成および編集できるかどうかを管理者が制御できます。 これらの設定は、次の場合に適用されます [クラウドの読み込みアカウントと書き出しアカウントの設定](/help/components/locations/configure-import-accounts.md) および [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md). <p>また、管理者は、ユーザーが作成して使用できるアカウントのタイプ（Google Cloud Platform、Azure RBAC、Amazon S3 など）を制限することもできます。</p><p>以前は、すべてのユーザーが、あらゆるタイプのアカウントと場所を作成、編集、使用できました。</p> | 2024年6月12日（PT） | 2024年6月30日（PT） |
| **書き出しと読み込みに使用されるアカウントと場所の共有** | ユーザーは、作成したアカウントと場所を組織内のすべてのユーザーに対して使用できるようになりました。アカウントと場所の所有者およびシステム管理者のみが、アカウントと場所を編集および削除できます。<p>以前は、アカウントと場所は、作成したユーザーのみが使用できました。</p><p>これらの設定は、ユーザーが次の場合に使用できます [クラウドの読み込みアカウントと書き出しアカウントの設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts) および [クラウドの読み込み場所と書き出し場所の設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-locations). </p> | 2024年6月12日（PT） | 2024年6月30日（PT） |
| **Web SDK のサーバー呼び出しを減らすための Activity Map** | 現在、Activity Map リンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。この度の機能強化では、AppMeasurement でのイベントの処理と同様に、一部のリンクイベントを取り上げ、それらを次のヒットにパッケージ化します。 <p>（更新されたドキュメントへのリンクを添付）</p> | オープンベータ版は 2024年6月19日（PT）から開始 | 未定 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* An-347682、AN-348396、AN-348625、AN-348668、AN-348926、AN-348936、AN-349040、AN-349191、AN-349195 349443、AN-349697、AN-349758、AN-349862、AN-350051、AN-350054、AN-350208、AN-350497、AN-350525、AN-351067
* Data Warehouseに関する AN-346862、AN-349409、AN-349926、AN-350629、AN-350996 の問題を修正しました。
* データフィードの問題 AN-346727、AN-348282、AN-348334、AN-348725、AN-348726、AN-348823、AN-349081、AN-349207、AN-349307 349539、AN-349710、AN-349729、AN-349742、AN-349878、AN-349943、AN-350527 を修正しました。
* 次のデータソースの問題を修正しました。AN-350038
* Analysis Workspaceの次の問題を修正しました。AN-342953、AN-346346、AN-349590、AN-349717、AN-350057、AN-350697、AN-350904
* Report Builderに関する AN-348903; AN-350691 の問題を修正。
* 次の A4T の問題を修正しました。AN-347690、AN-350853

### Analytics のその他の修正

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年5月22日（PT） | Analytics のヒット処理エンジンの次回リリース（**2024年7月を予定**）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |
| **ISO 地域のアップデート** | 2024年5月10日（PT） | アドビは、2024年6月7日（PT）に、2024年の ISO 地域の更新を実施します。このリリース以降、地理情報（地域）のマイナーな更新が行われる予定です。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
