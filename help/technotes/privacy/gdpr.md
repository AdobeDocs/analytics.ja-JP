---
description: このドキュメントでは、データ主体のGDPR アクセス権と削除権をサポートするためにAdobe Analyticsで何をすべきかを説明します。
title: Adobe Analytics と GDPR
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
TQID: 'https://experienceleague.adobe.com/G-3emGJR0FMicoTI8WUlWdM3SSoWjGb7sr6lxqceBdg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 55%

---

# Adobe Analytics と GDPR

このドキュメントでは、データ主体のGDPR アクセス権と削除権をサポートするためにAdobe Analyticsで何をすべきかを説明します。

>[!IMPORTANT]
>
>このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。 GDPR に関する助言については、お客様の企業の法務部門にご相談ください。

2018年5月25日に、欧州連合の General Data Protection Regulation（GDPR）が施行されました。 アドビの対応と、アドビの製品をご利用のお客様への影響について詳しくは、 [GDPR とお客様への影響](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html) を参照してください。

アドビはソフトウェアやサービスを企業に提供する際に、サービスの一環として、お客様に代わって個人データの受信および保管をおこなうデータ処理者としての役割を果たします。 アドビはデータ処理者として、お客様の許可と指示（お客様とアドビとの間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、アドビに処理および保管を委任する個人データを決めます。 Adobe CX Enterprise ソリューションを使用する場合、Adobeは、使用するソリューションとAdobe CX Enterprise アカウントに送信する情報に応じて、個人データをホストする場合があります。 例の一覧については、[Adobe CX Enterprise privacy.](https://www.adobe.com/jp/privacy/experience-cloud.html#collect)を参照してください。

![](assets/privacy_ready.png)

## アドビによる GDPR データの処理方法

Adobe CX Enterpriseでは、企業のデータガバナンスインフラストラクチャと、消費者体験の構築と管理に使用するAdobeツールを結びつける統合ソリューションを提供します。 Adobe CX Enterpriseのデータガバナンス機能は、データガバナンスポリシーとデータ利用を結びつけることを可能にします。

GDPR対応の手順と、Adobe CX Enterprise GDPR APIとの統合方法について、[Adobe AnalyticsでのGDPRの扱い方](https://www.adobe.com/jp/data-analytics-cloud/analytics/general-data-protection-regulation.html)を理解します。

## GDPR 対応の準備とお客様の Adobe Analytics データ

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。

そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels)を設定できます。 直接識別可能なデータまたは間接識別可能なデータを含むデータセットの列を特定して、そのデータに対応するためにアクセス要求と削除要求を送信できます。 リクエストごとに、Analytics Data Governance ユーザーインターフェイスで定義されたラベルは、そのリクエストに対応する特定の識別子に対して適用されます。

ラベルの設定方法について詳しくは、[レポートスイートデータのラベル設定](/help/admin/tools/privacy-labeling/labeling-overview.md)を参照してください。
