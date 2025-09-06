---
description: Adobe Analytics の実装で、データ主体のデータプライバシーアクセスおよび削除権限をサポートできるようにする手順の概要を説明します。
title: プライバシーワークフロー
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 100%

---

# プライバシーワークフロー

このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

1. Adobe Experience Platform の [Privacy Service の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)ページから始めて、Analytics データにラベルを付ける前にどのような質問をするべきかを把握してください。
1. **データ保持ポリシーを設定します。** アドビがデータプライバシーデータのアクセス／削除要求に対応するため、データ保持ポリシーが必要です。詳しくは、[データ変更に関する FAQ](/help/technotes/data-retention.md) を参照してください。Privacy Service API を使用するには、Adobe Analytics 内でデータ保持期間が設定されていることを確認する必要があります。
1. **データプライバシーラベル、Adobe Analytics ID および名前空間について確認します。** 詳しくは、[Analytics 変数のデータプライバシーラベル](/help/admin/tools/privacy-labeling/labels.md) および [ラベル設定に関するベストプラクティス](/help/admin/tools/privacy-labeling/best-practices.md) を参照してください。
1. **レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。** ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは web サイトを再実装すると、既存の変数の使用方法が変わる可能性があるため、ラベルを更新する必要が生じる可能性があります。[レポートスイートのデータのラベル設定](/help/admin/tools/privacy-labeling/namespaces.md) を参照してください。
1. **Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。** Adobe Analytics をご利用のお客様は、[Adobe Experience Cloud Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=ja) を呼び出すことで、顧客データに対するデータプライバシーのアクセスリクエストと削除リクエストを個別に送信できます。[ラベル設定に関するベストプラクティス](/help/admin/tools/privacy-labeling/best-practices.md) の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。
1. **レポートスイートのデータプライバシー設定を表示、管理します。** 詳しくは、 [レポートスイートのデータガバナンス設定を表示](/help/admin/tools/privacy-labeling/view-settings.md) を参照してください。
