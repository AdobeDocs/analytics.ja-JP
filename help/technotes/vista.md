---
title: Adobe Analyticsの VISTA ルール
description: VISTA ルールとその機能の詳細を説明します。
source-git-commit: 1e2284fd4a62816b27b33a91f3bee2575a852107
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# Adobe Analyticsの VISTA ルール

VISTA ルールは、データ収集と処理の間で適用できるカスタムデータ変更の代替形式です。 詳しくは、 [処理順序](processing-order.md) を参照してください。 VISTA ルールは、現在のデータが収集されたときにのみ影響します。既存のデータは変更されません。

VISTA ルールの一般的な使用例を次に示します。

* Analytics ヒットをレポートスイート間でコピーします（オプションで、コピーしたレポートスイートにデータを変更します）。
* が提供する使用例を超えるカスタム IP 除外 [IP で除外](/help/admin/admin/exclude-ip.md)
* 任意の変数値を条件付きまたはグローバルに変更する
* 他の変数に変数値が重複しています
* 変数の値に影響を与える可能性のあるAdobeFTP サイトにファイルをアップロードします

VISTA ルールの多くの使用例は、既に次のようにして提供されています。 [処理ルール](/help/admin/admin/c-processing-rules/processing-rules.md), [ボットルール](/help/admin/admin/bot-removal/bot-rules.md), [仮想レポートスイート](/help/components/vrs/vrs-about.md)またはAdobe Analyticsの実装を更新するだけです。 Adobeは、最後の手段としてのみ VISTA ルールを推奨します。

>[!IMPORTANT]
>
>VISTA ルールを使用するには、お客様の組織とAdobe Professional Servicesの間で有料契約が必要です。 VISTA ルールを作成または更新する場合は、Adobeのアカウントマネージャーにお問い合わせください。

## VISTA ルールを作成する

VISTA ルールを作成するには、Adobe Professional Servicesと連携する必要があります。 VISTA ルールを作成する場合は、担当のAdobeアカウントマネージャーにお問い合わせください。

## 既存の VISTA ルールを見る

Adobeには、既存の VISTA ルールを表示する UI は用意されていません。 既存の VISTA ルールのリストを取得するには、担当のAdobeのアカウントマネージャーまたはカスタマーケアに、必要なレポートスイートに問い合わせてください。
