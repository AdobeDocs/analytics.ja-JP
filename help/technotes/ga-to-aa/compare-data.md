---
title: Adobe Analytics データのサードパーティ製品との比較
description: Adobe Analytics のデータを他の Analytics ソリューションで収集されたデータと直接比較する場合のオプションを理解します。
feature: Third-party Integration
exl-id: b4f85088-7ffd-45dc-bdd1-c0fc8dc3b332
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: ht
source-wordcount: '250'
ht-degree: 100%

---

# Adobe Analytics データのサードパーティ製品との比較

オンラインでは多くの分析ソリューションを利用できます。これらの各ソリューションは、独自のメソッドを使用してコードを実装し、データを収集します。各製品で使用されるページ表示、訪問、ユニーク訪問者、その他の指標は、それぞれ独自に定義されます。

これらの定義、データ構造、実装は大幅に異なるため、 **Adobe カスタマーケアは、サードパーティの分析ツールとの不一致のトラブルシューティングをおこないません。**

Adobe Analytics とサードパーティの分析ツールの間に大きな相違がある場合は、以下のリソースを利用できます。

* **デバッガを使用した自己監査**：サイト上のページは、[Adobe のデバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)または他のパケット監視で確認できます。デバッガーを使用すると、実装を検証し、イメージリクエストが適切な変数で正しく実行されていることを確認できます。
* **データフィードを使用した自己監査**：Adobe は、1 日のすべての生データを含む[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)を受信するオプションを組織に提供します。その後、組織でこのデータを使用して、サードパーティの分析ツールと比較し、不一致があるかどうかを判断できます。
* **Adobe コンサルティングによる監査とデータの検証の支援**：正式な Adobe 担当者にサイトで完全な実装監査を実行するように依頼する場合は、組織のアカウントマネージャーにお問い合わせください。アカウントマネージャーは実装コンサルタントとのミーティングを設定し、実装コンサルタントが会社の契約に基づいてサイトを監査できます。
