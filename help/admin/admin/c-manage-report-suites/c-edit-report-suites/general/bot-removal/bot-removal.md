---
title: Adobe Analytics でのボットの削除
description: Adobe Analytics でボットを削除する方法
feature: Bot Removal
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 84%

---

# Adobe Analytics でのボットの削除

Adobe Analytics には、レポートからボットトラフィックを削除する複数のオプションがあります。

## ボットルールの使用

標準のボットフィルタリング方法とカスタムのボットフィルタリング方法の両方が **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL 一般]**／**[!UICONTROL ボットルール]**&#x200B;にあります。

| ルールタイプ | 説明 |
|--- |--- |
| 標準 IAB ボットルール | 「**[!UICONTROL IAB ボットフィルタリングルールを有効にする]**」を選択すると、[IAB](https://www.iab.com/)（International Advertising Bureau）の「International Spiders &amp; Bots Lists」を使用してボットトラフィックを削除します。ほとんどのお客様は、少なくともこのオプションを選択します。 |
| カスタムボットルール | ユーザーエージェント、IP アドレス、または IP 範囲に基づいて、カスタムボットルールを定義して追加できます。 |

詳しくは、[ボットルールの概要](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)を参照してください。

## [!UICONTROL websiteBot] プラグインを使用してボットを識別します。

[!UICONTROL websiteBot] プラグインを使用すると、デスクトップ訪問者がボットかどうかを動的に識別できます。このデータを使用すると、あらゆる種類のレポートの精度を高め、合法なサイトトラフィックの測定を改善できます。

このプラグインでは、次の 2 つのチェックを実行します。

* まず、navigator.UserAgent 変数を使用して、デバイスがデスクトップかモバイルデバイスかを判断します。モバイルデバイスは無視されます。
* デスクトップデバイスの場合は、マウスの動きに対するイベントリスナーを追加します。

詳しくは、『[Adobe Analytics 実装ガイド](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html?lang=ja)』を参照してください。

## アドビツールを組み合わせて使用

さらに、すばやく変形するボットに対応するために、アドビでは、適切かつ定期的に組み合わせることで、データ品質に悪影響を与えるボットを排除するのに役立つ、強力な機能をいくつか提供しています。Experience CloudID サービス、セグメント化、Data Warehouse、顧客属性および仮想レポートスイートの機能が含まれます。 以下に、これらのツールを使う方法の概要を示します。

### 手順 1：訪問者の Experience Cloud ID を新しい宣言済み ID に渡す

まず、[People コアサービス](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja)で新しい宣言済み ID を作成します。訪問者の Experience Cloud ID をこの新しい宣言済み ID に渡します。[Adobe Experience Platform のタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=ja) を使用すると、この処理を素早く簡単に行うことができます。宣言済み ID に「ECID」という名前を使用するとします。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

この ID をデータ要素経由で取得する方法を次に示します。データ要素には、正しい Experience Cloud 組織 ID を入力するようにしてください。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

このデータ要素を設定したら、[次の手順](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=ja)に従って Adobe Experience Platform のタグを使用して ECID ツールに宣言済み ID を渡します。

### 手順 2：セグメント化を使用したボットの識別

訪問者の ECID を宣言済み ID に渡したので、[Analysis Workspace のセグメント化](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=ja)を使用して、ボットのような行動をとる訪問者を識別できます。ボットは、多くの場合、直帰数、通常と異なるユーザーエージェント、不明なデバイス／ブラウザー情報、リファラーがない、新規訪問者、通常と異なるランディングページなどの動作によって定義されます。Workspace のドリルダウンとセグメント化の機能を使用して、IAB フィルタリングとレポートスイートのボットルールを回避したボットを識別します。例として、使用できるセグメントのスクリーンショットを次に示します。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### 手順 3：Data Warehouse を使用してセグメントからすべての [!DNL Experience Cloud IDs] を書き出す

セグメントを使用してボットを識別したら、次に、Data Warehouse を使用してこのセグメントに関連付けられたすべての Experience Cloud ID を抽出します。このスクリーンショットは、[Data Warehouse](/help/export/data-warehouse/data-warehouse.md) リクエストの設定方法を示します。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

必ず Experience Cloud 訪問者 ID をディメンションとして使用し、ボットセグメントを適用してください。

### 手順 4：このリストを顧客属性としてAdobeに渡す

Data Warehouse レポートが届いたら、履歴データからフィルタリングする必要のある ECID のリストが表示されます。これらの ECID をコピーして、2 列のみ（ECID とボットフラグ）からなる空白の .CSV ファイルに貼り付けます。

* **ECID**：この列ヘッダーが、上記の新しい宣言済み ID に付けた名前と一致することを確認してください。
* **ボットフラグ**:「ボットフラグ」を顧客属性スキーマディメンションとして追加します。

この.CSV ファイルを顧客属性の読み込みファイルとして使用し、この説明に従って、顧客属性にレポートスイートを登録します。 [ブログ投稿](https://theblog.adobe.com/link-digital-behavior-customers).

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### 手順 5：新しい顧客属性を利用したセグメントの作成

データセットが処理され、Analysis Workspace に統合されたら、新しい「ボットフラグ」顧客属性ディメンションと [!UICONTROL Exclude] コンテナを利用するもう 1 つのセグメントを作成します。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### 手順 6：このセグメントを仮想レポートスイートフィルターとして使用する

最後に、 [仮想レポートスイート](/help/components/vrs/vrs-about.md) では、このセグメントを使用して、識別されたボットを除外します。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

この新しくセグメント化された仮想レポートスイートでは、識別されたボットが削除され、よりクリーンなデータセットが得られるようになりました。

### 手順 7：手順 2、3、4 を定期的に繰り返す

リマインダーを毎月 1 回以上（定期的にスケジュールされた分析の前などに）設定し、新しいボットの識別とフィルタリングを行います。
