---
description: Analytics インベントリの使用
title: Analytics インベントリ
feature: Admin Tools
role: Admin
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 22%

---

# Analytics インベントリ {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Analytics インベントリ"
>abstract="このページでは、プロジェクトとコンポーネントの数、レポートスイート、ユーザーなど、Adobe Analytics 環境の包括的な概要について説明します。この情報は、Customer Journey Analytics へのアップグレードの準備を開始する際に特に役立ちます。"

<!-- markdownlint-enable MD034 -->

Analytics Inventory は、プロジェクトとコンポーネントの数、レポートスイート、ユーザーなど、Adobe Analytics環境の包括的な概要を提供します。 この情報は、Customer Journey Analytics へのアップグレードの準備を開始する際に特に役立ちます。

Analytics インベントリの目的は、次の質問に答えるのに役立つことです。

* 組織にとって、移行が必要なアセット（レポートスイート、セグメント、ユーザー、ワークスペースプロジェクトなど）はどれか、そして移行しなくてもよいアセットはどれか。

* 移行する必要があるアセットを決定したら、次の手順を実行します。

   * このアップグレードの前にアセットのクリーンアップを実行する必要がありますか。

   * プロセスの一環としてアセットの統合を行う必要がありますか？

   * アップグレードシーケンスはアセットに対して何にする必要がありますか？

   * 最初または最後にアップグレードするレポートスイートは？

## 権限

Analytics Inventory は、[Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics) のAdobe Analytics製品管理者権限を持つユーザーが使用できます。

## Analytics インベントリへのアクセス

