---
title: デバイスグラフ
description: デバイスグラフを使用してデータをステッチする際の前提条件と制限事項を理解します。
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# デバイスグラフ

デバイス間の分析には、データを結合する2つの異なる方法があります。 この方法では、Adobe Experience Platform・アイデンティティ・サービス協力グラフまたはプライベート・グラフを使用してデータを結合します。 CDAは、デバイスグラフと定期的に通信し、デバイスを相互にリンクします。

## 協力グラフとプライベートグラフの違い

Adobeオファーは、IDサービスの一部として2種類のデバイスグラフを作成します。

* **協力グラフ**: 任意の顧客が貢献し、参照できるハッシュ化されたデバイスIDのリポジトリ。 このタイプのデバイスグラフは共同作業なので、通常、プライベートグラフより多くのデバイスに一致します。
* **プライベートグラフ**: 組織だけが参照する、ハッシュ化されたデバイスIDのリポジトリ。

## デバイスグラフに固有の前提条件

デバイスグラフ方式を使用してデバイス間分析を実装する場合は、次の手順が必要です。 組織内のチームやアドビのアカウントマネージャーと協力して、以下のすべての条件を満たすようにします。

>[!IMPORTANT]
>
>すべての前提条件を満たしていない場合、クロスデバイス分析を有効にできないか、データを結び付ける際に結果の質が低下する可能性があります。

* 「 [概要」ページに表示されるすべての前提条件](overview.md)。
* 組織で、Adobe Experience Platform ID サービス Co-op グラフまたはプライベートグラフを使用する必要があります。Device Co-op ユーザーガイドの「[ホームページ](https://docs.adobe.com/content/help/ja-JP/device-co-op/using/home.html)」を参照してください。
* 導入では、Experience CloudIDサービスの最新バージョンを使用する必要があります。 Experience Cloud ID サービスユーザーガイドの「[ホームページ](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)」を参照してください。Adobe Experience Platform Launch を使用するほとんどの実装では、既に ECID がデプロイされている可能性があります。
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. この要件は、すべてのプラットフォーム（使用する場合はモバイルアプリを含む）に適用されます。Experience Cloud ID サー ビスユーザーガイドの [`setCustomerIDs`](https://docs.adobe.com/content/help/ja-JP/id-service/using/id-service-api/methods/setcustomerids.html) を参照してください。

## デバイスグラフに固有の制限

* 従来の Analytics ID はサポートされていません。Experience Cloud ID を持つ訪問者のみを関連付けます。
* プライベートグラフを使用している場合、新しいデバイスをステッチするのに最大24時間かかります。
* Co-op Graphを使用している場合、サイトを訪問する新しいデバイスが関連付けられるまでに最大2週間かかる場合があります。 CDA での直近の 2 週間の結び付けのレベルは、通常、2 週間よりも古い日付範囲の結び付けのレベルよりも低くなります。
* サードパーティのデバイスグラフはサポートされていません。

## 次の手順

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

