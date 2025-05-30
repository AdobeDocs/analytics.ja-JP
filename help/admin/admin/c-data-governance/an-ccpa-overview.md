---
description: このドキュメントでは、CCPA におけるデータ主体のアクセス権および削除権に対応するために、Adobe Analytics でどのような作業が必要かを説明します。
title: Adobe Analytics と CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: ht
source-wordcount: '593'
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

Adobe Experience Cloud には、ブランドのデータガバナンスインフラストラクチャと、消費者エクスペリエンスの作成と管理に使用するアドビのツールを接続する統合ソリューションが用意されています。Adobe Experience Cloud のデータガバナンス機能により、データガバナンスポリシーをデータ使用に直接リンクできます。

「[Adobe Analytics による GDPR の処理方法](https://www.adobe.com/jp/data-analytics-cloud/analytics/general-data-protection-regulation.html)」を確認してください。ここでは、プライバシー対応の手順と、Adobe Experience Cloud プライバシーサービス API との統合方法について説明しています。

## CCPA 対応の準備とお客様の Adobe Analytics データ

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels)を設定できます。お客様は、個人を直接的または間接的に特定できるデータを含むデータセット内の列を識別し、それらのデータに対するアクセス要求または削除要求を送信できます。各要求では、Analytics のデータガバナンス用ユーザーインターフェイスで設定されたラベルが、対象の要求に対応する固有識別子として扱われます。

ラベルの設定方法について詳しくは、[レポートスイートデータのラベル設定](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)を参照してください。

## 前提条件

* [GDPR 関連の用語](/help/admin/c-data-governance/gdpr-terminology.md)について学びます。
* ログイン会社名と Experience Cloud 組織をリンクさせます（まだリンクさせていない場合）。アドビカスタマーケアに問い合わせ、[組織とアカウントのリンク設定](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja)についてお尋ねください。
* CCPA の削除要求およびアクセス要求に対応できるよう、各レポートスイートのデータ保持ポリシーを設定します。

  データ保持期間が設定されていないと、Adobe Analytics は、プライバシーサービス API への要求の処理（お客様のエンドユーザーからのアクセス要求または削除要求の処理）をサポートすることはできません。データ保持期間の設定については、アドビのアカウントチームまでお問い合わせください。

* 権限の確認：Adobe Analytics でデータガバナンス管理インターフェイスを使用するには、Adobe Analytics の管理者である必要があります。
* ヒットレベルで同意ステータスを追跡するには、[同意管理変数](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)の実装を検討してください。
