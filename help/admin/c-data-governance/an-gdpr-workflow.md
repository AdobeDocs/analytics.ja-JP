---
description: 'null'
title: プライバシーワークフロー
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# プライバシーワークフロー

このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

| タスクの説明 | 手順と詳細情報のリンク |
|--- |--- |
| **手順 1**：データプライバシー関連のデータを含む可能性があるレポートスイートをすべて、Experience Cloud（または IMS）組織にマッピングします。データプライバシー要求は Experience Cloud 組織を使用して送信され、その組織が要求するすべてのレポートスイートに適用されます。要求は、その組織にマッピングされていないレポートスイートには適用されません。ログイン会社のレポートスイートだったとしてもそれは同様です。 | [組織へのレポートスイートのマッピング](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)を参照してください。 |
| **手順2**:データ保持ポリシーを設定します。 | アドビがデータプライバシーのデータのアクセス要求および削除要求に対応できるよう、データ保持ポリシーを設定する必要があります。詳しくは、この[Analytics データ保持の FAQ](/help/technotes/data-retention.md) を参照してください。 |
| **手順 3：** DULE／データプライバシーラベル、Adobe Analytics ID、名前空間および ID 拡張について確認します。 | このドキュメントの以下のトピックを参照してください。<ul><li>[Analytics 変数のデータプライバシーラベル](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **手順 4**：レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。注意：ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは Web サイトを再実装すると、既存の変数の使用方法が変わる可能性があり、これにより、ラベルを更新する必要が生じる可能性があります。 | 「[レポートスイートデータのラベル付け](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)」の手順に従います。 |
| **手順 5**：Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。 | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API](https://www.adobe.io/apis/experienceplatform/gdpr.html). [ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md)の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。 |
| **手順 6**：レポートスイートのデータプライバシー設定を表示、管理します。 | 「[レポートスイートのデータガバナンス設定の表示](/help/admin/c-data-governance/gdpr-view-settings.md)」の手順に従います。 |
