---
description: ここでは、Report Builder を Power BI と共に使用しているときによく発生する問題をいくつか紹介します。
seo-description: ここでは、Report Builder を Power BI と共に使用しているときによく発生する問題をいくつか紹介します。
seo-title: Power BI統合のトラブルシューティング
title: Power BI統合のトラブルシューティング
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Power BI統合のトラブルシューティング

ここでは、Report Builder を Power BI と共に使用しているときによく発生する問題をいくつか紹介します。

## 手順 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

スケジュールされたワークブックの Power BI 発行が成功するには、Power BI サービスが起動して動作している必要があります。発行の失敗には主に次の 2 つの理由があります。

* Power BI サービスがダウンしている。
* ワークブックをスケジュールしたユーザーの Microsoft アカウント資格情報が無効になっている。

Report Builder でスケジュールされた各タスクは、スケジュールされた実行ごとに 3 回試行されます。

* 最初の試行が失敗に終わると、「スケジュールされたこのワークブックを Microsoft Power BI に発行できませんでした。すぐにもう一度実行します」というメッセージが表示されます。
* 2 回目の試行が失敗に終わると、メッセージは表示されません。
* 3 回目の試行が失敗に終わると、「このワークブックを Power BI に発行できませんでした」というメッセージが表示されます。

## 手順 2：Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Report Builder リクエストを Power BI に発行した後にビジュアライゼーションが壊れる主な理由を以下に示します。

* Report Builder でリクエストを編集した（例えば、指標またはディメンションを変更して Power BI に再発行した）。リクエストを編集すると、ビジュアライゼーションが壊れる可能性があります。
* ビジュアライゼーションで使用されているリクエストを削除した。

