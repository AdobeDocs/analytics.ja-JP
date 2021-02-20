---
title: Launch データ要素を Analytics 変数にマッピングする
description: Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 100%

---


# Launch データ要素を Analytics 変数にマッピングする

Adobe Experience Platform Launch でデータ要素のリポジトリを取得したら、それらを Analytics ディメンションに割り当てることができます。

## 前提条件

[データレイヤーオブジェクトをデータ要素にマッピングする](layer-to-elements.md)：Launch のデータ要素について理解し、および操作するデータ要素が複数あることを確認します。

[ソリューションデザインドキュメントを作成する](../prepare/solution-design.md)：整理された状態を維持するには、ソリューションデザインドキュメントが不可欠です。ソリューションデザインドキュメントに従うと、データ要素を Analytics 変数へと簡単に割り当てることができます。

## データ要素を Analytics 変数に割り当てる

以下の手順に従った後に Launch でライブラリを公開すると、Analysis Workspace でカスタムディメンションを使用できます。Analytics 変数は、グローバルに設定することも、個々のルール内で設定することもできます。

### グローバル変数の設定

グローバル変数は、データ要素が存在するあらゆるページで変数値を設定する場合に最適です。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の Launch プロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」をクリックします。
1. 「[!UICONTROL グローバル変数]」アコーディオンをクリックすると、グローバル変数を割り当てるインターフェイスが表示されます。

### ルール内での変数の設定

ルールで設定された変数は、すべてのページで変数を設定したくない場合に最適です。ルールで条件を定義します。Adobe Experience Platform Launch ユーザーガイドの「[ルール](https://docs.adobe.com/content/help/ja-JP/launch/using/reference/manage-resources/rules.html)」を参照してください。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の Launch プロパティをクリックします。
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
