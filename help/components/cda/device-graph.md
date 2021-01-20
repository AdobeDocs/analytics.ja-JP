---
title: デバイスグラフ
description: デバイスグラフを使用してデータをステッチする際の前提条件と制限事項を理解します。
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 97%

---


# デバイスグラフ

デバイス間分析には、データを結合する2つの異なる方法があります。 この方法では、Adobe Experience Platform ID サービス Co-op グラフまたはプライベートグラフを使用してデータを結合します。CDA は、デバイスグラフと定期的に通信し、デバイスを相互にリンクします。

## Co-op グラフとプライベートグラフの違い

アドビは、ID サービスの一部として 2 種類のデバイスグラフを提供します。

* **Co-op グラフ**：任意の顧客が貢献し、参照できるハッシュ化されたデバイス ID のリポジトリ。このタイプのデバイスグラフは共同作業なので、通常、プライベートグラフより多くのデバイスに一致します。
* **プライベートグラフ**：組織だけが参照する、ハッシュ化されたデバイス ID のリポジトリ。

## デバイスグラフに固有の前提条件

デバイスグラフ方式を使用してクロスデバイス分析を実装する場合は、次の手順が必要です。組織内のチームやアドビのアカウントマネージャーと協力して、以下のすべての条件を満たすようにします。

>[!IMPORTANT]
>
>すべての前提条件を満たしていない場合、クロスデバイス分析を有効にできないか、データを結び付ける際に結果の質が低下する可能性があります。

* 「[概要](overview.md)」ページに表示されるすべての前提条件。
* 組織で、Adobe Experience Platform ID サービス Co-op グラフまたはプライベートグラフを使用する必要があります。Device Co-op ユーザーガイドの「[ホームページ](https://docs.adobe.com/content/help/ja-JP/device-co-op/using/home.html)」を参照してください。
* 実装では、Experience Cloud ID サービスの最新バージョンを使用する必要があります。Experience Cloud ID サービスユーザーガイドの「[ホームページ](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)」を参照してください。Adobe Experience Platform Launch を使用するほとんどの実装では、既に ECID がデプロイされている可能性があります。
* 実装ユーザーがログインしたときや電子メールを開いたときなど、個人を識別できるタイミングでは、実装は常にこの `setCustomerIDs` 関数（または相当する SDK）を呼び出します。この要件は、すべてのプラットフォーム（使用する場合はモバイルアプリを含む）に適用されます。Experience Cloud ID サービスユーザーガイドの [`setCustomerIDs`](https://docs.adobe.com/content/help/ja-JP/id-service/using/id-service-api/methods/setcustomerids.html) を参照してください。

## デバイスグラフに固有の制限

* 従来の Analytics ID はサポートされていません。Experience Cloud ID を持つ訪問者のみを関連付けます。
* 組織がプライベートグラフを使用している場合、新しいデバイスを結び付けるのに最大 24 時間かかります。
* Co-op グラフを使用している場合、サイトを訪問する新しいデバイスが関連付けられるまでに最大 2 週間かかる場合があります。CDA での直近の 2 週間の結び付けのレベルは、通常、2 週間よりも古い日付範囲の結び付けのレベルよりも低くなります。
* サードパーティのデバイスグラフはサポートされていません。

## 次の手順

組織がすべての要件を満たし、制限事項を理解したら、[クロスデバイス分析の設定](setup.md)を開始できます。

