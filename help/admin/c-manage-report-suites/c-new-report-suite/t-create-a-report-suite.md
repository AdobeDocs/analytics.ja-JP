---
description: Adobe Analyticsでのデータ収集用の基本コンテナの作成
title: レポートスイートの作成
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 63%

---

# レポートスイートの作成

レポートスイートは、Adobe Analytics がレポートの取り込みに使用するデータのサイロです。1 つの組織に複数のレポートスイートを設定し、それぞれ異なるデータセットを含めることができます。以前は個々のレポートスイートを用意することが重要でしたが、今では単一のレポートスイートを使用した方が便利になりました。の導入 [仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) およびレポート時間処理を使用すると、管理者はデータの独自のサブセットを作成でき、グローバルデータとサイト固有のデータの両方を柔軟に取得できます。

この記事は、データ収集の準備をおこなう、システムレベルの管理者またはAdobe Analytics管理者を対象としています。

## 前提条件 

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md):システムレベルの管理者が、Experience CloudAdmin Consoleを使用してAdobe Analyticsへのアクセス権を付与していることを確認します。

## レポートスイートの作成 {#create-report-suite}

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. **[!UICONTROL 新規作成]**／**[!UICONTROL レポートスイート]**&#x200B;をクリックします。
1. レポートスイートの設定をコピーするには、テンプレートリストで、事前定義済みのテンプレートと既存のレポートスイートのどちらを[テンプレート](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)として使用するかを選択します。

   >[!NOTE]
   >
   >設定のみをコピーできます。データはコピーできません。カスタマーケアが設定をコピーする場合は、カスタマーケアから提供されるリスクに関する免責事項についての確認書類を提出する必要があります。詳しくは、[ソースレポートスイートからコピーされない設定](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)を参照してください。

1. 「[新しいレポートスイート](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)」で説明されているフィールドに入力します。
1. 「**[!UICONTROL レポートスイートの作成]**」をクリックします。

レポートスイート ID の最大長は 40 バイトです。 レポートスイートのわかりやすい名前の最大長は 255 バイトです。

## トラブルシューティング

**Experience Cloud にログインすると、Analytics アイコンが灰色に表示される。**

これは、アカウントに Analytics に対する正しい権限が付与されていないことを表します。Adobe Analytics への十分なアクセス権限を持つプロファイルに所属しているかどうかについて、組織内のシステムレベルの管理者に確認します。

**Adobe Analytics にログインしても、「Adobe Analytics へようこそ」ポップアップとドロップダウンが表示されない。**

次を通じてログインしていることを確認します： [Experience Cloud](https://experience.adobe.com)my.omniture.com 経由ではなく my.omniture.com からログインしたユーザは、レポートスイートセットアップウィザードを使用できません。

## 次の手順

[Adobe Analyticsタグプロパティの作成 ](/help/implement/launch/create-analytics-property.md):Analytics 実装を管理する領域を作成します
