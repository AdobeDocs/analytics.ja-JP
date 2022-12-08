---
title: Adobe Analytics の VISTA ルール
description: VISTA ルールとその機能の詳細について説明します。
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 100%

---

# Adobe Analytics の VISTA ルール

VISTA ルールは、データ収集と処理の間で適用できるカスタムデータ変更の代替形式です。VISTA ルールが適用されるデータパイプラインの正確なステージについて詳しくは、[処理順序](processing-order.md)を参照してください。VISTA ルールは、現在収集されているデータにのみ影響します。既存のデータは変更されません。

VISTA ルールの一般的なユースケースには、例えば、次のものがあります。

* レポートスイート間で Analytics ヒットをコピーする（オプションで、コピーしたレポートスイートにデータを変更する）
* [IP による除外](/help/admin/admin/exclude-ip.md)で提供されるユースケースを超えるカスタム IP 除外
* 任意の変数値を条件付きまたはグローバルに変更する
* 変数値を他の変数に複製する
* 変数値に影響を及ぼす可能性のあるファイルを Adobe FTP サイトにアップロードする

VISTA ルールの多くのユースケースは、[処理ルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)、[ボットルール](/help/admin/admin/bot-removal/bot-rules.md)または[仮想レポートスイート](/help/components/vrs/vrs-about.md)で既に提供されているか、Adobe Analytics 実装を更新するだけで提供されます。アドビでは、VISTA ルールは最後の手段としてのみ使用することをお勧めします。

>[!IMPORTANT]
>
>VISTA ルールを使用するには、所属する組織と Adobe Professional Services の間の有料契約が必要です。VISTA ルールを作成または更新する場合は、所属する組織のアドビ担当営業または販売店にお問い合わせください。

## VISTA ルールの作成

VISTA ルールを作成するには、Adobe Professional Services と連携する必要があります。VISTA ルールを作成する場合は、所属する組織のアドビ担当営業または販売店にお問い合わせください。

## 既存の VISTA ルールの参照

アドビでは、既存の VISTA ルールを表示する UI は提供していません。既存の VISTA ルールのリストを取得するには、所属する組織のアドビ担当営業または販売店またはカスタマーケアに、目的のレポートスイートをお問い合わせください。
