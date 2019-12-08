---
description: 訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するためのマーケティングチャネルの処理ルールを作成します。
subtopic: Marketing channels
title: マーケティングチャネルの処理ルールの作成
topic: Reports and analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# マーケティングチャネルの処理ルールの作成

訪問者のヒットがチャネルに割り当てられた条件を満たすかどうかを判断するためのマーケティングチャネルの処理ルールを作成します。

この手順では、例として電子メールルールを使用します。この例では、マーケティングチャネルマネージャーページのチャネルのリストに電子メールチャネルを追加済みであることを前提としています。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. レポートスイートを選択します。

   レポートスイートでチャネルが定義されていない場合、[!UICONTROL マーケティングチャネル ：自動セットアップ]ページが表示されます。

   詳しくは、[自動セットアップの実行](/help/components/c-marketing-channels/c-channel-autosetup.md)を参照してください。

1. **[!UICONTROL 設定を編集]**／**[!UICONTROL マーケティングチャネル]**／**[!UICONTROL マーケティングチャネルの処理ルール]**&#x200B;の順にクリックします。

   ![手順の結果](assets/marketing_channel_rules.png)

1. 「**[!UICONTROL 新しいルールセットの追加]**」メニューから「**[!UICONTROL 電子メール]**」を選択します。

   これにより、チャネルを選択するのではなく、必要なパラメーターを持つルールを挿入するテンプレートを選択することになります。

   ![手順の結果](assets/example_email.png)

   ブール値論理（if／then 文）を使用してルールを設定します。例えば、電子メールチャネルルールでは次のルール文で強調した設定または情報を提供します。

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   この例では、*`<value>`* が電子メールキャンペーンに使用するクエリ文字列パラメーターです（例えば、*`eml`* など）。
1. ルールの作成を続けるには、「**[!UICONTROL ルールの追加]**」をクリックします。
1. ルールに優先順位を付けるには、目的の位置にルールをドラッグアンドドロップします。
1. 「**[!UICONTROL 保存]**」をクリックします。

>[!MORELIKETHIS]
>
>* [よくある質問と例](/help/components/c-marketing-channels/c-faq.md)

