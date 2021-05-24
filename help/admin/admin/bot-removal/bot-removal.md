---
title: Adobe Analytics でのボットの削除
description: Adobe Analyticsでボットを削除する方法
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: bb8ccbf782a1431e5278a95923a42c9e9e9e862b
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 53%

---

# Adobe Analytics でのボットの削除

Adobe Analytics には、レポートからボットトラフィックを削除する複数のオプションがあります。

## ボットルールの使用

標準のボットフィルタリング方法とカスタムのボットフィルタリング方法の両方が **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL 一般]**／**[!UICONTROL ボットルール]**&#x200B;にあります。

| ルールタイプ | 説明 |
|--- |--- |
| 標準 IAB ボットルール | 「**[!UICONTROL IAB ボットフィルタリングルールを有効にする]**」を選択すると、[IAB](https://www.iab.com/)（International Advertising Bureau）の「International Spiders &amp; Bots Lists」を使用してボットトラフィックを削除します。ほとんどのお客様は、少なくともこのオプションを選択します。 |
| カスタムボットルール | ユーザーエージェント、IPアドレスまたはIP範囲に基づいて、カスタムボットルールを定義して追加できます。 |

詳しくは、[ボットルールの概要](/help/admin/admin/bot-removal/bot-rules.md)を参照してください。

## [!UICONTROL webサイトボット]プラグインを使用してボットを識別します。

[!UICONTROL websiteBot]プラグインを使用すると、デスクトップ訪問者がボットであるかどうかを動的に識別できます。 このデータを使用すると、あらゆる種類のレポートの精度を高め、合法なサイトトラフィックの測定を改善することができます。

このプラグインでは、次の 2 つのチェックを実行します。

* まず、navigator.UserAgent変数を使用して、デバイスがデスクトップかモバイルデバイスかを判断します。 モバイルデバイスは無視されます。
* デスクトップデバイスの場合は、マウスの動きに対するイベントリスナーを追加します。

詳しくは、『Adobe Analytics実装ガイド[』を参照してください。](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html)

## アドビツールを組み合わせて使用

さらに、すばやく変形するボットに対応するために、アドビでは、適切かつ定期的に組み合わせることで、データ品質に悪影響を与えるボットを排除するのに役立つ、強力な機能をいくつか提供しています。提供されている機能：Experience Cloud ID サービス、セグメント化、Data Warehouse、顧客属性、および仮想レポートスイート。これらのツールの使用方法の概要を次に示します。

### 手順 1：訪問者の Experience Cloud ID を新しい宣言済み ID に渡す

開始するには、[Peopleコアサービス](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)に新しい宣言済みIDを作成します。 訪問者のExperience CloudIDをこの新しい宣言済みIDに渡します。この処理は、[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)を使用すると、すばやく簡単におこなえます。 宣言済み ID に「ECID」という名前を使用するとします。

![](assets/bot-cust-attr-setup.png)

この ID をデータ要素経由で取得する方法を次に示します。データ要素には、Experience CloudのOrgIDを正しく入力してください。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

このデータ要素を設定したら、[次の手順](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)に従って、AdobeLaunchのECIDツールに宣言済みIDを渡します。

### 手順 2：セグメント化を使用したボットの識別

訪問者の ECID を宣言済み ID に渡したので、[Analysis Workspace のセグメント化](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)を使用して、ボットのような行動をとる訪問者を識別できます。ボットは、多くの場合、直帰数、通常と異なるユーザーエージェント、不明なデバイス／ブラウザー情報、リファラーがない、新規訪問者、通常と異なるランディングページなどの動作によって定義されます。Workspace のドリルダウンとセグメント化の機能を使用して、IAB フィルタリングとレポートスイートのボットルールを回避したボットを識別します。例として、使用できるセグメントのスクリーンショットを次に示します。

![](assets/bot-filter-seg1.png)

### 手順 3：Data Warehouse を使用してセグメントからすべての [!DNL Experience Cloud IDs] を書き出す

セグメントを使用してExperience Cloudを識別したので、次の手順では、Data Warehouseを使用して、このセグメントに関連付けられているすべてのボットIDを抽出します。 次のスクリーンショットは、[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)リクエストの設定方法を示しています。

![](assets/bot-dwh-3.png)

忘れずにExperience Cloud訪問者IDをディメンションとして使用し、「ボット」セグメントを適用してください。

### 手順 4：このリストを顧客属性としてアドビに渡す

Data Warehouseレポートが届くと、履歴データからフィルタリングする必要のあるECIDのリストが表示されます。 これらの ECID をコピーして、2 列のみ（ECID とボットフラグ）からなる空白の .CSV ファイルに貼り付けます。

* **ECID**:この列ヘッダーが、上記の新しい宣言済みIDに付けた名前と一致することを確認してください。
* **ボットフラグ**:「ボットフラグ」を顧客属性スキーマディメンションとして追加します。

この .CSV ファイルを顧客属性の読み込みファイルとして使用し、この[ブログ投稿](https://theblog.adobe.com/link-digital-behavior-customers)の説明に従って、顧客属性にレポートスイートを登録します。

![](assets/bot-csv-4.png)

### 手順 5：新しい顧客属性を利用したセグメントの作成

データセットが処理され、Analysis Workspaceに統合されたら、新しい「ボットフラグ」顧客属性ディメンションと[!UICONTROL Exclude]コンテナを利用する1つのセグメントを作成します。

![](assets/bot-filter-seg2.png)

### 手順 6：このセグメントを仮想レポートスイートフィルターとして使用する

最後に、このセグメントを使用して識別されたボットを除外する[仮想レポートスイート](/help/components/vrs/vrs-about.md)を作成します。

![](assets/bot-vrs.png)

この新しくセグメント化された仮想レポートスイートでは、識別されたボットが削除され、よりクリーンなデータセットが得られるようになりました。

### 手順 7：手順 2、3、4 を定期的に繰り返す

新しいボット（定期的にスケジュールされた分析の前など）を識別してフィルタリングするために、少なくとも毎月のリマインダーを設定します。
