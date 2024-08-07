---
title: ファーストタッチチャネル
description: 訪問者のエンゲージメント期限内で最初のマーケティングチャネル。
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 91%

---

# ファーストタッチチャネル

「ファーストタッチチャネル [ ディメンション ](overview.md) は、訪問者のエンゲージメント期間中（デフォルトでは 30 日）に訪問者が最初にマッチしたマーケティングチャネルをレポートします。 このディメンションは、初回トラフィックを貴社のサイトに導くマーケティングチャネルを把握するのに役立ち、最も効果的な分野でマーケティング活動に焦点を当てることができます。

## このディメンションへのデータ入力

このディメンションは、[マーケティングチャネルマネージャー](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)で定義したチャネル名を直接参照します。

アドビのデータ収集サーバーに送信されるすべてのヒットは、レポートスイートのマーケティングチャネルの処理ルールを通じて実行されます。各ルールを数値順に繰り返し処理し、一致が見つかると、そのマーケティングチャネルがヒットに結び付けます。ファーストタッチチャネルは、訪問者が訪問者関与期間（デフォルトでは 30 日）を超えてサイトを訪問しない限り維持されます。

このディメンションを特定の値に設定する場合は、次の手順を実行する必要があります。

* 「レポートスイートの設定」の下のマーケティングチャネルマネージャーで、目的のディメンション項目をチャネルとして設定します。
* ヒットに必要な条件を含むマーケティングチャネルの処理ルールを設定します。
* サイトに対する訪問者のヒットは、マーケティングチャネルの処理ルールで説明されている条件に一致する必要があります。 _そして_、訪問者のエンゲージメント期間内に最初に一致するマーケティングチャネルの値である必要があります。

後続のヒットが、別のマーケティングチャネルの条件と一致する場合、このディメンションは新しいマーケティングチャネルで上書きされません。

## ディメンション項目

ディメンション項目には、マーケティングチャネルマネージャー内の任意のチャネル名が含まれます。デフォルトでは、`"Paid search"`、`"Natural search"`、`"Display"`、 `"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"`、`"Referring domains"`の値が含まれます。マーケティングチャネルマネージャーでチャネルを追加または削除できます。これは、このディメンションの値に影響を与えます。
