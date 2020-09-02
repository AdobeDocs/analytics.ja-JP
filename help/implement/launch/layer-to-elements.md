---
title: データレイヤーオブジェクトをデータ要素にマッピングする
description: データレイヤーから読み取るよう Launch を設定します。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 100%

---


# データレイヤーオブジェクトをデータ要素にマッピングする

組織がデータレイヤーを確立し、サイトに実装したら、Launch 内のデータ要素にデータレイヤーオブジェクトをマッピングできます。

## 前提条件

[データレイヤーを作成する](../prepare/data-layer.md)：サイトにデータレイヤーが存在することを確認します。技術的には、任意の JavaScript オブジェクトをマッピングしたり、CSS 要素をページから直接削除したりできますが、アドビではこの方法を最後の手段として使用することをお勧めします。サイトのレイアウトが変更されると、Launch で使用される CSS セレクターの動作が停止し、データが失われます。

## Adobe Experience Platform Launch を使用してデータ要素を作成する

[データ要素](https://docs.adobe.com/content/help/ja-JP/launch/using/reference/manage-resources/data-elements.html#create-a-data-element)は、ツール全体で使用できる Launch のコンポーネントです。データ要素を使用して、Adobe Analytics 拡張機能で変数の値を割り当てることができます。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の Launch プロパティをクリックします。
1. 「**[!UICONTROL データ要素]**」タブをクリックしてから、「**[!UICONTROL データ要素の追加]**」をクリックします。

   ![データ要素の作成](assets/createelement.png)

1. データ要素の名前を入力します。追跡するデータレイヤーの JavaScript 変数に対応する単純なラベルを指定できます。
1. **[!UICONTROL 拡張機能]**&#x200B;ドロップダウンで、「**[!UICONTROL コア]**」を選択します。
1. **[!UICONTROL データ要素の種類]**&#x200B;で、「**[!UICONTROL JavaScript 変数]**」を選択します。右側にテキストフィールドが表示され、このデータ要素にマッピングする JavaScript 変数を入力できます。
1. （通常はデータレイヤー内で）目的の JavaScript 変数を入力します。例えば、組織のデータレイヤーがアドビの推奨プラクティスと密接に一致する場合、値は `digitalData.page.pageInfo.pageName` になります。ブラウザーのコンソールを使用して、JavaScript 変数の構文と値を検証できます。
1. 「**[!UICONTROL 保存]**」をクリックします。

## 次の手順

[Launch データ要素を Analytics 変数にマッピングする](elements-to-variable.md)：Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
