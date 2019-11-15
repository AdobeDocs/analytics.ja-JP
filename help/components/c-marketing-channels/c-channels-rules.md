---
description: レポートにチャネルとチャネルデータを表示できるようにするには、チャネルおよびそのデータを処理するための基本的なルールを作成してください。また、関連チャネルのコストと予算の金額を作成し、訪問者のエンゲージメント期間の長さも指定することができます。管理ツールでレポートの設定を行います。
solution: Analytics
subtopic: Marketing channels
title: チャネルとルールについて
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# チャネルとルールについて

レポートにチャネルとチャネルデータを表示できるようにするには、チャネルおよびそのデータを処理するための基本的なルールを作成してください。また、関連チャネルのコストと予算の金額を作成し、訪問者のエンゲージメント期間の長さも指定することができます。管理ツールでレポートの設定を行います。

チャネルを訪問件数のコンテナとすると、訪問件数を適切なコンテナに割り当てるのがルールです。

![](assets/buckets_2.png)

アドビでは、複数の事前定義のチャネルを[自動セットアップ](/help/components/c-marketing-channels/c-channel-autosetup.md)を利用すると、事前定義された複数のチャネルが設定されます。このチャネルはニーズに合わせて編集できます。

>[!NOTE]
>
>アドビでは、テスト用にテンプレートとして使用できるレポートスイートにレポートを設定することをお勧めします。 それをひな形として、1 つまたはそれ以上の本番用レポートスイートにまとめてチャネルとルールセットを適用することができます。
>
>詳しくは、 [複数のレポートスイートへのテンプレートレポートスイート設定の適用](/help/components/c-marketing-channels/t-template.md).

また、次のトピックを確認してください。

* [前提条件](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [処理に関する重要な注意事項](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## 前提条件 {#prereqs}

必要な場合は、次の前提条件に関してカスタマーケアに問い合わせることができます。

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Set up user group access to the **[!UICONTROL Marketing Channel Report]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* システムは指定された順序でルールを処理し、ルールの 1 つが満たされると残りのルールの処理を中止します。
* ルールは VISTA が設定した変数にはアクセスできますが、VISTA が削除したデータにはアクセスできません。
* チャネルはコンバージョン指標のみを保存します。トラフィック指標は利用できません。
* 2 つのマーケティングチャネルが同じイベント（購入やクリックなど）からクレジットを受けることはありません。この点でマーケティングチャネルは eVar と異なります（同一イベントから 2 つの eVar がクレジットを受ける場合がある）。
* レポートは一度に 25 のチャネルまで処理できます。

