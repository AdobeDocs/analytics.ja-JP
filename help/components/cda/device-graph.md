---
title: デバイスグラフ
description: デバイスグラフを使用してデータをステッチする際の前提条件と制限事項を理解します。
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 62%

---

# デバイスグラフ

クロスデバイス分析では、プライベートグラフを使用してデータを結び付けることができます。 プライベートグラフは、組織に固有の、ハッシュ化されたデバイス ID のリポジトリです。 CDA は、デバイスグラフと定期的に通信し、デバイスを相互にリンクします。

## デバイスグラフに固有の前提条件

デバイスグラフ方式を使用してクロスデバイス分析を実装する場合は、次の手順が必要です。組織内のチームやAdobeアカウントチームと協力して、以下のすべての条件を満たすようにします。

>[!WARNING]
>
>すべての前提条件を満たしていない場合、クロスデバイス分析を有効にできないか、データを結び付ける際に結果の質が低下する可能性があります。

* 「[概要](overview.md)」ページに表示されるすべての前提条件。
* 組織では、 [Adobe Experience Platform Identity Service プライベートグラフ](https://business.adobe.com/products/experience-platform/identity-service.html). 関連トピック [ホームページ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja) 」を参照してください。
* 実装では、最新バージョンのExperience CloudID サービス (ECID) を使用する必要があります。 詳しくは、 [ホームページ](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) （ ID サービスユーザーガイド）を参照してください。 ほとんどの実装では、 [タグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja) Adobe Experience Platformでは、既に ID サービスがデプロイされている可能性があります。
* 実装ユーザーがログインしたときや電子メールを開いたときなど、個人を識別できるタイミングでは、実装は常にこの `setCustomerIDs` 関数（または相当する SDK）を呼び出します。この要件は、すべてのプラットフォーム（使用する場合はモバイルアプリを含む）に適用されます。詳しくは、 [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=ja) （ ID サービスユーザーガイド）を参照してください。

## デバイスグラフに固有の制限

* 従来の Analytics ID はサポートされていません。Experience Cloud ID を持つ訪問者のみを関連付けます。
* 組織がプライベートグラフを使用している場合、新しいデバイスを結び付けるのに最大 24 時間かかります。
* サードパーティのデバイスグラフはサポートされていません。

## 次の手順

組織がすべての要件を満たし、制限事項を理解したら、[クロスデバイス分析の設定](setup.md)を開始できます。
