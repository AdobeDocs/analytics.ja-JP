---
description: このドキュメントでは、データサブジェクトのGDPRアクセスおよび削除権限をサポートするためにAdobe Analyticsで行う必要があることを説明します。
title: Adobe Analytics と GDPR
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe Analytics と GDPR

このドキュメントでは、データサブジェクトのGDPRアクセスおよび削除権限をサポートするためにAdobe Analyticsで行う必要があることを説明します。

## アドビの概要 {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]このドキュメントの内容は法的な助言ではなく、その代用になるものでもありません。GDPR に関する助言については、お客様の企業の法務部門にご相談ください。

2018 年 5 月 25 日に、欧州連合の General Data Protection Regulation（GDPR）が施行されました。アドビの対応と、アドビの製品をご利用のお客様への影響について詳しくは、[GDPR とお客様への影響](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html)を参照してください。

アドビはソフトウェアやサービスを企業に提供する際に、サービスの一環として、お客様に代わって個人データの受信および保管をおこなうデータ処理者としての役割を果たします。アドビはデータ処理者として、お客様の許可と指示（お客様とアドビとの間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、アドビに処理および保管を委任する個人データを決めます。Adobe Experience Cloud ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が Adobe Experience Cloud アカウントに送信するよう設定した情報に基づいて、アドビは個人データをホストします。サンプルのリストについては、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/jp/privacy/experience-cloud.html#collect)を参照してください。

![](assets/privacy_ready.png)

## アドビによる GDPR データの処理方法 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform(ACP)は、ブランドのデータガバナンスインフラストラクチャと、消費者エクスペリエンスの作成と管理に使用するアドビのツールを結び付ける統合ソリューションを提供します。 Adobe Cloud Platformのデータガバナンス機能を使用すると、データガバナンスポリシーとデータの使用とを直接連携させることができます。

「[Adobe Analytics による GDPR の処理方法](https://www.adobe.com/jp/data-analytics-cloud/analytics/general-data-protection-regulation.html)」を確認してください。ここでは、GDPR 対応の手順と、Adobe Experience Cloud GDPR API との統合方法について説明しています。

## GDPR 対応の準備とお客様の Adobe Analytics データ {#section_9A47CDCD614C42238F6E05CFF0180195}

アドビは、お客様自身がレポートスイートのカスタムデータのことを最も熟知していると考えているので、お客様がデータガバナンスの各種設定を指定できるようにしています。

そのため Adobe Analytics にはデータガバナンス用ユーザーインターフェイスが用意されており、データ管理者であるお客様は、Analytics のレポートスイートと、レポートスイート内のすべてのディメンションと指標に[プライバシー用ラベル](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)を設定できます。データセット内の、直接識別可能なデータまたは間接的に識別可能なデータを含む列を識別して、アクセスを送信し、そのデータに対応するリクエストを削除できます。 リクエストごとに、Analyticsデータガバナンスユーザーインターフェイスで定義されたラベルが、そのリクエストに対応する特定の識別子に適用されます。

See [Label Report Suite Data](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) for more information on how to set the labels.

## 前提条件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* [GDPR 関連の用語](/help/admin/c-data-governance/gdpr-terminology.md)について学びます。
* ログイン会社名と Experience Cloud 組織をリンクさせます（まだリンクさせていない場合）。アドビカスタマーケアに問い合わせ、[組織とアカウントのリンク設定](https://marketing.adobe.com/resources/help/ja_JP/mcloud/organizations.html)についてお尋ねください。
* データガバナンスの設定をおこなう Adobe Analytics のレポートスイートを、[Experience Cloud 組織](https://marketing.adobe.com/resources/help/ja_JP/mcloud/report-suite-mapping.html)にマッピングします。
* GDPR の削除要求およびアクセス要求に対応できるよう、各レポートスイートのデータ保持ポリシーを設定します。

   > [!NOTE]データ保持期間が設定されていないと、Adobe Analytics は、GDPR API への要求の処理（お客様のエンドユーザーからのアクセス要求または削除要求の処理）をサポートすることはできません。データ保持期間を設定するには、カスタマーサクセスマネージャーにお問い合わせください。

* 権限の確認：adobe Analyticsでデータガバナンス管理インターフェイスを使用するには、Adobe Analytics管理者である必要があります。
