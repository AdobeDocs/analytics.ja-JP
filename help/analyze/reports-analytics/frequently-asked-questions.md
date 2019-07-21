---
description: Analytics に関して最もよくある質問に対する回答とトラブルシューティングの提案を示します。
keywords: Analytics のトラブルシューティング
seo-description: Analytics に関して最もよくある質問に対する回答とトラブルシューティングの提案を示します。
seo-title: よくある質問
title: よくある質問
uuid: 285b0ea4- aa07-4d39- a74f-37b1d02d19f1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# よくある質問

Reports&amp; Analyticsの最も頻繁に使用されるAnalytics質問の一部に対する回答およびトラブルシューティングの提案を示します。For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**アカウントがロックされています。ロック解除する方法**

アカウントを再アクティブ化するには、組織内の管理者にお問い合わせください。See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**データが収集されていても、空白のレポートが表示されるのはなぜですか。**

レポートデータのトラブルシューティングにはいくつかの点があります。

* 使用する指標のチェック:Reports&amp; Analyticsでは、デフォルトで売上高が使用されます。表示する指標がレポートに関連していることを確認してください。
* 日付範囲の確認:日付範囲（特に組織のデータ保持ポリシーを超えている場合）は、データを返さないことがあります。日付範囲が正しく設定されていることを確認してください。
* 内部URLフィルタのチェック:一部のトラフィックソースレポートは、内部URLフィルタを正しく定義するまで機能しません。

**ナビゲーションメニューに一部のレポートが表示されないのはなぜですか。**

メニューに表示されないレポートは、制限付き権限またはメニューのカスタマイズによって最も多く発生します。組織内の製品管理者に連絡して、必要なすべてのディメンションおよび指標にアクセスできること、およびレポートスイートのメニュー構造がカスタマイズされていないことを確認します。

**長期間の値が断ち切れるのはなぜですか。**

Adobe Analyticsのほとんどの変数には、文字制限があります。ページ名には100文字の制限があり、カスタムコンバージョン変数（eVar）には255文字の制限があります。アドビでは、切り捨てを防ぐために、アドビに送信する値を簡潔にすることをお勧めします。

**レポートに大きな遅延が表示されるのはなぜですか。**

リアルタイムレポートでは、いくつかのトラフィック指標を数分以内に使用できますが、コンバージョンやその他の処理中心データは通常30~90分以内に利用できます。Experience Cloud プラットフォームは堅牢ですが、いくつかの状況下ではレポーティングに遅延が生じることがあります。この遅延は遅延と呼ばれます。See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**iPhoneでデバイスのバージョンが表示されないのはなぜですか。**

Appleデバイスは、デバイスのバージョンではなく、ユーザーエージェント文字列にファームウェアバージョンをレポートします。Adobe Analyticsで使用できる情報を使用してiPhoneデバイスのバージョンを判断するのは困難です。See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**レポートの一番下の合計が値と値と一致しないのはなぜですか。**

ディメンション値は複数の場所に適用することがよくあります。例えば、午前0時にまたがる訪問、または1回の注文に属する複数の製品。ディメンション値は、該当するすべての行項目にわたってレポートされますが、レポートの合計で重複しません。See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**レポートスイートの特定のIPアドレスからデータを除外する方法を教えてください。**

サイトのテストや従業員の使用など、社内のWebサイト活動からのデータをレポートから除外できます。この機能により、自身や会社の同僚はトラフィックデータを歪曲することなく、自社サイトを訪問することができます。See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**レポートスイートを削除できますか。**

レポートスイートの削除はできません。ただし、レポートスイートはAdobe Analyticsのすべてのビューに表示されません。非表示のレポートスイートに送信されるサーバー呼び出しは、引き続き月額契約にカウントされます。See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**セグメント化を使用する場合、どのコンテナを使用すべきですか。Page view, visit, or visitor?**

使用するセグメントコンテナは、データを取得する範囲によって異なります。ページビューコンテナは、セグメント条件に一致するヒットのみを取り込み、訪問の無関係な部分を除外するのに役立ちます。訪問コンテナは、1つまたは複数のヒットがセグメント条件と一致するヒットのヒットをすべて取得し、一般的にセッションを調べるのに役立ちます。訪問者コンテナは、セグメント条件に一致するヒットがすべての訪問に取り込まれ、訪問者を確認するのに役立ちます。使用する最適なセグメントコンテナを決定するためのアナリストとして選択できます。See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**セグメントがData Warehouseに表示されないのはなぜですか。**

Data Warehouseの一意の処理アーキテクチャにより、パスなどのデータタイプを処理するためにプラットフォームは最適化されません。See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
