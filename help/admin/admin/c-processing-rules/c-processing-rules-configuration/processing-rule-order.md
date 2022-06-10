---
description: 処理ルールが存在する Analytics データパイプラインの場所。
subtopic: Processing rules
title: 処理順序
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 49%

---

# 処理順序

処理ルールを効果的に使用するには、データ収集時にルールが適用されるタイミングを理解する必要があります。

![処理順序](assets/analytics_processing_order.png)

次の表に、処理ルールの適用前と適用後に通常使用可能なデータを示します。

## 処理ルール前

| ディメンション | 説明 |
|--- |--- |
| [動的変数](/help/implement/vars/page-vars/dynamic-variables.md) | HTTP ヘッダーまたは他の変数から情報を取り出すことで、動的に設定される変数。 |
| [AppMeasurement](/help/implement/home.md) | AppMeasurement ライブラリで使用される関数とプラグインは、ブラウザーまたはクライアントアプリケーションで実行されます。 |
| [タグの実装](/help/implement/launch/overview.md) | Adobe Experience Platformデータ収集内のAdobe Analytics拡張機能で定義されたルール。 |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | Web SDK で収集されたデータは Adobe Experience Edge に送信され、目的のレポートスイートに転送されます。 |
| [ボットルール](/help/admin/admin/bot-removal/bot-rules.md) | 既知のスパイダーやボットによって生成されたトラフィックを削除できます。 |

## 処理ルール後

| ディメンション | 説明 |
|--- |--- |
| VISTA によって追加されるデータ | 処理ルールは VISTA の前に適用されます。 |
| 訪問ページ番号 | 処理ルールは、現在のヒットに含まれるデータのみを認識します。 訪問ページ番号は、処理ルールの適用後にコンパイルされます。 |
| ページ名が設定されていない場合は、クリーン URL をページ名として追加 | 処理ルールと VISTA の適用後、ページ名が設定されていない場合、クリーン URL がページ名として追加されます。このロジックは処理ルールの適用後に実行されるので、Adobeでは、ページ名が空白かどうかを確認する条件を追加することをお勧めします。  次を実行した場合、 **[!UICONTROL サイトコンテンツ]** > **[!UICONTROL ページ]** レポートを作成し、ページ名の URL 値が表示される場合、ページ名変数が空白になっている可能性があります。  空のページ名をテストする条件を設定したり、ページ名またはページ URL に特定の値が含まれているかどうかをテストしたりできます。 これにより、ページ名を必要に応じて設定できます。 |
| マーケティングチャネルの処理ルール | 処理ルールを使用して、[マーケティングチャネル処理ルール](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=ja)によって処理するデータを準備できます。 |
| GEO 参照 | 訪問者の州と訪問者の郵便番号の値が含まれます。 |
| eVar の持続性 | 以前のヒットに含まれていた eVar はルールの処理時の各ヒットまで持続されません。処理される現在のヒットに設定された eVar のみ使用できます。 |

## VISTA を使用してヒットをコピーするときに処理ルールを適用する方法

他のレポートスイートにヒットをコピーするように VISTA ルールが設定されている場合、ヒットは、他のレポートスイートに定義されている処理ルールを介して送信されます。

元のレポートスイートで処理ルールが定義されている場合、これらのルールは、Engineering Services による VISTA ルールの設定方法に基づいて適用される場合と適用されない場合があります。 確認するには、VISTA ルールで「pre」または「post」値を追加のレポートスイートにコピーしたかどうかを導入担当者に問い合わせてください。「pre」値をコピーした場合、元のレポートスイートに定義されている処理ルールは適用されません。「post」値をコピーした場合、処理ルールが適用された後にヒットがコピーされます。
