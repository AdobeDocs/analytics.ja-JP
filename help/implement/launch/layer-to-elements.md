---
title: データレイヤーオブジェクトをデータ要素にマッピングする
description: データレイヤーから読み取るタグを設定します。
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 60%

---

# データレイヤーオブジェクトをデータ要素にマッピングする

組織がデータレイヤーを確立し、サイトに実装したら、タグ内のデータ要素にデータレイヤーオブジェクトをマッピングできます。

>[!NOTE]
>Adobe Experience Platform Launchは、Experience Platformのデータ収集テクノロジーのスイートとしてリブランドされました。 その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。 用語の変更点の一覧については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

## 前提条件

[データレイヤーを作成する](../prepare/data-layer.md)：サイトにデータレイヤーが存在することを確認します。技術的には、任意の JavaScript オブジェクトをマッピングしたり、CSS 要素をページから直接削除したりできますが、アドビではこの方法を最後の手段として使用することをお勧めします。サイトのレイアウトが変更されると、タグで使用されるCSSセレクターが機能しなくなり、データが失われます。

## タグを使用したデータ要素の作成

[データ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) 要素は、データ収集UIのコンポーネントで、ツール全体で使用できます。データ要素を使用して、Adobe Analytics 拡張機能で変数の値を割り当てることができます。

1. [experience.adobe.com](https://experience.adobe.com)に移動し、プロンプトが表示されたらログインします。
1. **[!UICONTROL Launch /データ収集]**&#x200B;を選択します。
1. 「**[!UICONTROL Launch /データ収集に移動]**」をクリックし、「**[!UICONTROL タグ]**」を選択します。
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
