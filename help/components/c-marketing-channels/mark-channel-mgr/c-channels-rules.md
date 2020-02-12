---
title: チャネルの定義
description: レポートにチャネルとチャネルデータを表示できるようにするには、チャネルおよびそのデータを処理するための基本的なルールを作成してください。また、関連チャネルのコストと予算の金額を作成し、訪問者のエンゲージメント期間の長さも指定することができます。管理ツールでレポートの設定を行います。
translation-type: tm+mt
source-git-commit: e080c38e536f710490291aaca252cba36456b0f9

---


# チャネルの定義

レポートにチャネルとチャネルデータを表示できるようにするには、チャネルおよびそのデータを処理するための基本的なルールを作成してください。また、関連チャネルのコストと予算の金額を作成し、訪問者のエンゲージメント期間の長さも指定することができます。管理ツールでレポートの設定を行います。

チャネルを訪問件数のコンテナとすると、訪問件数を適切なコンテナに割り当てるのがルールです。

![](assets/buckets_2.png)

アドビでは、複数の事前定義のチャネルを[自動セットアップ](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)を利用すると、事前定義された複数のチャネルが設定されます。このチャネルはニーズに合わせて編集できます。

>[!NOTE]
>
>まずテスト用のレポートスイートにレポートを設定することを推奨します。それをひな形として、1 つまたはそれ以上の本番用レポートスイートにまとめてチャネルとルールセットを適用することができます。
>
>詳しくは、[複数のレポートスイートへのテンプレートレポートスイート設定の適用](/help/components/c-marketing-channels/getting-started/t-template.md)。

## 前提条件 {#prereqs}

必要な場合は、次の前提条件に関してカスタマーケアに問い合わせることができます。

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   詳しくは、Analytics ヘルプの「[一般的なアカウント設定](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html)」を参照してください。

* マーケティングチャネルディメンションへのアクセスを設定します。

   See [Marketing Channels permissions](/help/components/c-marketing-channels/mc-access/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## 処理に関する重要事項 {#important-proc-rules}

* システムは指定された順序でルールを処理し、ルールの 1 つが満たされると残りのルールの処理を中止します。
* ルールは VISTA が設定した変数にはアクセスできますが、VISTA が削除したデータにはアクセスできません。
* チャネルはコンバージョン指標のみを保存します。トラフィック指標は利用できません。
* 2 つのマーケティングチャネルが同じイベント（購入やクリックなど）からクレジットを受けることはありません。この点でマーケティングチャネルは eVar と異なります（同一イベントから 2 つの eVar がクレジットを受ける場合がある）。
* レポートは一度に 25 のチャネルまで処理できます。

