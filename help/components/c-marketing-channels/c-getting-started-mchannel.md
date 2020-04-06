---
title: マーケティングチャネル
description: マーケティングチャネルのワークフロー、自動セットアップ、および複数のレポートスイートにテンプレートレポートスイートの設定を適用する方法について説明します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# マーケティングチャネル

マーケティングチャネルは、一般に、サイトに訪問者が到達する方法に関するインサイトを提供するために使用されます。 追跡するチャネルと追跡する方法に基づいて、マーケティングチャネルの処理ルールをカスタマイズできます。

マーケティングチャネルの中心となるのがファーストタッチとラストタッチ指標です。これらの指標は、標準のコンバージョン指標を構成するものです。

## マーケティングチャネルのワークフロー

![](assets/step1_icon.png) ビジネス要件に基づき各チャネルを定義する。

使用するチャネルの定義は、マーケティングチャネルの最も重要な要素の1つです。 チャネルを定義するには、組織内の複数の個人間でのコラボレーションが必要になる場合があります。 以下に、考慮すべき質問を示します。

* 有料検索を使用していますか。
* 電子メールキャンペーンを使用 別々に追跡する複数の電子メールキャンペーンを使用しているか。
* トラフィックをサイトに導くアフィリエイトがあるか。 個別に追跡するアフィリエイトがあるか。
* 別々に追跡する上で有利な外部キャンペーンはありますか。
* すべてのソーシャル集計サイトを追跡しますか。それとも、個別に追跡するソーシャルネットワーキングサイトはありますか。
* コンバージョンに影響を与える可能性のあるチャネルを追跡する他に何かありますか。

推奨チャネルのリストは、よくある質問と例 [を参照してください](/help/components/c-marketing-channels/c-faq.md)。 使用するチャネルのリストを作成し、チャネルの作成時にチャネルの有効化と定義を簡単に行えるようにします。

![](assets/step2_icon.png) マーケティ追加ングチャネルを参照して [!UICONTROL Marketing Channel Manager] ください。

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

前提条件と概念情報については、[チャネルとルール](/help/components/c-marketing-channels/c-channels.md)を参照してください。

手順については、「[マーケティングチャネルの追加](/help/components/c-marketing-channels/c-channels.md)」を参照してください。

>[!NOTE]
>
>マーケティングチャネルが事前に設定されていない場合は、[自動セットアップ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)が表示されます。このセットアップでは、カスタマイズ可能な事前設定済みチャネルがいくつか提供されています。 アドビでは、これらのルールをテンプレートとして使用することをお勧めします。 ただし、既に実線のチャネル定義がある場合は、自動セットアップをスキップできます。

![](assets/step3_icon.png) ページ上の各チャネルのルールを設定または調整 [!UICONTROL Marketing Channel Processing Rules] します。

ページでチャネルを作成し [!UICONTROL Marketing Channel Manager] たら、チャネルがデータを取得してレポートできるようにルールを設定します。

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

チャネルが自動設定で作成された場合、これらのチャネルのルールが定義されます。 必要に応じて変更できます。

## マーケティングチャネルの自動設定 {#run-auto-setup}

マーケティングチャネルレポートには、すぐに使い始められるように 1 回限りのセットアップページが用意されています。追跡に使用できる複数のマーケティングチャネルを提供します。 この設定は、ルールやルールの作成に慣れている場合はチャネルをスキップできます。 ただし、ウィザードでウィザードを使用してウィザードを作成することをお勧めするチャネルがあります。 自動セットアップを使用すると、ルールの構築方法を確認したり、目的に合わせてルールを編集したりできます。 定義済みのチャネルは、いつでも無効にできます。

マーケティングチャネルの自動セットアップの実行方法です。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager], select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![手順の結果](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. 詳しくは、[マーケティングチャネルマネージャ－](/help/components/c-marketing-channels/c-channels.md)を参照してください。レポートスイートに1つ以上のマーケティングチャネルが含まれる場合、このページは表示されません。 マーケティングオプションを含まない別のレポートスイートを選択しない限り、このページに再度アクセスすることはできません。チャネル

1. 作成するチャネルが選択されていることを確認します。

   選択した場合、、、 **[!UICONTROL Email]**&#x200B;および **[!UICONTROL Display]**&#x200B;は必須フ **[!UICONTROL Affiliate]** ィールドです。

1. クリック **[!UICONTROL Save]**.

## 複数のレポートスイートへのテンプレートレポートスイート設定の適用

マーケティングテンプレート設定をテストするテンプレートとしてマスターレポートスイートをチャネルする方法。 時間を節約するために、このテンプレートを一括更新で1つ以上の実稼働レポートスイートに適用できます。 このタスクは、個別にチャネルとルールセットに対して実行します。

>[!NOTE]ルールセットを適用する前に、テンプレートからチャネルを適用してください。この手順を実行する際、チャネルは全レポートスイート間で同一である必要があります。

1. 選択したレポートスイートでマーケティングチャネルレポートが有効になっていることを確認します。この手順はアカウントマネージャーがおこないます。
1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. **[!UICONTROL Report Suite Manager]** ページで、テンプレートレポートスイートと、1 つ以上の対象レポートスイートを選択します。
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. On the **[!UICONTROL Select Master Report Suites]** page, select a template report suite.
1. クリック **[!UICONTROL Save All]**.
1. テンプレートから複数のレポートスイートにルールを適用します。
   1. Return to the [!UICONTROL Report Suite Manager] page.
   1. テンプレートレポートスイートと、1 つ以上の対象レポートスイートを選択します。
   1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. クリック **[!UICONTROL Save]**. この手順で「保存」ボタンが無効になっている場合は、いずれかのルールを展開して有効にします。

