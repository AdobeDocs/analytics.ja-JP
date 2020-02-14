---
title: マーケティングチャネル — はじめに
description: マーケティングチャネルのワークフロー、自動セットアップ、および複数のレポートスイートにテンプレートレポートスイート設定を適用する方法について説明します。
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# マーケティングチャネル — はじめに

マーケティングチャネルは、サイトに訪問者がどのように到達するかを把握するために一般に使われます。追跡するチャネルと追跡する方法に応じて、マーケティングチャネルの処理ルールをカスタマイズできます。

マーケティングチャネルの中心となるのがファーストタッチとラストタッチ指標です。これらの指標は、標準のコンバージョン指標を構成するものです。

## マーケティングチャネルのワークフロー

![](assets/step1_icon.png) ビジネス要件に基づき各チャネルを定義する。

使用するチャネルを定義することは、マーケティングチャネルの重要な手順の 1 つです。チャネルの定義には、組織内の複数のユーザー間での共同作業が必要です。考慮すべきいくつかの質問を以下に示します。

* 有料検索を使用しているか。
* 電子メールキャンペーンを使用しているか。複数の電子メールキャンペーンを使用しており、これらを個別に追跡するか。
* トラフィックをサイトに導くアフィリエイトがあるか。個別に追跡したいアフィリエイトがあるか。
* 個別に追跡すると効果的な外部のキャンペーンがあるか。
* すべてのソーシャルネットワーキングサイトの集計を行うか。または、個別に追跡したいソーシャルネットワーキングサイトがあるか。
* コンバージョンに影響を与えている可能性があり、追跡したい他のチャネルがあるか。

チャネルの推奨事項のリストについては、[よくある質問と例](/help/components/c-marketing-channels/c-faq.md)を参照してください。使用するチャネルのリストを作成し、チャネルの作成時にチャネルの有効化と定義を簡単に行えるようにします。

![](assets/step2_icon.png) ページにマーケティングチャネルを追 [!UICONTROL Marketing Channel Manager] 加します。

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

前提条件と概念情報については、[チャネルとルール](/help/components/c-marketing-channels/c-channels.md)を参照してください。

手順については、「[マーケティングチャネルの追加](/help/components/c-marketing-channels/c-channels.md)」を参照してください。

>[!NOTE]
>
>マーケティングチャネルが事前に設定されていない場合は、[自動セットアップ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)が表示されます。このセットアップではいくつかの事前定義のチャネルが提供され、これらのチャネルをカスタマイズできます。アドビでは、これらのルールをテンプレートとして使用することをお勧めします。ただし、既に確立されたチャネル定義がある場合は、自動セットアップをスキップすることができます。

![](assets/step3_icon.png) ページ上で各チャネルのルールを設定または調整 [!UICONTROL Marketing Channel Processing Rules] します。

After you create channels on the [!UICONTROL Marketing Channel Manager] page, you configure the rules so that channels can retrieve and report data.

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

チャネルが自動セットアップで作成された場合は、これらのチャネルのルールが定義されています。ニーズに合わせてこれらのルールを変更します。

## マーケティングチャネルの自動セットアップ {#run-auto-setup}

マーケティングチャネルレポートには、すぐに使い始められるように 1 回限りのセットアップページが用意されています。このレポートは、トラッキングに使用できる複数のマーケティングチャネルを提供します。チャネルとルールを問題なくご自分で作成できる場合には、このセットアップをスキップしてかまいません。ただし、アドビでは、ウィザードを使用してチャネルを作成することを推奨します。自動セットアップを使用すると、ルールの構成方法を確認できます。また、個々の目的に合わせてルールを編集することもできます。事前定義のチャネルは、いつでも無効にしたり削除したりできます。

マーケティングチャネルの自動セットアップの実行方法です。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager], select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![手順の結果](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. 詳しくは、[マーケティングチャネルマネージャ－](/help/components/c-marketing-channels/c-channels.md)を参照してください。このページは、レポートスイートに既にマーケティングチャネルが含まれている場合には表示されません。マーケティングチャネルのない別のレポートスイートを選択しない限り、再度このページにアクセスすることはできません。

1. 作成するチャネルが選択されていることを確認します。

   選択すると、、、 **[!UICONTROL Email]**&#x200B;および **[!UICONTROL Display]**&#x200B;が必須 **[!UICONTROL Affiliate]** フィールドになります。

1. クリック **[!UICONTROL Save]**.

## 複数のレポートスイートへのテンプレートレポートスイート設定の適用

マーケティングチャネル設定をテストするテンプレートとして、マスターレポートスイートを使用する方法です。時間を節約するために、1 つのレポートスイートにおける設定を 1 つ以上のレポートスイートに適用することが可能です。この作業は、チャネルとルールセットに対して別々に実行します。

> [!NOTE]ルールセットを適用する前に、テンプレートからチャネルを適用してください。この手順を実行する際、チャネルは全レポートスイート間で同一である必要があります。

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

