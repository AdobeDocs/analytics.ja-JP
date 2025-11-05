---
title: Adobe Analytics の VISTA ルール
description: VISTA ルールとその機能の詳細について説明します。
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 57%

---

# Adobe Analytics の VISTA ルール

VISTA ルールは、データ収集と処理の間で適用できるカスタムデータ変更の代替形式です。VISTA ルールが適用されるデータパイプラインの正確なステージについて詳しくは、[処理順序](processing-order.md)を参照してください。VISTA ルールは、現在収集されているデータにのみ影響します。既存のデータは変更されません。

VISTA ルールの一般的なユースケースには、例えば、次のものがあります。

* レポートスイート間で Analytics ヒットをコピーする（オプションで、コピーしたレポートスイートにデータを変更する）
* [IP による除外](/help/admin/tools/exclude-ip.md)で提供されるユースケースを超えるカスタム IP 除外
* 任意の変数値を条件付きまたはグローバルに変更する
* 変数値を他の変数に複製する
* 変数値に影響を及ぼす可能性のあるファイルを Adobe FTP サイトにアップロードする

VISTA ルールの多くのユースケースは、[処理ルール](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)、[ボットルール](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)または[仮想レポートスイート](/help/components/vrs/vrs-about.md)で既に提供されているか、Adobe Analytics 実装を更新するだけで提供されます。アドビでは、VISTA ルールは最後の手段としてのみ使用することをお勧めします。

>[!IMPORTANT]
>
>VISTA ルールの実装と設定には、お客様とAdobe Professional Servicesの間の有料契約が必要です。 VISTA ルールを作成または更新する場合は、Adobe アカウントチームにお問い合わせください。
>
>注意：
>
>* VISTA ルールの作成には、初期実装のみが含まれます。 継続的なメンテナンスや VISTA ルールの更新には、個別の有料エンゲージメントが必要です。
>
>* VISTA ルールは、データ内の特定の条件に依存します。 例えば、Adobe Analyticsの実装、収集するデータのタイプや文字列の長さ、DB VISTA に使用するテーブルの変更、または入力データパターンに対するその他の変更によって、VISTA ルールが期待どおりに機能しなくなる場合があります。 Adobeでは、VISTA ルールを定期的に確認して、更新または削除が必要かどうかを判断することをお勧めします。

## VISTA ルールの作成 {#create}

VISTA ルールを作成するには、Adobe Professional Services と連携する必要があります。VISTA ルールを作成する場合は、Adobe アカウントチームにお問い合わせください。

## 既存の VISTA ルールの参照 {#see}

アドビでは、既存の VISTA ルールを表示する UI は提供していません。既存の VISTA ルールのリストを取得するには、Adobe アカウントチームまたはカスタマーケアにお問い合わせください。
