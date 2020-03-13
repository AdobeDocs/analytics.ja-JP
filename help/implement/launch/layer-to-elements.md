---
title: データレイヤーオブジェクトのデータ要素へのマッピング
description: データレイヤーから読み取るように「起動」を設定します。
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# データレイヤーオブジェクトのデータ要素へのマッピング

組織がサイトにデータレイヤーを確立し、実装したら、「起動」内のデータ要素にデータレイヤーオブジェクトをマップできます。

## 前提条件

[データレイヤーの作成](../prepare/data-layer.md):データレイヤーがサイト上に存在することを確認します。 技術的には任意のJavaScriptオブジェクトをマップしたり、CSS要素をページから直接削除したりできますが、アドビではこの方法を最後の手段としてお勧めします。 サイトのレイアウトが変更されると、「起動」で使用されるCSSセレクターが機能しなくなり、データが失われます。

## Adobe Experience Platform Launchを使用したデータ要素の作成

[データ要素は](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) 、ツール全体で使用できる起動のコンポーネントです。 データ要素を使用して、Adobe Analytics拡張機能で変数値を割り当てることができます。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 目的の「起動」プロパティをクリックします。
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![データ要素を作成する](assets/createelement.png)

1. データ要素の名前を入力します。 追跡するデータレイヤー内のJavaScript変数に対応する単純なラベルを指定できます。
1. ドロップダウ [!UICONTROL Extension] ンで、を選択しま [!UICONTROL Core]す。
1. ドロップダウ [!UICONTROL Data Element Type] ンで、を選択しま [!UICONTROL JavaScript Variable]す。 右側にテキストフィールドが表示され、このテキストフィールドを使用してJavaScript変数を入力し、このデータ要素にマッピングできます。
1. 目的のJavaScript変数を入力します（通常はデータレイヤー内）。 例えば、組織のデータレイヤーがアドビの推奨プラクティスと密接に一致する場合、値は次のようになりま `digitalData.page.pageInfo.pageName`す。 ブラウザーのコンソールを使用して、JavaScript変数の構文と値を検証できます。
1. クリック [!UICONTROL Save].

## 次の手順

[データ要素のAnalytics変数へのマッピング](elements-to-variable.md):Analytics変数にデータ要素を割り当てて、Analysis Workspaceでディメンションとして使用できるようにします。
