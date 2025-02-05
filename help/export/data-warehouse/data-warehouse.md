---
description: Data Warehouseと、カスタムレポートを作成して実行できるデータのフィルタリング方法について説明します。
title: Data Warehouseの概要
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 79%

---

# Data Warehouse の概要

データウェアハウスでは、Adobe Analytics データをコピーして保存したり、データをフィルタリングして実行できるカスタムレポートを作成したりできます。

## レポートの概要

データウェアハウスレポートでは、独自の質問に基づいて、生データからの詳細なデータ関係を表示できます。1 つのリクエストに含めることができる行数に制限はありません（個別レポート、スケジュール済みレポート、ダウンロード済みレポートの場合)。

>[!NOTE]
>
>Data Warehouse では、レポート期間中に最初に発生した値がレポートされます。

>[!IMPORTANT]
>
>分類された値でセグメント化する場合、Analysis Workspace と Data Warehouse では、「未指定」の値の処理方法が異なります。Workspace では、「未指定」は分類されていない値を表し、Data Warehouse では「未指定」はユーザーが「未指定」に分類した値を表します。

## 配信の概要

データウェアハウスレポートはメールで送信されるか、クラウドストレージプロバイダーに送信されます。処理には最大 72 時間かかる場合があります。処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。

Data Warehouse は、1 MB を超えるファイルを自動的に zip ファイルに圧縮します。電子メールの添付ファイルサイズは最大 10 MB です。

## アクセス

アドビでは、特定のレポートスイートの管理者レベルのユーザーに対してのみ Data Warehouse を有効にします。（グローバルレポートスイートおよび子レポートスイートで有効にできますが、ロールアップレポートスイートでは無効になります）。 管理者は、Data Warehouseへのアクセス権を持つグループを作成し、管理者以外のレベルのユーザーをそのグループに関連付けることができます。

詳しくは、[データウェアハウス権限の管理](/help/export/data-warehouse/t-dw-group.md)を参照してください。

## データウェアハウスリクエストの作成

データウェアハウスリクエストの作成方法について詳しくは、[データウェアハウスリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

## データウェアハウスリクエストの管理

データウェアハウスリクエストの管理方法について詳しくは、[データウェアハウスリクエストの管理](/help/export/data-warehouse/data-warehouse-requests-manage.md)を参照してください。

