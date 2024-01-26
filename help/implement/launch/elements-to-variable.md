---
title: タグデータ要素の Analytics 変数へのマッピング
description: Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 96%

---


# タグデータ要素の Analytics 変数へのマッピング

タグデータ要素のリポジトリーを取得したら、それらを Analytics のディメンションに割り当てることができます。

## 前提条件 

[データレイヤーオブジェクトをデータ要素にマッピングする](layer-to-elements.md)：タグデータ要素について理解していること、操作するタグデータ要素が複数あることを確認します。

[ソリューションデザインドキュメントを作成する](../prepare/solution-design.md)：整理された状態を維持するには、ソリューションデザインドキュメントが不可欠です。ソリューションデザインドキュメントに従うと、データ要素を Analytics 変数へと簡単に割り当てることができます。

## データ要素を Analytics 変数に割り当てる

以下の手順に従った後にタグライブラリを公開すると、Analysis Workspace でカスタムディメンションを使用できます。Analytics 変数は、グローバルに設定することも、個々のルール内で設定することもできます。

### グローバル変数の設定

グローバル変数は、データ要素が存在するあらゆるページで変数値を設定する場合に最適です。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」をクリックします。
1. 「[!UICONTROL グローバル変数]」アコーディオンをクリックすると、グローバル変数を割り当てるインターフェイスが表示されます。

### ルール内での変数の設定

ルールで設定された変数は、すべてのページで変数を設定したくない場合に最適です。ルールで条件を定義します。Adobe Experience Platform タグに関するドキュメントの[ルール](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=ja)を参照してください。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブをクリックし、目的のルールをクリックします（または作成します）。
1. 「[!UICONTROL アクション]」の下の「[!UICONTROL 追加]」ボタンをクリックします。
1. を設定します。 [!UICONTROL 拡張] Adobe Analyticsのドロップダウンリスト、 [!UICONTROL アクションタイプ] を変数を設定します。
1. 目的の Analytics 変数の右側にある![データ要素](assets/data-element.png)アイコンをクリックします。組織の[ソリューションデザインドキュメント](../prepare/solution-design.md)には、使用する Analytics 変数が記載されています。
1. モーダルウィンドウで目的のデータ要素を選択します。「[!UICONTROL 選択]」をクリックします。
1. `%` 記号で囲まれたテキストフィールドに、データ要素名が追加されます。例えば、データ要素に「Page name」という名前を付けた場合、変数にデータ要素を割り当てると、文字列 `%Page name%` 表示されます。

>[!TIP]
>
> 同じ変数内のデータ要素を連結できます。例えば、「Hostname」データ要素と「Pathname」データ要素がある場合、`%Hostname%%Pathname%` を使用して、両方を 1 つの変数に組み合わせることができます。

## 次の手順

[ページ変数](../vars/page-vars/page-variables.md)：Analysis Workspace でディメンションを活用するために、実装で使用できるページレベルの変数について説明します。

[設定変数](../vars/config-vars/configuration-variables.md)：Adobe Analytics で他の機能のロックを解除するために、実装で使用できる設定変数について説明します。
