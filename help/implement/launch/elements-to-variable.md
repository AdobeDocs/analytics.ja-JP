---
title: 起動データ要素のAnalytics変数へのマッピング
description: データ要素をAnalytics変数に割り当て、Analytics Workspaceでディメンションとして使用できるようにします。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 起動データ要素のAnalytics変数へのマッピング

Adobe Experience Platform Launchでデータ要素のリポジトリを取得したら、それらをAnalyticsディメンションに割り当てることができます。

## 前提条件

[データレイヤーオブジェクトのデータ要素へのマップ](layer-to-elements.md):「起動」のデータ要素と、操作する必要のある要素がいくつかあることを確認します。

[ソリューションデザインドキュメント](../prepare/solution-design.md):ソリューション設計ドキュメントは、整理を維持するために不可欠です。 ソリューションデザインドキュメントに従うと、Analytics変数へのデータ要素の割り当てが簡単になります。

## Analytics変数へのデータ要素の割り当て

次の手順に従った後で起動でライブラリを公開すると、Launch Workspaceでカスタムディメンションを分析できます。 Analytics変数は、グローバルに、または個々のルール内に設定できます。

### グローバル変数の設定

グローバル変数は、データ要素が存在するすべてのページで変数値を設定する場合に最適です。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の「起動」プロパティをクリックします。
1. Click the [!UICONTROL Extensions tab], then click [!UICONTROL Configure] under the Adobe Analytics extension.
1. 「グローバル変数  」アコーディオンをクリックすると、グローバル変数を割り当てるためのインターフェイスが表示されます。

### ルール内の変数の設定

ルールに設定された変数は、すべてのページで変数を設定したくない場合に最適です。 ルールで条件を定義します。 See [Rules](https://docs.adobe.com/content/help/ja-JP/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の「起動」プロパティをクリックします。
1. 「ルール」タ [!UICONTROL ブをクリックし] 、目的のルールをクリックします（または作成します）。
1. 「アクション」の下 [!UICONTROL 追加にあるボタンをク] リックしま す。
1. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「変数を設定」に設定します。
1. 目的のAnalytics変 ![数の右に](assets/data-element.png) 、データ要素アイコンをクリックします。 組織のソリューションデザ [インドキュメント](../prepare/solution-design.md) （Analytics変数）は、どの変数を使用するかを指定します。
1. モーダルウィンドウで目的のデータ要素を選択します。 「選択」をク [!UICONTROL リックしま]す。
1. データ要素名は、記号で囲まれたテキストフィールドに追加さ `%` れます。 例えば、データ要素に「Page name」という名前を付けた場合、変数にデータ要素を割り当てる `%Page name%` ときに文字列が表示されます。

>[!TIP] 同じ変数内のデータ要素を連結できます。 例えば、「Hostname」データ要素と「Pathname」データ要素がある場合は、を使用して、両方を単一の変数に組み合わせることができま `%Hostname%%Pathname%`す。

## 次の手順

[ページ変数](../vars/page-vars/page-variables.md):実装で使用できるページレベルの変数を説明し、Workspaceのディメンションをさらに活用します。分析

[設定変数](../vars/config-vars/configuration-variables.md):Adobe Analyticsの他の機能のロックを解除するために、実装で使用できる設定変数について説明します。
