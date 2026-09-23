---
title: ドメイン
description: 訪問者がインターネットにアクセスするために使用する組織または ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 31%
---
# ドメイン

「ドメイン」ディメンション [1}は、訪問者がインターネットへのアクセスに使用するアクセス ポイントを報告します。](overview.md)

>[!NOTE]
>
>Data Warehouseには、同様の情報を報告する廃止された&#39;[!UICONTROL Domains]&#39; （複数形）ディメンションが含まれています。 Adobeでは、このディメンション &#39;[!UICONTROL Domain]&#39; （単数）を使用して一貫性を保つことをお勧めします。

## このディメンションへのデータ入力

Adobeでは、このディメンションを訪問者のIP アドレスからサーバーサイドで取得し、逆引きDNS ルックアップを含むいくつかの方法を使用してアクセスポイントドメインを決定します。 Adobeは[Digital Element](https://www.digitalelement.com/)と連携して、このルックアップを管理します。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（訪問者のIP アドレスから取得） |
| **Web SDK / XDM フィールド** | なし（訪問者のIP アドレスから取得） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[ データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Network Lookup]を有効にします。

## ディメンション項目

ディメンション項目の例としては、`comcast.net`、`rr.com`、`sbcglobal.net`、`amazonaws.com` などがあります。 これらのドメインはアクセスポイントであり、ISPまたは組織を表すドメインである必要はありません。

ディメンション値が `None` の場合は、アクセスポイントの IP アドレスの所有者がドメインを提供しなかったことを意味します。
