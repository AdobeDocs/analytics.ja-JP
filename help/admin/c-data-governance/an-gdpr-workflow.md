---
description: Adobe Analytics の実装で、データ主体のデータプライバシーアクセスおよび削除権限をサポートできるようにする手順の概要を説明します。
title: プライバシーワークフロー
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# プライバシーワークフロー

このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

1. **データ保持ポリシーを設定します。** データプライバシーデータのアクセス/削除要求に対するAdobeには、データ保持ポリシーが必要です。詳しくは、[データ保持のFAQ](/help/technotes/data-retention.md)を参照してください。
1. **DULE／データプライバシーラベル、Adobe Analytics ID、名前空間および ID 拡張について確認します。** 詳しくは、 Analytics変 [数のデータプライバシーラベルおよびラベル設](/help/admin/c-data-governance/gdpr-labels.md) 定に関するベス [トプラクティスを参照してください](/help/admin/c-data-governance/gdpr-analytics-ids.md)。
1. **レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。** ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になっている場合は、ラベル設定が必要な可能性のある新しい変数を公開できるので、ラベル設定を確認します。 モバイルアプリやWebサイトの再実装によって、既存の変数の使用方法が変わる場合があります。これにより、ラベルを更新する必要が生じる場合もあります。 [レポートスイートデータのラベル付け](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)を参照してください。
1. **Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。** Adobe Analytics をご利用のお客様は、[Adobe Experience Cloud データプライバシー API](https://www.adobe.io/apis/experienceplatform/gdpr.html) を呼び出すことで、顧客データに対するデータプライバシーのアクセス要求および削除要求を個別に送信できます。[ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md)の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。
1. **レポートスイートのデータプライバシー設定を表示、管理します。** 詳しく [は、レポートスイートのデータガバナンス設定の表示](/help/admin/c-data-governance/gdpr-view-settings.md)を参照してください。
