---
description: Data Warehouse は、データをフィルタリングして、保存用およびカスタムレポート用の Analytics データのコピーを参照できます。ユーザー独自の質問に基づいて、生データから詳細なデータの関連性を表示するようレポートにリクエストできます。Data Warehouse レポートは、電子メールで送信したり、クラウドストレージプロバイダーに送信したりできます。処理には最大 72 時間かかる場合があります。 処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。
title: Data Warehouse の概要
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 58%

---

# Data Warehouse の概要

Data Warehouseを使用すると、Adobe Analyticsデータをコピーして保存したり、カスタムレポートを作成したりできます。これは、データをフィルタリングすることで実行できます。

## レポートの概要

Data Warehouseレポートでは、ユニークな質問に基づいて生のデータから詳細なデータの関係を表示できます。 1 つのリクエストに含める行数に制限はありません（個々のレポート、予定レポート、ダウンロードされたレポート）。

>[!NOTE]
>
>Data Warehouse では、レポート期間中に最初に発生した値がレポートされます。

>[!IMPORTANT]
>
>分類された値でセグメント化する場合、Analysis Workspace と Data Warehouse では、「未指定」の値の処理方法が異なります。Workspace では、「未指定」は分類されていない値を表し、Data Warehouse では「未指定」はユーザーが「未指定」に分類した値を表します。

## 配信の概要

Data Warehouseレポートは、電子メールで送信したり、クラウドストレージプロバイダーに送信したりできます。処理には最大 72 時間かかる場合があります。 処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。

Data Warehouse は、1 MB を超えるファイルを自動的に zip ファイルに圧縮します。電子メールの添付ファイルサイズは最大 10 MB です。

## アクセス

アドビでは、特定のレポートスイートの管理者レベルのユーザーに対してのみ Data Warehouse を有効にします。（Data Warehouse は、グローバルレポートスイートおよび子レポートスイートに対して有効にすることができます。ただし、ロールアップレポートスイートに対しては有効にすることができません）。管理者は Data Warehouse にアクセスできるグループを作成し、非管理者レベルのユーザーをそのグループに関連付けることができます。

詳しくは、 [Data Warehouse権限の管理](/help/export/data-warehouse/t-dw-group.md).

## Data Warehouse リクエストの作成

リクエストの作成方法について詳しくは、「Data Warehouseリクエストの作成方法」を参照してください。 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Data Warehouse リクエストの管理

Data Warehouseリクエストの管理方法について詳しくは、 [Data Warehouseリクエストの管理](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## FAQ

よくある質問のリストについては、 [Data Warehouseの FAQ](/help/export/data-warehouse/faq.md).