---
description: フィルターを適用してフォールアウトレポートを作成する手順について説明します。
title: リクエストウィザードを使用したフォールアウトレポートのフィルタリング
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 80%

---

# リクエストウィザードを使用したフォールアウトレポートのフィルタリング

{{legacy-arb}}

フォールアウトレポートにフィルターを適用する手順について説明します。

この例では、ページのフォールアウトレポートを示します。

1. Adobe Report Builder で「**[!UICONTROL 作成]**」をクリックして、リクエストウィザードを表示します。
1. 適切なレポートスイートを選択します。
1. 左側のツリービューで、**[!UICONTROL パス]**／**[!UICONTROL ページ]**／**[!UICONTROL ページのフォールアウト]**&#x200B;を選択します。

   ![Report Builder ディレクトリの Windows ツリービューを示すスクリーンショット。 ページフォールアウトが選択されている。](assets/page_fallout.png)

1. 適切な[日付範囲](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)を設定します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. ウィザードの手順 2 の「**[!UICONTROL 行ラベル]**」で、「**[!UICONTROL チェックポイントの定義]**」リンクをクリックします（フォールアウトレポートでは、パターンが事前に適用されているパスレポートとは異なり、常にパス要素を定義する必要があります）。

   ![ チェックポイントを定義リンクを示すスクリーンショット。](assets/define_checkpoints.png)

1. 「**[!UICONTROL フィルター]**」オプションを選択します。

1. **[!UICONTROL サイトセクションフォールアウトチェックポイントの定義]**&#x200B;ダイアログボックスで、セルの範囲またはリストからチェックポイントを定義します。「**[!UICONTROL OK]**」をクリックします。
1. セルの範囲またはリストのいずれから選択するかを決定します。
1. リストから選択する場合は、「**[!UICONTROL 追加]**」をクリックしてチェックポイントを選択し、フォールアウトパスに追加します。3 ～ 8 件のチェックポイントを定義できます（利用可能な要素は、「**[!UICONTROL その他]**」をクリックすると検索できます）。

   フィルターの絞り込みについて詳しくは、[ ディメンションのフィルター ](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/filter-dimensions.md) を参照してください。

1. 左の列から選択してオレンジ色の矢印をクリックして、**[!UICONTROL 使用可能な要素]** を右に移動します。
1. 「**[!UICONTROL OK]**」を 3 回クリックして、「**[!UICONTROL 完了]**」をクリックします。

   レポートが更新されます。
