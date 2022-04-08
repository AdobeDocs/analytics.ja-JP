---
description: Adobe Analytics でデータ収集用の基本コンテナを作成します
title: レポートスイートの作成
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# レポートスイートの作成

レポートスイートは、Adobe Analytics がレポートの取り込みに使用するデータのサイロです。1 つの組織に複数のレポートスイートを設定し、それぞれ異なるデータセットを含めることができます。以前は個々のレポートスイートを用意することが重要でしたが、今では単一のレポートスイートを使用した方が便利になりました。[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja#virtual-report-suites)とレポート時間処理を導入したことで、管理者は独自のデータサブセットを作成でき、グローバルデータとサイト固有のデータの両方を柔軟に取得できるようになりました。

この記事は、データ収集の準備をするシステムレベル管理者または Adobe Analytics 管理者を対象としています。

## 前提条件

[Adobe Analytics はじめての管理ガイド](/help/admin/admin-console/first-admin-guide.md)：Experience Cloud Admin Console でシステムレベル管理者から Adobe Analytics へのアクセスを許可されていることを確認します。

## レポートスイートの作成 {#create-report-suite}

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;をクリックします。
1. **[!UICONTROL 新規作成]**／**[!UICONTROL レポートスイート]**&#x200B;をクリックします。
1. 事前定義済みのテンプレートか既存のレポートスイートのどちらかを選択し、 [テンプレート](../c-report-suite-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >設定のみをコピーできます。データはコピーできません。カスタマーケアが設定をコピーする場合は、カスタマーケアから提供されるリスクに関する免責事項についての確認書類を提出する必要があります。詳しくは、[ソースレポートスイートからコピーされない設定](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)を参照してください。

1. 「[新しいレポートスイート](../c-new-report-suite/new-report-suite.md)」で説明されているフィールドに入力します。
1. 「**[!UICONTROL レポートスイートの作成]**」をクリックします。

レポートスイート ID の最大長は 40 バイトです。レポートスイートのわかりやすい名前の最大長は 255 バイトです。

## トラブルシューティング

**Experience Cloud にログインすると、Analytics アイコンが灰色に表示される。**

これは、アカウントに Analytics に対する正しい権限が付与されていないことを表します。Adobe Analytics への十分なアクセス権限を持つプロファイルに所属しているかどうかについて、組織内のシステムレベルの管理者に確認します。

## 次の手順

[Adobe Analytics タグプロパティの作成](/help/implement/launch/create-analytics-property.md)：Analytics 実装を管理する領域を作成します.
