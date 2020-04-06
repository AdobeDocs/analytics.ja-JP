---
description: マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。マーケティングチャネルのないレポートスイートの場合、自動セットアップを使用すると、複数のチャネルとそのルールを作成できます。 必要に応じて、定義済みのチャネルを編集したり、独自の（合計25個まで）を作成したりできます。
subtopic: Marketing channels
title: マーケティングチャネルの管理
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# マーケティングチャネルの管理

マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。マーケティングチャネルのないレポートスイートの場合、自動セットアップを使用すると、複数のチャネルとそのルールを作成できます。 必要に応じて、定義済みのチャネルを編集したり、独自の（合計25個まで）を作成したりできます。

以下に、チャネル作成のガイドラインを示します。

* すべてのチャネルのリストを作成し、すべての訪問者ヒットが適切な分類に分類されるようにして、事前に計画を立てます。
* 内部ヒットと直接ヒットのカテゴリ [のチャネル](/help/components/c-marketing-channels/c-faq.md) を常に含 [めます](/help/components/c-marketing-channels/c-faq.md) 。

ページへのチャネルの追 [!UICONTROL Marketing Channels] 加は、マーケティングチャネルの処理ルールページでのルールの作成とは [独立して行われます](/help/components/c-marketing-channels/c-rules.md) 。 ルールを作成するときに、そのルールをチャネルに関連付けます。

## マーケティングチャネルの追加 {#add-mktg-channels}

マーケティングチャネルマネージャーでマーケティングチャネルを追加します。

>[!NOTE]チャネルは削除できません。使用しないチャネルは、無効にするか名前を変更し、後で使用するためにとっておきます。

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.

   複数のレポートスイートを選択する場合は、テンプレートから選択したレポートスイートに設定をコピーするテンプレートを選択します。

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   レポートスイートでチャネルが定義されていない場合、[自動セットアップ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)ページが表示されます。

1. ページ上で、 [!UICONTROL Marketing Channel Manager] をクリックしま **[!UICONTROL Add Channel]**&#x200B;す。

   このオプションは、チャネルが 25 個定義されている場合は利用できません。

1. ズーム後に **[!UICONTROL Save.]**
1. ルールを設定するには、をチャネルに対してクリックしま **[!UICONTROL Marketing Channel Processing Rules]**&#x200B;す。

   [マーケティングチャネルの処理ルールの作成](/help/components/c-marketing-channels/c-rules.md)を参照してください。

## マーケティングチャネルマネージャー - インターフェイスの定義 {#mktg-channel-mgr}

ページのフィールドの定 [!UICONTROL Marketing Channel Manager] 義です。

| フィールド | 定義 |
|--- |--- |
| 有効 | このマーケティングチャネルを有効または無効にします。 |
| チャネル名 | マーケティングチャネルのわかりやすい名前。 |
| ラスト タッチ チャネルの上書き | 既存の永続的なラストタッチチャネルを、選択したラストタッチで上書きするかどうかをチャネルします。 このチェックボックスを選択すると、すべてのチャネル（「直接」と「内部」を含む）が既存のラストタッチチャネルを上書きします。 その結果、コンバージョンはクレジットを受けるに値しないチャネルに関連付けられます。 例えば、このオプションを使用すると、自然検索チャネルを使用して以前にチャネルを取得した場合に、ダイレクトユーザーがコンバージョンのクレジットを受け取らないようにできます。 |
| チャネルの分類 | この値でチャネルを分類できます。 マーケティングチャネルの分類を作成する際に、分類（サブチャネル）を追 [加することができ](/help/components/c-marketing-channels/classifictions-mchannel.md)ます。 |
| タイプ | ユーザーがサイトに来た方法を指定します。 「オンライン」または「オフライン」を選択できます。[オンラインチャネル]は、検索訪問者や電子メールキャンペーンに使用します。 オフラインチャネルは、新聞のクーポンや訪問者の広告でサイトを見つけた人に適用されます。 オフラインチャネルには、通常、データソースからインポートされたレポートが含まれます。 [データソース](https://docs.adobe.com/content/help/ja-JP/analytics/import/data-sources/datasrc-home.html)を参照してください。[オフラインデータの追加](/help/components/c-marketing-channels/c-getting-started-mchannel.md)を参照してください。 |
| 色 | このマーケティングチャネルに関連付ける色。 この色は、マーケティングチャネルレポートで、このチャネルを表します。 |

## 定義チャネル

チャネルとチャネルデータをレポートに表示する前に、データを処理するチャネルと基になるルールを作成します。 また、関連するチャネルのコストと予算額を作成し、訪問者のエンゲージメント期間の長さを指定することもできます。 管理ツールでレポート設定タスクを実行します。

訪問のコンテナと考えます。 このルールは、訪問を適切なコンテナに割り当てます。

![](assets/buckets_2.png)

アドビでは、自動設定時に定義済みのチャネルをい [くつか提供します](/help/components/c-marketing-channels/c-getting-started-mchannel.md) 。これらのオプションは、ニーズに合わせて編集できます。

>[!NOTE]
>
>まずテスト用のレポートスイートにレポートを設定することを推奨します。テンプレートを使用して、1つ以上の実稼働用レポートスイートにチャネルとルールセットをグローバルに適用することができます。
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### 前提条件 {#prereqs}

必要な場合は、次の前提条件に関してカスタマーケアに問い合わせることができます。

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   詳しくは、Analytics ヘルプの「[一般的なアカウント設定](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/general-acct-settings-admin.html)」を参照してください。

* マーケティングチャネルディメンションへのアクセスを設定

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### 処理に関する重要事項 {#important-proc-rules}

* ルールは指定した順序で処理され、ルールが満たされると、残りのルールの処理が停止します。
* ルールはVISTAが設定した変数にアクセスできますが、VISTAが削除したデータにはアクセスできません。
* チャネルには、コンバージョン指標のみが保存されます。 トラフィック指標は使用できません。
* 2人のマーケティングチャネルが同じイベント（購入やクリックなど）のクレジットを受け取ることはありません。 このように、マーケティングチャネルはeVar(同じイベントのクレジットを2つのeVarが受け取る場合)とは異なります。
* レポートは一度に最大25個のチャネルを処理できます。

