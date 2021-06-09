---
description: Adobe Analyticsでのデータ収集用の基本コンテナの作成
title: レポートスイートの作成
feature: 管理ツール
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: b7d71e89c427f1f8ffe68beb1e83646c54e92825
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 62%

---

# レポートスイートの作成

レポートスイートは、Adobe Analytics がレポートの取り込みに使用するデータのサイロです。1 つの組織に複数のレポートスイートを設定し、それぞれ異なるデータセットを含めることができます。以前は個々のレポートスイートを用意することが重要でしたが、今では単一のレポートスイートを使用した方が便利になりました。[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites)とレポート時間処理が導入され、管理者は独自のデータサブセットを作成でき、グローバルデータとサイト固有のデータの両方を柔軟に取得できます。

この記事は、データ収集の準備をおこなうシステムレベルの管理者またはAdobe Analytics管理者向けに作成されています。

## 前提条件

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md):システムレベルの管理者から、Experience CloudAdmin Consoleを使用したAdobe Analyticsへのアクセス権が付与されていることを確認します。

## レポートスイートの作成 {#create-report-suite}

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. **[!UICONTROL 新規作成]**／**[!UICONTROL レポートスイート]**&#x200B;をクリックします。
1. レポートスイートの設定をコピーするには、テンプレートリストで、事前定義済みのテンプレートと既存のレポートスイートのどちらを[テンプレート](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)として使用するかを選択します。

   >[!NOTE]
   >
   >設定のみをコピーできます。データはコピーできません。カスタマーケアが設定をコピーする場合は、カスタマーケアから提供されるリスクに関する免責事項についての確認書類を提出する必要があります。詳しくは、[ソースレポートスイートからコピーされない設定](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)を参照してください。

1. 「[新しいレポートスイート](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)」で説明されているフィールドに入力します。
1. 「**[!UICONTROL レポートスイートの作成]**」をクリックします。

レポートスイートIDの最大長は40バイトです。 レポートスイートのわかりやすい名前の最大長は255バイトです。

## トラブルシューティング

**Experience Cloud にログインすると、Analytics アイコンが灰色に表示される。**

これは、アカウントに Analytics に対する正しい権限が付与されていないことを表します。Adobe Analytics への十分なアクセス権限を持つプロファイルに所属しているかどうかについて、組織内のシステムレベルの管理者に確認します。

**Adobe Analytics にログインしても、「Adobe Analytics へようこそ」ポップアップとドロップダウンが表示されない。**

my.omniture.comではなく、[Experience Cloud](https://experience.adobe.com)を使用してログインしていることを確認します。 my.omniture.com からログインしたユーザは、レポートスイートセットアップウィザードを使用できません。

## 次の手順

[Adobe Experience Platform LaunchでAdobe Analyticsのプロパティを作成および設定します](/help/implement/launch/create-analytics-property.md)。Analytics実装を管理する領域を作成する
