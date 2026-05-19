---
description: Adobe Analytics でデータ収集用の基本コンテナを作成します
title: レポートスイートの作成
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
TQID: https://experienceleague.adobe.com/ZmPcYHvXOhaXXnqsSVUh1bpvignxomS3d4S76iMCAa4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 87%

---

# レポートスイートの作成

レポートスイートは、Adobe Analytics がレポートの取り込みに使用するデータのサイロです。 1 つの組織に複数のレポートスイートを設定し、それぞれ異なるデータセットを含めることができます。 以前は個々のレポートスイートを用意することが重要でしたが、今では単一のレポートスイートを使用した方が便利になりました。 [仮想レポートスイート](/help/components/vrs/vrs-about.md#virtual-report-suites)とレポート時間処理を導入したことで、管理者は独自のデータサブセットを作成でき、グローバルデータとサイト固有のデータの両方を柔軟に取得できるようになりました。

この記事は、データ収集の準備をするシステムレベル管理者または Adobe Analytics 管理者を対象としています。

## 前提条件

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md)：システムレベルの管理者が、CX Enterprise Admin Consoleを介したAdobe Analyticsへのアクセス権を付与していることを確認します。

## レポートスイートの作成 {#create-report-suite}

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;をクリックします。
1. 「**[!UICONTROL レポートスイートを追加]**」をクリックします。
1. 事前定義済みのテンプレートと既存のレポートスイートのどちらを[テンプレート](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md)として使用するかを選択します。

   >[!NOTE]
   >
   >設定のみをコピーできます。データはコピーできません。 カスタマーケアが設定をコピーする場合は、カスタマーケアから提供されるリスクに関する免責事項についての確認書類を提出する必要があります。 詳しくは、[ソースレポートスイートからコピーされない設定](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md)を参照してください。

1. [新しいレポートスイート](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)で説明されているフィールドに入力します。
1. 「**[!UICONTROL レポートスイートを作成]**」をクリックします。

レポートスイート ID の最大長は 40 バイトです。 レポートスイートのわかりやすい名前の最大長は 255 バイトです。

## トラブルシューティング

**CX Enterpriseにログインすると、Analytics アイコンがグレー表示されます。**

これは、アカウントに Analytics に対する正しい権限が付与されていないことを表します。 Adobe Analytics への十分なアクセス権限を持つプロファイルに所属しているかどうかについて、組織内のシステムレベルの管理者に確認します。

## 次の手順

[Adobe Analytics タグプロパティの作成](/help/implement/launch/create-analytics-property.md)：Analytics 実装を管理する領域を作成します。