1. **[!UICONTROL 管理者]** メニューの **[!UICONTROL Analytics インベントリ]** をクリックします。 または、**[!UICONTROL すべての管理者]**/**[!UICONTROL Analytics インベントリ]** に移動します。

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. メイン画面には、Adobe Analytics環境の包括的なインベントリが表示されます。

   ![ メインインベントリ画面 ](assets/an_inventory.png)

   特に、この画面には次の内容が表示されます。

   * この組織の下でアクティブなAnalysis Workspaceおよびモバイルスコアカードプロジェクトの、すべてのユーザーにわたる合計数。
   * すべてのユーザーをまたいで、この組織の下でアクティブなセグメントと計算指標の合計数。
   * 定義されたベースレポートスイートの合計数。 仮想レポートスイートは含まれません。
   * Media Analytics 機能がアクティブな場合は、どのモードで実行するか。
   * この組織で定義されたユーザーの合計数。


## コンポーネント {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="コンポーネント"
>abstract="このセクションには、Adobe Analytics 環境に存在するプロジェクト、セグメント、計算指標の数が表示されます。プロジェクトとコンポーネントは、Customer Journey Analytics に移行できます。"

<!-- markdownlint-enable MD034 -->

この最初のリリースでは、Workspace プロジェクト、セグメントおよび計算指標の概要在庫数を確認できます。 今後のリリースでは、これらのコンポーネントを分析できるようになります。

## データの設定と収集 {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="データの設定と収集"
>abstract="このセクションには、Adobe Analytics 環境内のレポートスイートの数と、ストリーミングメディアサービスへのアクセス権が表示されます。"

<!-- markdownlint-enable MD034 -->

### レポートスイート

レポートスイート表示には、組織の下で定義されたすべてのレポートスイートが表示されます。 次の質問に答えることができます。

* 過去 90 日間に最もヒットしたレポートスイートはどれですか。
* 過去 90 日間にヒットがなかったレポートスイートは何ですか。
* 最大数のディメンションが定義されているレポートスイートはどれですか？
* 最も多くの指標が定義されているレポートスイートはどれですか？

これらの質問に対する回答は、どのレポートスイートが移行の最適な候補であるかについての優れたアイデアを提供します。

>[!NOTE]
>
>この表は、一度に 1 つのセル値をゆっくりと入力します。


1. レポートスイートを分析するには、**[!UICONTROL データ設定と収集]**/**[!UICONTROL レポートスイート]** に移動し、「**[!UICONTROL 分析]**」をクリックします。

   ![ レポートスイートのリスト ](assets/an_inv_rs.png)

   | 要素 | 説明 |
   | --- | --- |
   | 名前 | レポートスイートの名前 |
   | ID | レポートスイート ID （rsid）。 英数字文字のみ含めることができる一意の ID を指定します。この ID は作成後は変更できません。アドビによって設定される必須の ID プレフィックスも変更できません。 |
   | 発生件数 (過去 90 日間) | 「発生件数」指標は、特定のディメンションが設定または持続されたヒット数を示します。過去 90 日間にこのレポートスイートが受け取ったヒット数 |
   | 指標 | このレポートスイートで定義されている指標の数 |
   | ディメンション | このレポートスイートで定義されているディメンションの数 |
   | Analytics for Target (A4T) は有効になっています | [ デフォルトでは非表示 ] このレポートスイートは [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t) に対して有効になっていますか？ |
   | マーケティングチャネルは有効になっています | [ デフォルトでは非表示 ] このレポートスイートは [ マーケティングチャネル ](https://experienceleague.adobe.com/ja/docs/analytics/components/marketing-channels/c-getting-started-mchannel) に対して有効になっていますか？ |
   | ソースコネクタは有効になっています | このレポートスイートは、Adobe Experience Platformの [Adobe Analytics Source Connector for report suite data](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics) に対して有効になっていますか？ つまり、このレポートスイートは、Analytics Source Connector を使用してCustomer Journey Analyticsに移行できますか。 |
   | カレンダータイプ | [ デフォルトでは非表示 ] 詳細については、「[ カスタムカレンダー ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#)」を参照してください |

#### ディメンションの分析

この画面には、特定のレポートスイートに定義されたすべてのディメンションの詳細が表示されます。 このビューでは、次の質問に答えることができます。

* このレポートスイートに対して有効なディメンションは何ですか？
* このディメンションの過去 90 日間の上位 10 個のディメンション項目は何ですか？

1. レポートスイートページで **[!UICONTROL ディメンション]** リンクをクリックします。

   | 要素 | 説明 |
   | --- | --- |
   | 名前 | ディメンションの名前 |
   | ID | ディメンション ID。 |
   | タイプ | ディメンションのタイプ。 使用可能な値には、コンバージョン、トラフィック、ナビゲーション、トラフィックソース、顧客、日付またはAdobe製品固有のディメンション（AEM、オーディエンス、Adobe Campaign、モバイルアプリなど）があります。 |
   | 説明 | すべてのディメンションに説明があるわけではありません。 |
   | ソースコネクタは有効になっています | このディメンションは、Adobe Experience Platformの [Adobe Analytics Source Connector for report suite data](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics) に対して有効になっていますか？ つまり、このディメンションは、Analytics Source Connector を使用してCustomer Journey Analyticsに移行できますか。 |

1. CJAに移行する意味のあるディメンションを判断します。


#### 指標の分析

この画面には、特定のレポートスイート用に定義されたすべての指標の詳細が表示されます。 このビューでは、次の質問に答えることができます。

* このレポートスイートに対して有効になっている指標は何ですか？
* 過去 90 日間の上位 10 個の指標は何ですか？

1. レポートスイートページの **[!UICONTROL 指標]** リンクをクリックします。


   | 要素 | 説明 |
   | --- | --- |
   | 名前 | 指標の名前 |
   | ID | 指標 ID。 |
   | タイプ | 指標のタイプ。 使用可能な値には、コンバージョン、トラフィック、ナビゲーション、トラフィックソース、顧客、日付またはAdobe製品固有のディメンション（AEM、オーディエンス、Adobe Campaign、モバイルアプリなど）があります。 |
   | 説明 | すべてのディメンションに説明があるわけではありません。 |
   | ソースコネクタは有効になっています | この指標は、Adobe Experience Platformの [Adobe Analytics Source Connector for report suite data](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/analytics) に対して有効になっていますか？ つまり、この指標は、Analytics Source Connector を使用してCustomer Journey Analyticsに移行できますか。 |

1. CJAに移行する意味のある指標を判断します。

### CSV に書き出し

1. レポートスイート、ディメンション、指標のリストを.csv ファイルに書き出すには、「**[!UICONTROL CSV に書き出し]**」をクリックします。

1. .csv ファイルがダウンロードフォルダーに表示されます。

1. を開き、デバイスのスプレッドシートアプリケーションで保存します。

>[!NOTE]
>
>除外された項目と列は、.csv ファイルに書き出されません。


### フィルター、検索、並べ替え、移動

* テーブルを検索できます。
* 左側のパネルで、フィルターアイコンをクリックして、「タイプ」でフィルタリングします。 または、「**[!UICONTROL フィルターを非表示]**」をクリックします。
* すべての列を昇順/降順で並べ替えることができます（単一の列の並べ替えのみ）。
* パンくずリスト内の項目をクリックすると、別の画面に移動できます。

## ユーザー管理 {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="ユーザー管理"
>abstract="このセクションには、Adobe Analytics 環境内のユーザーの数が表示されます。"

<!-- markdownlint-enable MD034 -->

ユーザー管理は、Analytics インベントリの今後のリリースで使用できるようになります。

## コンポーネントの移行

[ コンポーネントの移行 ](/help/admin/admin/component-migration/component-migration.md) を使用して、Adobe Analytics管理者は、Analytics プロジェクトとそれに関連するコンポーネントをCustomer Journey Analyticsに移行できます。

移行プロセスには、次が含まれます。

* Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。

* Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。