---
description: アラートを管理.
title: アラートマネージャーの概要
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 69b763bc5740223be54309c0c0b98f40536c4d7e
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 33%

---

# アラートマネージャー

アラートマネージャーは、 [セグメントマネージャ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja) そして [計算指標マネージャ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja).

![](assets/alert-manager.png)

## アラートマネージャーへのアクセス

1. Adobe Analyticsで、 [!UICONTROL **コンポーネント**] > [!UICONTROL **アラート**].

## アラートマネージャで使用可能なアクション

アラートマネージャでは、次の操作を実行できます。

* 「**[!UICONTROL + 追加]**」をクリックすると、アラートビルダーにアクセスします。
* アラートのタグ付け。これにより、アラートを使いやすく整理できます。
* アラートの削除。
* アラートの名前の変更。
* アラートの承認。
* アラートのコピー。
* アラートの有効化／無効化。
* アラートの有効期限の&#x200B;**更新**。1 つまたは複数のアラートが選択されている場合、「**[!UICONTROL 更新]**」をクリックすることで更新できます。これにより、元の有効期限にかかわらず、「**[!UICONTROL 更新]**」がクリックされた日から 1 年先に有効期限が延長されます。
* アラートの .CSV ファイルへの書き出し。
* アラートタイトルのダブルクリックによるアラートの編集。
* アラートの検索。
* 他のレポートスイートへのアラートの追加。
* アラートの所有者の指定／変更。
* 他のフィルターの追加。
* アラートの&#x200B;**有効期限**&#x200B;の定義。

## 列の設定

アラートマネージャで、各アラートに対して表示される情報を構成するには、表示する列を構成します。

アラート・マネージャで表示される列を構成するには、次の手順に従います。

1. Adobe Analyticsで、 **[!UICONTROL コンポーネント]** 「 」タブで、「 **[!UICONTROL アラート]**.

1. アラートマネージャーで、 **列のカスタマイズ** アイコン ![列をカスタマイズアイコン](assets/customize-columns-icon.png)をクリックし、アラートマネージャーに表示する列を選択します。

   以下の列を表示できます。

   | 列のタイトル | 説明 |
   |---|---|
   | お気に入り | 各アラートの横に星形のアイコンが表示され、アラートをお気に入りに登録できます。 <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | タイトルと説明 | これらの値は、アラートビルダーで提供されます。 タイトルと説明を編集するには、タイトルリンクを選択してアラートビルダーを開きます。 |
   | レポートスイート | アラートが最後に保存されたレポートスイートを示します。 |
   | 所有者 | アラートの所有者を示します。 管理者以外のユーザーは、自分が所有しているまたは自分が共有していたアラートのみを表示できます。 |
   | タグ | 自分または自分とアラートを共有しているユーザーによってアラートに適用されたタグが表示されます。 |
   | 共有先 | 自分がアラートを共有している個人、グループ（管理者のみ）、または全員（管理者のみ）が表示されます。 |
   | 変更日 | アラートが最後に変更された日付を示します。 |
   | 前回の使用 | **注意：** この機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsのリリース手順については、 [Adobe Analyticsの機能リリース](/help/release-notes/releases.md).<p>アラートが最後に使用された日付を表示します。</p> <p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、および削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p> |

   {style="table-layout:auto"}
