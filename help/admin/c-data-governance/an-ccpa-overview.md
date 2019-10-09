---
description: このドキュメントでは、データサブジェクトのCCPAアクセスおよび削除権限をサポートするためにAdobe Analyticsで行う必要がある操作について説明します。
seo-description: このドキュメントでは、データサブジェクトのCCPAアクセスおよび削除権限をサポートするためにAdobe Analyticsで行う必要がある操作について説明します。
seo-title: Adobe AnalyticsとCCPA
title: Adobe AnalyticsとCCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Adobe AnalyticsとCCPA

このドキュメントでは、データサブジェクトのCCPAアクセスおよび削除権限をサポートするためにAdobe Analyticsで行う必要がある操作について説明します。

## アドビの概要

>[!IMPORTANT]このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。CCPAに関するアドバイスは、貴社の法務部にお問い合わせください。

2020年1月1日、カリフォルニア消費者プライバシー法(CCPA)が施行されます。 For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

アドビはソフトウェアやサービスを企業に提供する際に、サービスの一環として、お客様に代わって個人データの受信および保管をおこなうデータ処理者としての役割を果たします。データ処理装置として、アドビは、お客様の会社の許可と手順（例えば、アドビとの契約に基づいて）に従って個人データを処理します。

データコントローラーは、アドビが処理し、お客様に代わって保存する個人データを決定します。 Adobe Experience Cloud ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が Adobe Experience Cloud アカウントに送信するよう設定した情報に基づいて、アドビは個人データをホストします。For a list of examples, see [Adobe Experience Cloud privacy.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## アドビによるCCPAデータの処理方法

Adobe Cloud Platform（ACP）には統合型ソリューションが用意されており、お客様のデータガバナンスインフラストラクチャと、顧客エクスペリエンスを作成および管理するためのアドビのツールを連携させることができます。Adobe Cloud Platform のこのデータガバナンス機能によって、データガバナンスポリシーとデータ利用を直接リンクさせることができます。

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## CCPA ReadinessとAdobe Analyticsデータ

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2)を設定できます。お客様は、個人を直接的または間接的に特定できるデータを含むデータセット内の列を識別し、それらのデータに対するアクセス要求または削除要求を送信できます。各要求では、Analytics のデータガバナンス用ユーザーインターフェイスで設定されたラベルが、対象の要求に対応する固有識別子として扱われます。

ラベルの設定方法について詳しくは、[レポートスイートのデータのラベル設定](/help//admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731)を参照してください。

## 前提条件

* Familiarize yourself with [Privacy terminology.](/help/admin/c-data-governance/gdpr-terminology.md#concept_83C744A9D077476BAD8F8492DF68EBD7)
* ログイン会社名と Experience Cloud 組織をリンクさせます（まだリンクさせていない場合）。Contact Adobe Customer Care and refer to [Organizations and account linking.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Map any Adobe Analytics report suite that you want to set up for data governance to [your Experience Cloud organization.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* CCPAの削除およびアクセスのリクエストを受け入れられるように、各レポートスイートにデータ保持ポリシーを設定します。

   Adobe Analyticsでデータ保持期間が設定されていない場合、Adobe Analyticsは、Privacy Services APIに対するリクエストの処理、つまり、エンドユーザーから受け取るアクセスまたは削除のリクエストの処理を支援できません。 データ保持期間の設定については、カスタマーサクセスマネージャーまでお問い合わせください。

* 権限の確認：Adobe Analytics でデータガバナンス管理インターフェイスを使用するには、Adobe Analytics の管理者である必要があります。
* ヒットレベルで同 [意ステータスを追跡するには](/help/admin/c-data-governance/consent-variables.md) 、同意管理変数の実装を検討します。
