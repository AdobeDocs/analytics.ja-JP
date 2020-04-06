---
description: 仮想レポートスイートは、コンポーネントを含めたり除外したりするようにキュレーションできます。分析ワークスペース。
title: 仮想レポートスイートコンポーネントのキュレーション
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 仮想レポートスイートコンポーネントのキュレーション

仮想レポートスイートは、コンポーネントを含めたり除外したりするようにキュレーションできます。分析ワークスペース。

>[!NOTE]キュレーションされた Workspace プロジェクトおよびキュレーションされた仮想レポートスイート（VRS）で、管理者および非管理者が表示できるコンポーネントに対して変更が加えられました。以前は、キュレーションされていないコンポーネントは、をクリックすると誰でも表示できまし **[!UICONTROL Show all Components]**&#x200B;た。 The [updated curation experience](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/curate-projects-vrs.html) allows for more fine-grained control over which components are visible.

コンポーネントのキュレーションを有効にするには、次の手順に従います。

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. を定義したら、 **[!UICONTROL Settings]**&#x200B;タブをクリック **[!UICONTROL Components]** します。

1. チェックボックスを選択しま **[!UICONTROL Enable Customization of Virtual Report Suite Components]**&#x200B;す。

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >コンポーネントのカスタマイズが有効になっている場合、仮想レポートスイートは **Analysis Workspace からのみ**&#x200B;アクセスでき、次の場所からはアクセスできません。

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * Analytics レポート API
   チェックすると、仮想レポートスイートに含めるコンポーネントを追加できます。追加するには、該当するコンポーネントを「除外されたコンポーネント」列から「含まれるコンポーネント」列にドラッグします。 含めたり除外したりできるコンポーネントは次のとおりです。

   * ディメンション
   * 指標
   * セグメント
   * 日付範囲
   >[!NOTE]
   >
   >キュレートされたコンポーネント（セグメント、計算指標、日付範囲）を&#x200B;*共有*&#x200B;する必要はありません。共有されていなくても、仮想レポートスイート用にキュレートされている場合は、Analysis Workspace で常に表示されます。

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## コンポーネントの名前の変更 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

仮想レポートスイートに固有の、含まれるコンポーネントの表示名を変更できます。 例えば、仮想レポートスイートにページ名を含め、モバイルに適したコンテキストに名前を変更する場合は、アプリ画面に変更できます。 この仮想レポートスイートが使用されると、分析ワークスペースに新しい名前が表示されます。

![](assets/vrs-rename-component.png)

分析ワークスペースで、含まれる任意のコンポーネントの情報アイコンをクリックし、名前を変更したコンポーネントの元の名前を表示します。

![](assets/vrs-aw-renamed.png)

## コンポーネントグループ {#section_483BEC76F49E46ADAAA03F0A12E48426}

コンポーネントグループを使用して、一括コンポーネントを仮想レポートスイートに追加します。 例えば、モバイルアプリ分析に固有のデフォルトのコンポーネントセットを読み込む場合は、モバイルアプリグループを選択します。 対応するディメンションと指標のセット（既に名前が変更されています）が、仮想レポートスイートに自動的に追加されます。リスト。

![](assets/vrs-comp-grp.png)

## Workspace の動作 {#section_6C32F8B642804C0097FCB14E21028D4A}

Analysis Workspace のキュレーションについて詳しくは、[プロジェクトのキュレーションおよび共有](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/curate.html)を参照してください。
