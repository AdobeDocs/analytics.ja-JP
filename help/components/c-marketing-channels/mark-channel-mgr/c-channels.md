---
description: マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。
subtopic: Marketing channels
title: マーケティングチャネルの管理
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dd58453a0459bc200a00badf34d06c259ce9fb59

---


# マーケティングチャネルの管理

マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。

チャネル作成時のガイドラインは次のとおりです。

* すべての訪問者が適切なチャネルに分類されるように、すべてのチャネルの一覧を作成し、事前に計画を立ててください。
* 常に[内部](/help/components/c-marketing-channels/mc-faq/c-faq.md)ヒットのカテゴリ用のチャネルと、[直接](/help/components/c-marketing-channels/mc-faq/c-faq.md)ヒットのカテゴリ用のチャネルを含めてください。

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) page. ルールを作成するときに、そのルールをチャネルに関連付けます。

## マーケティングチャネルの追加 {#add-mktg-channels}

マーケティングチャネルマネージャーでマーケティングチャネルを追加します。

> [!NOTE]チャネルは削除できません。使用しないチャネルは、無効にするか名前を変更し、後で使用するためにとっておきます。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   複数のレポートスイートを選択した場合、テンプレートから選択したレポートスイートに設定をコピーするために、テンプレートを選択する必要があります。

   詳しくは、[複数のレポートスイートへのテンプレートレポートスイート設定の適用](/help/components/c-marketing-channels/getting-started/t-template.md)。

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   レポートスイートでチャネルが定義されていない場合、[自動セットアップ](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)ページが表示されます。

1. ページ上で、 [!UICONTROL Marketing Channel Manager] をクリックしま **[!UICONTROL Add Channel]**&#x200B;す。

   このオプションは、チャネルが 25 個定義されている場合は利用できません。

1. ズーム後に **[!UICONTROL Save.]**
1. チャネルのルールを設定するには、をクリックしま **[!UICONTROL Marketing Channel Processing Rules]**&#x200B;す。

   [マーケティングチャネルの処理ルールの作成](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md)を参照してください。

## マーケティングチャネルマネージャー - インターフェイスの定義 {#mktg-channel-mgr}

ページのフィールドの [!UICONTROL Marketing Channel Manager] 定義。

| フィールド | 定義 |
|--- |--- |
| 有効 |  このマーケティングチャネルの有効と無効を切り替えます。 |
| チャネル名 | マーケティングチャネルの分かりやすい名前をつけます。 |
| ラストタッチチャネルの上書き | ラストタッチチャネルを上書きするかどうかをチャネルごとに指定できます。このチェックボックスを選択すると、すべてのチャネル（「直接」と「内部」を含む）が既存のラストタッチチャネルを上書きします。設定を変更すると、誤ったチャネル（「直接」や「内部」）にコンバージョンが関連付けられるリスクがあるので、注意が必要です。たとえば、「自然検索」チャネルを通してユーザーが以前に獲得されている場合、「直接アクセス」での訪問が発生しても、「自然検索」のチャネルがコンバージョンのクレジットを引き続き受け取るようにしたい場合は、「直接アクセス」チャネルの「ラストタッチチャネルの上書き」オプションを外しておきます（デフォルト設定のまま変更しない）。 |
| チャネルの分類 |  この値によって、チャネルを分類できます。You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md). |
| タイプ | サイトへのユーザーの訪問手段を指定します。「オンライン」または「オフライン」を選択できます。検索エンジンまたは電子メールキャンペーンから来訪した訪問者に対しては「オンライン」チャネルを使用します。「オフライン」チャネルは、新聞のクーポンや雑誌の広告でサイトの情報を見つけた訪問者に使用します。オフラインチャネルには通常、データソースからインポートされたデータが含まれます。[データソース](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html)を参照してください。[オフラインデータの追加](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)を参照してください。 |
| 色 |  このマーケティングチャネルに関連付けられている色。この色は、マーケティングチャネルレポートで、このチャネルを表します。 |