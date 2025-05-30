---
description: 仮想レポートスイートをキュレートして、Analysis Workspace で利用可能なコンポーネントを限定できます。
title: 仮想レポートスイートコンポーネントのキュレーション
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 92%

---

# 仮想レポートスイートコンポーネントのキュレーション

仮想レポートスイートをキュレートして、Analysis Workspace で利用可能なコンポーネントを限定できます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Component curation](https://video.tv.adobe.com/v/3425530?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!NOTE]
>
>キュレーションされた Workspace プロジェクトおよびキュレーションされた仮想レポートスイートで、管理者および非管理者が表示できるコンポーネントに対して変更が加えられました。以前は、「**[!UICONTROL すべてのコンポーネントを表示]**」ボタンをクリックすることで、誰でもキュレーションされていないコンポーネントを表示できました。[更新されたキュレーション機能](/help/analyze/analysis-workspace/curate-share/curate.md)により、どのコンポーネントを表示できるかをより詳細に制御できます。

コンポーネントのキュレーションを有効にするには、次の手順に従います。

1. **[!UICONTROL Analytics]**/**[!UICONTROL コンポーネント]**/**[!UICONTROL 仮想レポートスイート]**/**[!UICONTROL 新しい仮想レポートスイートの作成]** に移動します。
1. **[!UICONTROL 設定]**&#x200B;を定義したら、「**[!UICONTROL コンポーネント]**」タブをクリックします。

1. 「**[!UICONTROL 仮想レポートスイートコンポーネントのカスタマイズを有効にする]**」チェックボックスを選択します。

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >コンポーネントのカスタマイズが有効になっている場合、仮想レポートスイートは **Analysis Workspace からのみ**&#x200B;アクセスでき、次の場所からはアクセスできません。
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* Analytics レポート API

   このチェックボックスを選択した後は、「除外されたコンポーネント」列から「含まれるコンポーネント」列にコンポーネントをドラッグすることで、任意のコンポーネントを仮想レポートスイートに追加できます。仮想レポートスイートに含めるかどうかを選択できるコンポーネントは次のとおりです。

   * ディメンション
   * 指標
   * セグメント
   * 日付範囲

   >[!NOTE]
   >
   >キュレートされたコンポーネント（セグメント、計算指標、日付範囲）を&#x200B;*共有*&#x200B;する必要はありません。共有されていなくても、仮想レポートスイート用にキュレートされている場合は、Analysis Workspace で常に表示されます。

1. コンポーネントにフィルターを適用するかコンポーネントの検索を実行して「**[!UICONTROL すべてを追加]**」をクリックすると、選択されたすべてのコンポーネントが「含む」列に追加されます。

   ![](assets/vrs-add-all.png)

## コンポーネントの名前の変更 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

仮想レポートスイートに含まれるコンポーネントの表示名はレポートスイートごとに固有の名前に変更できます。例えば、仮想レポートスイートに「ページ名」を含めるときに、モバイルのコンテキストに応じてコンポーネント名に変更する必要がある場合は、この名前を「アプリ画面」などに変更できます。新しい名前はこの仮想レポートスイートが使用されるたびに Analysis Workspace に表示されます。

![](assets/vrs-rename-component.png)

Analysis Workspace でコンポーネント名の横にある情報アイコンをクリックすると、変更前のコンポーネント名が表示されます。

![](assets/vrs-aw-renamed.png)

## コンポーネントグループ {#section_483BEC76F49E46ADAAA03F0A12E48426}

仮想レポートスイートに一括でコンポーネントを追加するには、コンポーネントグループを使用します。例えば、モバイルアプリ分析で使用するデフォルトのコンポーネントセットをインポートするには、モバイルアプリグループを選択します。対応する一連のディメンションと指標が（既に名前が変更された状態で）自動的に仮想レポートスイートの「含む」リストに追加されます。

![](assets/vrs-comp-grp.png)

## Workspace の動作 {#section_6C32F8B642804C0097FCB14E21028D4A}

Analysis Workspace のキュレーションについて詳しくは、[プロジェクトのキュレーションおよび共有](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=ja)を参照してください。
