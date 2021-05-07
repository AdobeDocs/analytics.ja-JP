---
title: Adobe Analytics でのボットの削除
description: Adobe Analytics でボットを削除する 3 つの方法
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
translation-type: tm+mt
source-git-commit: b78e8303277b08a4c693283e45416f2e104268b7
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 93%

---

# Adobe Analytics でのボットの削除

Adobe Analytics には、レポートからボットトラフィックを削除する複数のオプションがあります。

## ボットルールの使用

標準のボットフィルタリング方法とカスタムのボットフィルタリング方法の両方が **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL 一般]**／**[!UICONTROL ボットルール]**&#x200B;にあります。

| ルールタイプ | 説明 |
|--- |--- |
| 標準 IAB ボットルール | 「**[!UICONTROL IAB ボットフィルタリングルールを有効にする]**」を選択すると、[IAB](https://www.iab.com/)（International Advertising Bureau）の「International Spiders &amp; Bots Lists」を使用してボットトラフィックを削除します。ほとんどのお客様は、少なくともこのオプションを選択します。 |
| カスタムボットルール | ユーザーエージェント、IP アドレス、または IP 範囲に基づいて、カスタムボットルールを定義して追加できます。 |

詳しくは、[ボットルールの概要](/help/admin/admin/bot-removal/bot-rules.md)を参照してください。

## [!UICONTROL webサイトボット]プラグインを使用してボットを識別します。

webサイトボットプラグインを使用すると、デスクトップ訪問者がボットかどうかを動的に識別できます。 このデータを使用すると、あらゆる種類のレポートの精度を高め、合法なサイトトラフィックの測定を改善することができます。

このプラグインでは、次の 2 つのチェックを実行します。

* まず、navigator.UserAgent変数を使用して、デバイスがデスクトップデバイスかモバイルデバイスかを判断します。 モバイルデバイスは無視されます。
* デスクトップデバイスの場合は、マウスの動きに対するイベントリスナーを追加します。

詳しくは、『[Adobe Analytics導入ガイド](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html)』を参照してください。

## アドビツールを組み合わせて使用

さらに、すばやく変形するボットに対応するために、アドビでは、適切かつ定期的に組み合わせることで、データ品質に悪影響を与えるボットを排除するのに役立つ、強力な機能をいくつか提供しています。提供されている機能：Experience Cloud ID サービス、セグメント化、Data Warehouse、顧客属性、および仮想レポートスイート。以下に、これらのツールの活用方法の概要を示します。

### 手順 1：訪問者の Experience Cloud ID を新しい宣言済み ID に渡す

まず、[People コアサービス](https://docs.adobe.com/content/help/ja-JP/core-services/interface/audiences/audience-library.html)で新しい宣言済み ID を作成します。訪問者の Experience Cloud ID をこの新しい宣言済み ID に渡す必要があります。[Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) を使用すると、この処理をすばやく簡単におこなうことができます。宣言済み ID に「ECID」という名前を使用するとします。

![](assets/bot-cust-attr-setup.png)

この ID をデータ要素経由で取得する方法を次に示します。データ要素には、正しい Experience Cloud 組織 ID を入力するようにしてください。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

このデータ要素を設定したら、[次の手順](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html)に従って、Launch の ECID ツールに宣言済み ID を渡します。

### 手順 2：セグメント化を使用したボットの識別

訪問者の ECID を宣言済み ID に渡したので、[Analysis Workspace のセグメント化](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)を使用して、ボットのような行動をとる訪問者を識別できます。ボットは、多くの場合、直帰数、通常と異なるユーザーエージェント、不明なデバイス／ブラウザー情報、リファラーがない、新規訪問者、通常と異なるランディングページなどの動作によって定義されます。Workspace のドリルダウンとセグメント化の機能を使用して、IAB フィルタリングとレポートスイートのボットルールを回避したボットを識別します。例として、使用できるセグメントのスクリーンショットを次に示します。

![](assets/bot-filter-seg1.png)

### 手順 3：Data Warehouse を使用してセグメントからすべての [!DNL Experience Cloud IDs] を書き出す

セグメントを使用してボットを識別したら、次に、Data Warehouse を利用してこのセグメントに関連付けられたすべての Experience Cloud ID を抽出します。次に、[Data Warehouse](https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html) リクエストの設定方法を示します。

![](assets/bot-dwh-3.png)

必ず Experience Cloud 訪問者 ID をディメンションとして使用し、ボットセグメントを適用してください。

### 手順 4：このリストを顧客属性としてアドビに渡す

Data Warehouse レポートが届いたら、履歴データからフィルタリングする必要のある ECID のリストが表示されます。これらの ECID をコピーして、2 列のみ（ECID とボットフラグ）からなる空白の .CSV ファイルに貼り付けます。

* **ECID**：この列ヘッダーが、上記の新しい宣言済み ID に付けた名前と一致することを確認してください。
* **ボットフラグ**：これを顧客属性スキーマディメンションとして追加します。

この .CSV ファイルを顧客属性の読み込みファイルとして使用し、この[ブログ投稿](https://theblog.adobe.com/link-digital-behavior-customers)の説明に従って、顧客属性にレポートスイートを登録します。

![](assets/bot-csv-4.png)

### 手順 5：新しい顧客属性を利用したセグメントの作成

データセットが処理され、Analysis Workspace に統合されたら、新しい「ボットフラグ」顧客属性ディメンションと [!UICONTROL Exclude] コンテナを利用するもう 1 つのセグメントを作成します。

![](assets/bot-filter-seg2.png)

### 手順 6：このセグメントを仮想レポートスイートフィルターとして使用する

最後に、次のように、このセグメントを利用して識別されたボットを除外する[仮想レポートスイート](/help/components/vrs/vrs-about.md)を作成する必要があります。

![](assets/bot-vrs.png)

この新しくセグメント化された仮想レポートスイートでは、識別されたボットが完全に削除され、非常にクリーンなデータセットになります。

### 手順 7：手順 2、3、4 を定期的に繰り返す

リマインダーを毎月 1 回以上（定期的にスケジュールされた分析の前などに）設定し、新しいボットの識別とフィルタリングをおこないます。
