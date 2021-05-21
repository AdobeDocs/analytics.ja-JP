---
description: このドキュメントでは、CCPA におけるデータ主体のアクセス権および削除権に対応するために、Adobe Analytics でどのような作業が必要かを説明します。
title: Adobe Analytics と CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '641'
ht-degree: 100%

---

# Adobe Analytics と CCPA

このドキュメントでは、CCPA におけるデータ主体のアクセス権および削除権に対応するために、Adobe Analytics でどのような作業が必要かを説明します。

## アドビの概要

>[!IMPORTANT]
>
>このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。CCPA に関する助言については、お客様の企業の法務部門にご相談ください。

2020 年 1 月 1 日、カリフォルニア州消費者プライバシー法（CCPA）が施行されます。アドビの対応と、アドビの製品をご利用のお客様への影響について詳しくは、[アドビのプライバシーセンター](https://www.adobe.com/jp/privacy.html)を参照してください。

アドビはソフトウェアやサービスを企業に提供する際に、サービスの一環として、お客様に代わって個人データの受信および保管をおこなうデータ処理者としての役割を果たします。アドビはデータ処理者として、お客様の許可と指示（お客様とアドビとの間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、アドビに処理および保管を委任する個人データを決めます。Adobe Experience Cloud ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が Adobe Experience Cloud アカウントに送信するよう設定した情報に基づいて、アドビは個人データをホストします。サンプルのリストについては、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/jp/privacy/experience-cloud.html#collect)を参照してください。

## アドビによる CCPA データの処理方法

Adobe Cloud Platform（ACP）には統合型ソリューションが用意されており、お客様のデータガバナンスインフラストラクチャと、顧客エクスペリエンスを作成および管理するためのアドビのツールを連携させることができます。Adobe Cloud Platform のこのデータガバナンス機能によって、データガバナンスポリシーとデータ利用を直接リンクさせることができます。

「[Adobe Analytics による GDPR の処理方法](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html)」を確認してください。ここでは、プライバシー対応の手順と、Adobe Experience Cloud プライバシーサービス API との統合方法について説明しています。

## CCPA 対応の準備とお客様の Adobe Analytics データ

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)を設定できます。お客様は、個人を直接的または間接的に特定できるデータを含むデータセット内の列を識別し、それらのデータに対するアクセス要求または削除要求を送信できます。各要求では、Analytics のデータガバナンス用ユーザーインターフェイスで設定されたラベルが、対象の要求に対応する固有識別子として扱われます。

ラベルの設定方法について詳しくは、[レポートスイートのデータのラベル設定](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)を参照してください。

## 前提条件

* [GDPR 関連の用語](/help/admin/c-data-governance/gdpr-terminology.md)について学びます。
* ログイン会社名と Experience Cloud 組織をリンクさせます（まだリンクさせていない場合）。アドビカスタマーケアに問い合わせ、[組織とアカウントのリンク設定](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/organizations.html)についてお尋ねください。
* データガバナンスの設定をおこなう Adobe Analytics のレポートスイートを、[Experience Cloud 組織](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)にマッピングします。
* CCPA の削除要求およびアクセス要求に対応できるよう、各レポートスイートのデータ保持ポリシーを設定します。

   データ保持期間が設定されていないと、Adobe Analytics は、プライバシーサービス API への要求の処理（お客様のエンドユーザーからのアクセス要求または削除要求の処理）をサポートすることはできません。データ保持期間の設定については、カスタマーサクセスマネージャーまでお問い合わせください。

* 権限の確認：Adobe Analytics でデータガバナンス管理インターフェイスを使用するには、Adobe Analytics の管理者である必要があります。
* ヒットレベルで同意ステータスを追跡するには、[同意管理変数](/help/admin/c-data-governance/consent-variables.md)の実装を検討してください。
