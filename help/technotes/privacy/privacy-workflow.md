---
description: Adobe Analytics の実装で、データ主体のデータプライバシーアクセスおよび削除権限をサポートできるようにする手順の概要を説明します。
title: プライバシーワークフロー
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# プライバシーワークフロー

このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

1. Adobe Experience Platform の [Privacy Service の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)ページから始めて、Analytics データにラベルを付ける前にどのような質問をするべきかを把握してください。
1. **データ保持ポリシーを設定します。** Adobeがデータプライバシーデータへのアクセス/削除要求を処理するには、データ保持ポリシーが必要です。  詳しくは、[データ変更に関する FAQ](/help/technotes/data-retention.md) を参照してください。 Privacy Service API を使用するには、Adobe Analytics 内でデータ保持期間が設定されていることを確認する必要があります。
1. **データプライバシーラベル、Adobe Analytics ID、および名前空間について理解します。** Analytics変数の[&#x200B; データプライバシーラベル &#x200B;](/help/admin/tools/privacy-labeling/labels.md)および[&#x200B; ラベル付けのベストプラクティス &#x200B;](/help/admin/tools/privacy-labeling/best-practices.md)を参照してください。
1. **レポートスイートの各変数に、ID、機密性、データガバナンスのラベルを割り当てます。** ラベル付けは、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数が有効になるたびに確認する必要があります。 また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。 モバイルアプリまたは web サイトを再実装すると、既存の変数の使用方法が変わる可能性があるため、ラベルを更新する必要が生じる可能性があります。 [レポートスイートのデータのラベル設定](/help/admin/tools/privacy-labeling/namespaces.md) を参照してください。
1. **Adobe Data Privacy APIに接続し、アクセス要求と削除要求を送信します。** Adobe Analyticsのお客様は、[Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=ja)を呼び出して、お客様のデータにアクセスして削除するための個々のデータプライバシーリクエストを送信できます。 [ラベル設定に関するベストプラクティス](/help/admin/tools/privacy-labeling/best-practices.md) の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。
1. **レポートスイートのデータプライバシー設定を表示および管理します。** [&#x200B; レポートスイートのデータガバナンス設定の表示](/help/admin/tools/privacy-labeling/view-settings.md)を参照してください。
