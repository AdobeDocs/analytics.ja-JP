---
description: Adobe Analytics の実装で、データ主体のデータプライバシーアクセスおよび削除権限をサポートできるようにする手順の概要を説明します。
title: プライバシーワークフロー
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 100%

---

# プライバシーワークフロー

このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

1. **データ保持ポリシーを設定します。** アドビがデータプライバシーデータのアクセス／削除要求に対応するため、データ保持ポリシーが必要です。詳しくは、[データ変更 FAQ](/help/technotes/data-retention.md) を参照してください。
1. **DULE／データプライバシーラベル、Adobe Analytics ID、名前空間および ID 拡張について確認します。** 詳しくは、[Analytics 変数のデータプライバシーラベル](/help/admin/c-data-governance/gdpr-labels.md) および [ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md) を参照してください。
1. **レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。** ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは web サイトを再実装すると、既存の変数の使用方法が変わる可能性があるため、ラベルを更新する必要が生じる可能性があります。[レポートスイートのデータのラベル設定](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) を参照してください。
1. **Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。** Adobe Analytics をご利用のお客様は、[Adobe Experience Cloud データプライバシー API](https://www.adobe.io/apis/experienceplatform/gdpr.html) を呼び出すことで、顧客データに対するデータプライバシーのアクセス要求および削除要求を個別に送信できます。[ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md) の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。
1. **レポートスイートのデータプライバシー設定を表示、管理します。** 詳しくは、 [レポートスイートのデータガバナンス設定を表示](/help/admin/c-data-governance/gdpr-view-settings.md) を参照してください。
