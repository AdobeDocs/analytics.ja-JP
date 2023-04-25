---
title: データレイヤーオブジェクトをデータ要素にマッピングする
description: データレイヤーから読み取るようにタグを設定します。
feature: Launch Implementation
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 94%

---

# データレイヤーオブジェクトをデータ要素にマッピングする

組織がデータレイヤーを確立してサイトに実装したら、タグ内のデータ要素にデータレイヤーオブジェクトをマッピングできます。

## 前提条件

[データレイヤーを作成する](../prepare/data-layer.md)：サイトにデータレイヤーが存在することを確認します。技術的には、任意の JavaScript オブジェクトをマッピングしたり、CSS 要素をページから直接削除したりできますが、アドビではこの方法を最後の手段として使用することをお勧めします。サイトのレイアウトが変更されると、タグで使用される CSS セレクターの動作が停止し、データが失われます。

## タグを使用したデータ要素の作成

[データ要素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=ja)は、ツール全体で使用できる Adobe Experience Platform データ収集のコンポーネントです。データ要素を使用して、Adobe Analytics 拡張機能で変数の値を割り当てることができます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「**[!UICONTROL データ要素]**」タブをクリックしてから、「**[!UICONTROL データ要素の追加]**」をクリックします。

   ![データ要素の作成](assets/createelement.png)

1. データ要素の名前を入力します。追跡するデータレイヤーの JavaScript 変数に対応する単純なラベルを指定できます。
1. 以下 **[!UICONTROL 拡張]** ドロップダウンリストで、「 **[!UICONTROL コア]**.
1. 以下 **[!UICONTROL データ要素タイプ]** ドロップダウンリストで、「 **[!UICONTROL JavaScript 変数]**. 右側にテキストフィールドが表示され、このデータ要素にマッピングする JavaScript 変数を入力できます。
1. （通常はデータレイヤー内で）目的の JavaScript 変数を入力します。例えば、組織のデータレイヤーがアドビの推奨プラクティスと密接に一致する場合、値は `digitalData.page.pageInfo.pageName` になります。ブラウザーのコンソールを使用して、JavaScript 変数の構文と値を検証できます。
1. 「**[!UICONTROL 保存]**」をクリックします。

## 次の手順

[Launch データ要素を Analytics 変数にマッピングする](elements-to-variable.md)：Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
