---
title: レポートスイートの作成
seo-title: Adobe Analyticsでのレポートスイートの作成
description: Adobe Analyticsでデータ収集用の基本コンテナを作成します。
seo-description: Adobe Analyticsでデータ収集用の基本コンテナを作成します。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# レポートスイートの作成

レポートスイートは、Adobe Analyticsがレポートを引き出すために使用するデータのサイロです。組織には多数のレポートスイートを含めることができ、それぞれ異なるデータセットを含みます。これまでは、個別のレポートスイートが重要になっていましたが、単一のレポートスイートを使用するとさらに有利になります。仮想レポートスイートとレポートの時間処理を導入することで、ユーザーは独自のデータサブセットを作成でき、グローバルデータとサイト固有データの両方を柔軟に取得できます。

この記事は、システムレベルの管理者またはAnalytics管理者がデータ収集に備えるために設計されています。

## 前提条件

[Adobe Analytics First Admin Guide](first-admin-guide.md):システムレベルの管理者がExperience Cloud管理コンソールからAdobe Analyticsへのアクセスを許可していることを確認します

## レポートスイートの作成

> [!NOTE]注意:レガシー管理者を使用してAdobe Analyticsでレポートスイートを作成する方法もあります。アドビでは、ここで概説するレポートスイートのセットアップウィザードを使用することをお勧めします。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 右上の9正方形アイコンをクリックし、色付きのAnalyticsロゴをクリックします。
1. "Adobe Analyticsにようこそ」モーダルウィンドウが自動的にポップアップ表示されます。必要に応じて、右上のヘルプアイコンをクリックし、"Adobe Analyticsにようこそ」を選択します。
1. モーダルウィンドウで、「設定を開始」をクリックします。
1. プロパティタイプ、業種、タイムゾーンなどの基本について概説する各プロンプトに従います。「次へ」をクリックします。
1. レポートスイートが作成されるようになりました。アドビでは開発レポートスイートも使用することを推奨しているので、テストで顧客データが無効になることはありません。右上のヘルプアイコンをクリックし、"Adobe Analyticsにようこそ」を再度選択します。
1. モーダルウィンドウで、「セットアップを開始」をクリックします。
末尾に"- DEV"を付加する以外は、このレポートスイートに名前を付けます。このレポートスイートは内部トラフィックのみを受信するので、予測サイズは最小にできます。
1. 「次へ」をクリックして開発レポートスイートの作成を終了します。

## トラブルシューティング

**Experience Cloudにログインすると、Analyticsアイコンが灰色表示になります。**

つまり、アカウントにAnalyticsに対する正しい権限が付与されていないことを意味します。組織レベルの管理者を使用して、Adobe Analyticsにアクセスするための十分な権限を持つプロファイルに属していることを確認します。

**Adobe Analyticsにログインした後、"Adobe Analyticsにようこそ」ポップアップおよびドロップダウンが表示されません。**

. omniture. comではなく、Experience Cloud経由でログインしていることを確認してください。my.omniture.com経由でログインしたユーザーには、レポートスイートのセットアップウィザードがありません。

## 次の手順

[起動時に、Adobe Analyticsのプロパティを作成し、設定](../../implement/implement-with-launch/create-analytics-property.md)します。Analytics実装を管理する領域の作成
