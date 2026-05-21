---
description: フィルターを適用してフォールアウトレポートを作成する手順について説明します。
title: リクエストウィザードを使用したフォールアウトレポートのフィルタリング
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
TQID: https://experienceleague.adobe.com/b-OBsmKfOFGtPK3Ar6pJtGUc3vZ4L2Jeei2sNK-7Npg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 77%

---

# リクエストウィザードを使用したフォールアウトレポートのフィルタリング

{{legacy-arb}}

フォールアウトレポートにフィルターを適用する手順について説明します。

次の例は、ページフォールアウトレポートを示しています。

1. Adobe Report Builder で「**[!UICONTROL 作成]**」をクリックして、リクエストウィザードを表示します。
1. 適切なレポートスイートを選択します。
1. 左側のツリービューで、**[!UICONTROL パス]**／**[!UICONTROL ページ]**／**[!UICONTROL ページのフォールアウト]**&#x200B;を選択します。

   Report Builder ディレクトリのWindows ツリービューを示す![&#x200B; スクリーンショット。 ページのフォールアウトが選択されています。](assets/page_fallout.png)

1. 適切な[日付範囲](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)を設定します。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. ウィザードの手順 2 の「**[!UICONTROL 行ラベル]**」で、「**[!UICONTROL チェックポイントの定義]**」リンクをクリックします （フォールアウトレポートでは、パターンが事前に適用されているパスレポートとは異なり、常にパス要素を定義する必要があります）。

   チェックポイントの定義リンクを示す![&#x200B; スクリーンショット。](assets/define_checkpoints.png)

1. 「**[!UICONTROL フィルター]**」オプションを選択します。

1. **[!UICONTROL サイトセクションフォールアウトチェックポイントの定義]**&#x200B;ダイアログボックスで、セルの範囲またはリストからチェックポイントを定義します。 「**[!UICONTROL OK]**」をクリックします。
1. セルの範囲またはリストのいずれから選択するかを決定します。
1. リストから選択する場合は、「**[!UICONTROL 追加]**」をクリックしてチェックポイントを選択し、フォールアウトパスに追加します。 3 ～ 8 件のチェックポイントを定義できます （利用可能な要素は、「**[!UICONTROL その他]**」をクリックすると検索できます）。

   フィルターの絞り込みについて詳しくは、[&#x200B; フィルターディメンション &#x200B;](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/filter-dimensions.md)を参照してください。

1. **[!UICONTROL 使用可能な要素]**&#x200B;を選択し、オレンジ色の矢印をクリックして、左側の列から右側に移動します。
1. 「**[!UICONTROL OK]**」を 3 回クリックして、「**[!UICONTROL 完了]**」をクリックします。

   レポートが更新されます。
