---
description: マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。
subtopic: Marketing channels
title: マーケティングチャネルの管理
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 100%

---

# マーケティングチャネルの管理

>[!NOTE]
>
> マーケティングチャネルに関する一般情報については、[マーケティングチャネルの基本を学ぶ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)を参照してください。
>
> Attribution と Customer Journey Analytics に対するマーケティングチャネルの効果を最大限に高めるために、[改訂版のベストプラクティス](/help/components/c-marketing-channels/mchannel-best-practices.md)を公開しました。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定編集]**／**[!UICONTROL マーケティングチャネル]**／**[!UICONTROL マーケティングチャネルマネージャー]**

マーケティングチャネルマネージャーでマーケティングチャネルを追加または有効化します。レポートスイートにマーケティングチャネルがない場合は、自動セットアップによって複数のチャネルと各チャネルのルールを作成することができます。ニーズに合わせて事前定義のチャネルを編集したり、独自に作成したりすることができます（合計 25 個まで）。

[!UICONTROL マーケティングチャネル]ページへのチャネルの追加は、[マーケティングチャネルの処理ルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)ページのルールの作成から独立して行うことができます。ルールを作成するときに、そのルールをチャネルに関連付けます。

チャネル作成時のガイドラインは次のとおりです。

* すべての訪問者が適切なチャネルに分類されるように、すべてのチャネルの一覧を作成し、事前に計画を立ててください。
* [内部](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)ヒット数のカテゴリのチャネルを含めます。
* 包括的な「その他のキャンペーン」チャネルを含め、有料チャネルの後、および有機チャネルの前に配置します。


## 前提条件 {#prereqs}

* マーケティングチャネルディメンションへのアクセスを設定します。

  詳しくは、[マーケティングチャネルの権限](/help/components/c-marketing-channels/c-channel-report-access.md)を参照してください。

## マーケティングチャネルの追加 {#add-mktg-channels}

マーケティングチャネルマネージャーでマーケティングチャネルを追加します。

>[!NOTE]
>
>チャネルは削除できません。使用しないチャネルは、無効にするか名前を変更し、後で使用するためにとっておきます。

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. [!UICONTROL Report Suite Manager] ページで、レポートスイートを選択します。

   複数のレポートスイートを選択した場合、テンプレートから選択したレポートスイートに設定をコピーするために、テンプレートを選択する必要があります。

   詳しくは、[複数のレポートスイートへのテンプレートレポートスイート設定の適用](/help/components/c-marketing-channels/c-getting-started-mchannel.md)を参照してください。

1. **[!UICONTROL 設定を編集]**／**[!UICONTROL マーケティングチャネル]**／**[!UICONTROL マーケティングチャネルマネージャー]**&#x200B;をクリックします。

   レポートスイートでチャネルが定義されていない場合、[自動セットアップ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)ページが表示されます。

1. [!UICONTROL マーケティングチャネルマネージャー]ページで、「**[!UICONTROL チャネルの追加]**」をクリックします。

   このオプションは、チャネルが 25 個定義されている場合は利用できません。

1. 「**[!UICONTROL 保存]**」をクリックします。
1. チャネルのルールを設定するには、「**[!UICONTROL マーケティングチャネルの処理ルール]**」をクリックします。

   [マーケティングチャネルの処理ルールの作成](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)を参照してください。

## チャネル設定の適用 {#mktg-channel-mgr}

[!UICONTROL マーケティングチャネルマネージャー]ページの各チャネルに適用できる設定は様々です。

| フィールド | 定義 |
|--- |--- |
| 有効 | このマーケティングチャネルの有効と無効を切り替えます。 |
| チャネル名 | マーケティングチャネルの分かりやすい名前をつけます。 |
| ラストタッチチャネルの上書き | ラストタッチチャネルを上書きするかどうかをチャネルごとに指定できます。このチェックボックスを選択すると、すべてのチャネル（「直接」と「内部」を含む）が既存のラストタッチチャネルを上書きします。設定を変更すると、誤ったチャネル（「直接」や「内部」）にコンバージョンが関連付けられるリスクがあるので、注意が必要です。たとえば、「自然検索」チャネルを通してユーザーが以前に獲得されている場合、「直接アクセス」での訪問が発生しても、「自然検索」のチャネルがコンバージョンのクレジットを引き続き受け取るようにしたい場合は、「直接アクセス」チャネルの「ラストタッチチャネルの上書き」オプションを外しておきます（デフォルト設定のまま変更しない）。 |
| チャネルの分類 | この値によって、チャネルを分類できます。[マーケティングチャネルの分類](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)を作成する場合、チャネル分類（サブチャネル）を追加することができます。 |
| タイプ | サイトへのユーザーの訪問手段を指定します。「オンライン」または「オフライン」を選択できます。検索エンジンまたは電子メールキャンペーンから来訪した訪問者に対しては「オンライン」チャネルを使用します。「オフライン」チャネルは、新聞のクーポンや雑誌の広告でサイトの情報を見つけた訪問者に使用します。オフラインチャネルには通常、データソースからインポートされたデータが含まれます。[データソース](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=ja)を参照してください。[オフラインデータの追加](/help/components/c-marketing-channels/c-getting-started-mchannel.md)を参照してください。 |
| Color | Reports &amp; Analytics のみ：このマーケティングチャネルに関連付けられている色。この色は、マーケティングチャネルレポートで、このチャネルを表します。 |

### ベストプラクティスの上書き

ダイレクトチャネルと内部チャネルのラストタッチの上書きオプションをオフにすることをお勧めします。これにより、他の永続的なラストタッチチャネル（または相互）からクレジットを取得できなくなります。

![](assets/int-channel2.png)

## チャネルルールの定義

レポートにチャネルとチャネルデータを表示できるようにするには、チャネルおよびそのデータを処理するための基本的なルールを作成してください。また、[訪問者エンゲージメント期間](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)の長さも指定できます。

アドビでは、[自動セットアップ](/help/components/c-marketing-channels/c-getting-started-mchannel.md)中に定義済みのチャネルをいくつか提供します。これらはニーズに合わせて編集できます。また、この設定を変更し、[マーケティングチャネルの処理ルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)内でカスタムルールを定義することもできます。

>[!NOTE]
>
>まずテスト用のレポートスイートにレポートを設定することを推奨します。それをひな形として、1 つまたはそれ以上の本番用レポートスイートにまとめてチャネルとルールセットを適用することができます。
>
>詳しくは、[複数のレポートスイートへのテンプレートレポートスイート設定の適用](/help/components/c-marketing-channels/c-getting-started-mchannel.md)を参照してください。
