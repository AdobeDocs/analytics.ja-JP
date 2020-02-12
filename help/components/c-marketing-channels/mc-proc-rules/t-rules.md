---
title: マーケティングチャネルの処理ルールの作成
description: 訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するためのマーケティングチャネルの処理ルールを作成します。
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# マーケティングチャネルの処理ルールの作成

訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するためのマーケティングチャネルの処理ルールを作成します。

この手順では、例として電子メールルールを使用します。この例では、マーケティングチャネルマネージャーページのチャネルのリストに電子メールチャネルを追加済みであることを前提としています。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. レポートスイートを選択します。

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![手順の結果](assets/marketing_channel_rules.png)

1. メニューか **[!UICONTROL Add New Rule Set]** らを選択しま **[!UICONTROL Email]**&#x200B;す。

   これにより、チャネルを選択するのではなく、必要なパラメーターを持つルールを挿入するテンプレートを選択することになります。

   ![手順の結果](assets/example_email.png)

   ブール値論理（if／then 文）を使用してルールを設定します。例えば、電子メールチャネルルールでは次のルール文で強調した設定または情報を提供します。

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   この例では、*`<value>`* が電子メールキャンペーンに使用するクエリ文字列パラメーターです（例えば、*`eml`* など）。
1. ルールの作成を続行するには、をクリックしま **[!UICONTROL Add Rule]**&#x200B;す。
1. ルールに優先順位を付けるには、目的の位置にルールをドラッグアンドドロップします。
1. ズーム後に **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [よくある質問と例](/help/components/c-marketing-channels/mc-faq/c-faq.md)

