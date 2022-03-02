---
title: データレイヤーオブジェクトをデータ要素にマッピングする
description: データレイヤーから読み取るようにタグを設定します。
feature: Launch Implementation
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 100%

---

# データレイヤーオブジェクトをデータ要素にマッピングする

組織がデータレイヤーを確立してサイトに実装したら、タグ内のデータ要素にデータレイヤーオブジェクトをマッピングできます。

## 前提条件

[データレイヤーを作成する](../prepare/data-layer.md)：サイトにデータレイヤーが存在することを確認します。技術的には、任意の JavaScript オブジェクトをマッピングしたり、CSS 要素をページから直接削除したりできますが、アドビではこの方法を最後の手段として使用することをお勧めします。サイトのレイアウトが変更されると、タグで使用される CSS セレクターの動作が停止し、データが失われます。

## タグを使用したデータ要素の作成

[データ要素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=ja)は、ツール全体で使用できるデータ収集 UI のコンポーネントです。データ要素を使用して、Adobe Analytics 拡張機能で変数の値を割り当てることができます。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「**[!UICONTROL データ要素]**」タブをクリックしてから、「**[!UICONTROL データ要素の追加]**」をクリックします。

   ![データ要素の作成](assets/createelement.png)

1. データ要素の名前を入力します。追跡するデータレイヤーの JavaScript 変数に対応する単純なラベルを指定できます。
1. **[!UICONTROL 拡張機能]**&#x200B;ドロップダウンで、「**[!UICONTROL コア]**」を選択します。
1. **[!UICONTROL データ要素の種類]**&#x200B;で、「**[!UICONTROL JavaScript 変数]**」を選択します。右側にテキストフィールドが表示され、このデータ要素にマッピングする JavaScript 変数を入力できます。
1. （通常はデータレイヤー内で）目的の JavaScript 変数を入力します。例えば、組織のデータレイヤーがアドビの推奨プラクティスと密接に一致する場合、値は `digitalData.page.pageInfo.pageName` になります。ブラウザーのコンソールを使用して、JavaScript 変数の構文と値を検証できます。
1. 「**[!UICONTROL 保存]**」をクリックします。

## 次の手順

[Launch データ要素を Analytics 変数にマッピングする](elements-to-variable.md)：Analytics 変数にデータ要素を割り当てて、Analysis Workspace でディメンションとして使用できるようにします。
