---
description: このドキュメントでは、GDPR におけるデータ主体のアクセス権および削除権に対応するために、Adobe Analytics でどのような作業が必要かを説明します。
title: Adobe Analytics と GDPR
feature: Data Governance
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: ht
source-wordcount: '598'
ht-degree: 100%

---

# Adobe Analytics と GDPR

このドキュメントでは、GDPR におけるデータ主体のアクセス権および削除権に対応するために、Adobe Analytics でどのような作業が必要かを説明します。

## アドビの概要 {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。GDPR に関する助言については、お客様の企業の法務部門にご相談ください。

2018 年 5 月 25 日に、欧州連合の General Data Protection Regulation（GDPR）が施行されました。アドビの対応と、アドビの製品をご利用のお客様への影響について詳しくは、 [GDPR とお客様への影響](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html) を参照してください。

アドビはソフトウェアやサービスを企業に提供する際に、サービスの一環として、お客様に代わって個人データの受信および保管をおこなうデータ処理者としての役割を果たします。アドビはデータ処理者として、お客様の許可と指示（お客様とアドビとの間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、アドビに処理および保管を委任する個人データを決めます。Adobe Experience Cloud ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が Adobe Experience Cloud アカウントに送信するよう設定した情報に基づいて、アドビは個人データをホストします。サンプルのリストについては、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/jp/privacy/experience-cloud.html#collect)を参照してください。

![](assets/privacy_ready.png)

## アドビによる GDPR データの処理方法 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform（ACP）には統合型ソリューションが用意されており、お客様のデータガバナンスインフラストラクチャと、顧客エクスペリエンスを作成および管理するためのアドビのツールを連携させることができます。Adobe Cloud Platform のこのデータガバナンス機能によって、データガバナンスポリシーとデータ利用を直接リンクさせることができます。

「[Adobe Analytics による GDPR の処理方法](https://www.adobe.com/jp/data-analytics-cloud/analytics/general-data-protection-regulation.html)」を確認してください。ここでは、GDPR 対応の手順と、Adobe Experience Cloud GDPR API との統合方法について説明しています。

## GDPR 対応の準備とお客様の Adobe Analytics データ {#section_9A47CDCD614C42238F6E05CFF0180195}

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。

そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)を設定できます。お客様は、個人を直接的または間接的に特定できるデータを含むデータセット内の列を識別し、それらのデータに対するアクセス要求または削除要求を送信できます。各要求では、Analytics のデータガバナンス用ユーザーインターフェイスで設定されたラベルが、対象の要求に対応する固有識別子として扱われます。

ラベルの設定方法について詳しくは、[レポートスイートのデータのラベル設定](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) を参照してください。

## 前提条件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* [GDPR 関連の用語](/help/admin/c-data-governance/gdpr-terminology.md)について学びます。
* ログイン会社名と Experience Cloud 組織をリンクさせます（まだリンクさせていない場合）。アドビカスタマーケアに問い合わせ、[組織とアカウントのリンク設定](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja)についてお尋ねください。
* GDPR の削除要求およびアクセス要求に対応できるよう、各レポートスイートのデータ保持ポリシーを設定します。

   >[!NOTE]
   >
   >データ保持期間が設定されていないと、Adobe Analytics は、GDPR API への要求の処理（お客様のエンドユーザーからのアクセス要求または削除要求の処理）をサポートすることはできません。データ保持期間の設定については、カスタマーサクセスマネージャーまでお問い合わせください。

* 権限の確認：Adobe Analytics でデータガバナンス管理インターフェイスを使用するには、Adobe Analytics の管理者である必要があります。

