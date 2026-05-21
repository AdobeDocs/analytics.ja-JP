---
description: データウェアハウスと、カスタムレポートを作成して実行できるデータのフィルタリング方法について説明します。
title: データウェアハウスの概要
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
TQID: https://experienceleague.adobe.com/Vkn9mWvBzaiIBf1KYIEUK8cRwTuzw41MT-v-thMBg38
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 285
ht-degree: 86%

---

# データウェアハウスの概要

データウェアハウスでは、Adobe Analytics データをコピーして保存したり、データをフィルタリングして実行できるカスタムレポートを作成したりできます。

## レポートの概要

データウェアハウスレポートでは、独自の質問に基づいて、生データからの詳細なデータ関係を表示できます。 1 つのリクエストに含めることができる行数に制限はありません（個別レポート、スケジュール済みレポート、ダウンロード済みレポートの場合)。

>[!NOTE]
>
>Data Warehouse では、レポート期間中に最初に発生した値がレポートされます。

>[!IMPORTANT]
>
>分類された値でセグメント化する場合、Analysis Workspace と Data Warehouse では、「未指定」の値の処理方法が異なります。 Workspace では、「未指定」は分類されていない値を表し、Data Warehouse では「未指定」はユーザーが「未指定」に分類した値を表します。

## 配信の概要

データウェアハウスレポートはメールで送信されるか、クラウドストレージプロバイダーに送信されます。処理には最大 72 時間かかる場合があります。 処理に要する時間は、クエリの複雑さとリクエストされたデータの量に応じて異なります。

Data Warehouse は、サイズが 1 MB を超えるファイルを自動的に ZIP 圧縮します。 メールの添付ファイルの最大サイズは 10 MB です。

## アクセス

アドビでは、特定のレポートスイートの管理者レベルのユーザーに対してのみデータウェアハウスを有効にします。 （グローバルレポートスイートと子レポートスイートでは有効にできますが、ロールアップレポートスイートでは有効にできません）。 管理者は、Data Warehouseへのアクセス権を持つグループを作成し、管理者以外のレベルのユーザーをそのグループに関連付けることができます。

詳しくは、[データウェアハウス権限の管理](/help/export/data-warehouse/t-dw-group.md)を参照してください。

## データウェアハウスリクエストの作成

データウェアハウスリクエストの作成方法について詳しくは、[データウェアハウスリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

## データウェアハウスリクエストの管理

データウェアハウスリクエストの管理方法について詳しくは、[データウェアハウスリクエストの管理](/help/export/data-warehouse/data-warehouse-requests-manage.md)を参照してください。

