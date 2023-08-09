---
description: フィルターを適用してフォールアウトレポートを作成する手順について説明します。
title: リクエストウィザードを使用したフォールアウトレポートのフィルタリング
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 91%

---

# リクエストウィザードを使用したフォールアウトレポートのフィルタリング

フォールアウトレポートにフィルターを適用する手順について説明します。

この例では、ページのフォールアウトレポートを示します。

1. Adobe Report Builder で「**[!UICONTROL 作成]**」をクリックして、リクエストウィザードを表示します。
1. 適切なレポートスイートを選択します。
1. 左側のツリービューで、**[!UICONTROL パス]**／**[!UICONTROL ページ]**／**[!UICONTROL ページのフォールアウト]**&#x200B;を選択します。

   ![Report Builder・ディレクトリの Windows ツリー・ビューを示すスクリーンショット。 ページのフォールアウトが選択されています。](assets/page_fallout.png)

1. 適切な[日付範囲](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を設定します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. ウィザードの手順 2 の「**[!UICONTROL 行ラベル]**」で、「**[!UICONTROL チェックポイントの定義]**」リンクをクリックします（フォールアウトレポートでは、パターンが事前に適用されているパスレポートとは異なり、常にパスエレメントを定義する必要があります）。

   ![「チェックポイントの定義」リンクを示すスクリーンショット。](assets/define_checkpoints.png)

1. 「**[!UICONTROL フィルター]**」オプションを選択します。

1. **[!UICONTROL サイトセクションフォールアウトチェックポイントの定義]**&#x200B;ダイアログボックスで、セルの範囲またはリストからチェックポイントを定義します。「**[!UICONTROL OK]**」をクリックします。
1. セルの範囲またはリストのいずれから選択するかを決定します。
1. リストから選択する場合は、「**[!UICONTROL 追加]**」をクリックしてチェックポイントを選択し、フォールアウトパスに追加します。3 ～ 8 件のチェックポイントを定義できます（利用可能なエレメントは、「**[!UICONTROL その他]**」をクリックすると検索できます）。

   フィルターの絞り込みについて詳しくは、[フィルターディメンション](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md)を参照してください。1. 左の列の「**[!UICONTROL 使用可能なエレメント]**」から選択し、オレンジ色の矢印をクリックして、右側に移動します。
1. 「**[!UICONTROL OK]**」を 3 回クリックして、「**[!UICONTROL 完了]**」をクリックします。

   レポートが更新されます。
