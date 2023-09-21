---
description: セグメントマネージャでは、セグメントを様々な方法で管理できます。例えば、共有、フィルターを適用、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。
title: セグメントの管理 (セグメントマネージャ)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: bd588a06546c59e9a5a61b0260229bafaba150f1
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 35%

---

# セグメントマネージャー

セグメントマネージャでは、セグメントを様々な方法で管理できます。例えば、共有、フィルターを適用、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。

Analytics セグメントマネージャには、自分が所有しているすべてのセグメントと、自分が共有しているセグメントが表示されます。管理者レベルのユーザーは、組織内のすべてのセグメントを表示できます。この概要では、セグメントマネージャのユーザーインターフェイスと機能について説明します。

![セグメントマネージャー](assets/segments-manager.png)

## セグメントマネージャへのアクセス

1. Adobe Analyticsで、 **[!UICONTROL コンポーネント]** 「 」タブで、「 **[!UICONTROL セグメント]**.

   または

   既存のレポートで、セグメントアイコンを選択します。 ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 左側のナビゲーションで、「 **[!UICONTROL 管理]**.

## セグメントマネージャで使用可能なアクション

セグメントマネージャでは、次の操作を実行できます。

* [セグメントのフィルタリング](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [セグメントのお気に入りへの登録](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [セグメントの承認](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [セグメントのタグ設定](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [セグメントの共有](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* セグメントを CSV ファイルに書き出します。

* [セグメントのコピー](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [セグメントの削除](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## 列の設定

表示する列を設定することで、セグメントマネージャでセグメントごとに表示される情報を設定できます。

セグメントマネージャで表示する列を設定するには：

1. Adobe Analyticsで、 **[!UICONTROL コンポーネント]** 「 」タブで、「 **[!UICONTROL セグメント]**.

1. セグメントマネージャで、 **列のカスタマイズ** アイコン ![列をカスタマイズアイコン](assets/customize-columns-icon.png)をクリックし、セグメントマネージャに表示する列を選択します。

   以下の列を表示できます。

   | 列のタイトル | 説明 |
   |---|---|
   | タイトルと説明 | これらの値は、セグメントビルダーで提供されます。 タイトルと説明を編集するには、タイトルリンクを選択して、セグメントビルダーを開きます。 |
   | お気に入り | 各セグメントの横に星形のアイコンが表示され、セグメントをお気に入りに登録できます。 詳しくは、 [セグメントのお気に入りへの登録](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | レポートスイート | この列には、セグメントが最後に保存されたレポートスイートが示されます。 |
   | 所有者 | セグメントの所有者が示されます。管理者以外のユーザーは、自分が所有しているまたは自分が共有していたセグメントのみを表示できます。 |
   | タグ（列の選択でチェックされていないので、列は表示されていません） | 自分または自分とセグメントを共有しているユーザーによってセグメントに適用されたタグ。 |
   | 共有先 | 自分がセグメントを共有している個人、グループまたは全員が表示されます。グループまたは全員を表示できるのは管理者のみです。 <p>セグメントが自分と共有されているとき、または自分と共有されているときに、セグメント名の横に共有アイコンが表示されます。</p> |
   | 変更日 | セグメントが最後に修正された日付を表示します。 |
   | 使用場所 | **注意：** この機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsのリリース手順については、 [Adobe Analyticsの機能リリース](/help/release-notes/releases.md).<p>セグメントが現在使用されているコンポーネントの数を示します。 <p>例えば、セグメントが 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は次のように表示されます。 [!UICONTROL **42 個のコンポーネント**].</p> <p>この列の値を選択して、セグメントが使用されている場所の分類を表示します ( 例： [!UICONTROL **プロジェクト (40)**], [!UICONTROL **アラート (2)**]) をクリックします。</p><p>セグメントは、次のいずれかのコンポーネントタイプで使用できます。</p> <ul><li>アラート</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li><li>計算指標</li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、および削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。</p><p>The [!UICONTROL **使用場所**] デフォルトでは、列は表示されません。 [列の設定](#configure-columns) をクリックして表示します。</p> |
   | 前回の使用 | **注意：** この機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsのリリース手順については、 [Adobe Analyticsの機能リリース](/help/release-notes/releases.md).<p>次のいずれかのコンポーネントタイプでセグメントが最後に使用された日付を表示します。</p> <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li><li>セグメント</li></ul> <p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、および削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。 |

   {style="table-layout:auto"}

## ハウツービデオ {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

この [Adobe Analytics の ビデオ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=ja)では、セグメントマネージャの使用方法の概要を説明しています。


