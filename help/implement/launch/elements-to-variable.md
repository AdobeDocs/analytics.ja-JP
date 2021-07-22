---
title: タグデータ要素のAnalytics変数へのマッピング
description: Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 76%

---

# タグデータ要素のAnalytics変数へのマッピング

タグデータ要素のリポジトリを取得したら、それらをAnalyticsディメンションに割り当てることができます。

>[!NOTE]
>Adobe Experience Platform Launchは、Experience Platformのデータ収集テクノロジーのスイートとしてリブランドされました。 その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。 用語の変更点の一覧については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

## 前提条件 

[データレイヤーオブジェクトをデータ要素にマッピングする](layer-to-elements.md):タグデータ要素と、操作するデータ要素が複数あることを理解していることを確認します。

[ソリューションデザインドキュメントを作成する](../prepare/solution-design.md)：整理された状態を維持するには、ソリューションデザインドキュメントが不可欠です。ソリューションデザインドキュメントに従うと、データ要素を Analytics 変数へと簡単に割り当てることができます。

## データ要素を Analytics 変数に割り当てる

以下の手順に従ってタグライブラリを公開すると、Analysis Workspaceでカスタムディメンションを使用できます。 Analytics 変数は、グローバルに設定することも、個々のルール内で設定することもできます。

### グローバル変数の設定

グローバル変数は、データ要素が存在するあらゆるページで変数値を設定する場合に最適です。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」をクリックします。
1. 「[!UICONTROL グローバル変数]」アコーディオンをクリックすると、グローバル変数を割り当てるインターフェイスが表示されます。

### ルール内での変数の設定

ルールで設定された変数は、すべてのページで変数を設定したくない場合に最適です。ルールで条件を定義します。Adobe Experience Platform Launch ユーザーガイドの「[ルール](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/rules.html?lang=ja)」を参照してください。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブをクリックし、目的のルールをクリックします（または作成します）。
1. 「[!UICONTROL アクション]」の下の「[!UICONTROL 追加]」ボタンをクリックします。
1. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「変数を設定」に設定します。
1. 目的の Analytics 変数の右側にある![データ要素](assets/data-element.png)アイコンをクリックします。組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)には、使用する Analytics 変数が記載されています。
1. モーダルウィンドウで目的のデータ要素を選択します。「[!UICONTROL 選択]」をクリックします。
1. `%` 記号で囲まれたテキストフィールドに、データ要素名が追加されます。例えば、データ要素に「Page name」という名前を付けた場合、変数にデータ要素を割り当てると、文字列 `%Page name%` 表示されます。

>[!TIP]
>
> 同じ変数内のデータ要素を連結できます。例えば、「Hostname」データ要素と「Pathname」データ要素がある場合、`%Hostname%%Pathname%` を使用して、両方を 1 つの変数に組み合わせることができます。

## 次の手順

[ページ変数](../vars/page-vars/page-variables.md)：Analysis Workspace でディメンションを活用するために、実装で使用できるページレベルの変数について説明します。

[設定変数](../vars/config-vars/configuration-variables.md)：Adobe Analytics で他の機能のロックを解除するために、実装で使用できる設定変数について説明します。
