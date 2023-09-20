---
description: 計算指標ページでは、指標を様々な方法で管理できます。例えば、共有、フィルタリング、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。
title: 計算指標マネージャー
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: 637f498c8abee0f3c83780bccd0447f2e3a804e3
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 12%

---

# 計算指標マネージャー

計算指標ページでは、指標を様々な方法で管理できます。例えば、共有、フィルタリング、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。

計算指標ページには、自分が所有しているすべてのセグメントと、自分が共有しているセグメントが表示されます。 管理者レベルのユーザーは、組織内のすべてのカスタム指標を表示できます。

<!-- add screenshot -->

## 計算指標マネージャへのアクセス

1. Adobe Analyticsで、 [!UICONTROL **コンポーネント**] > [!UICONTROL **計算指標**].

## 計算指標マネージャで使用可能なアクション

計算指標マネージャでは、次の操作を実行できます。

* [計算指標へのフィルター設定](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [計算指標のお気に入りへの登録](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [計算指標の承認](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [計算指標のタグ付け](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [計算指標の共有](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* 計算指標を CSV ファイルに書き出します。

* [計算指標のコピー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* 計算指標の削除

## 列の設定

計算指標マネージャで、各計算指標に対して表示される情報を設定するには、表示する列を設定します。

計算指標マネージャで表示する列を設定するには：

1. Adobe Analyticsで、 **[!UICONTROL コンポーネント]** 「 」タブで、「 **[!UICONTROL 計算指標]**.

1. 計算指標マネージャで、 **列のカスタマイズ** アイコン ![列をカスタマイズアイコン](assets/customize-columns-icon.png)をクリックし、計算指標マネージャーに表示する列を選択します。

   以下の列を表示できます。

   | 列のタイトル | 説明 |
   |---|---|
   | お気に入り | 各計算指標の横に星形のアイコンが表示され、計算指標をお気に入りに登録できます。 詳しくは、 [計算指標のお気に入りへの登録](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | タイトルと説明 | これらの値は、計算指標ビルダーで提供されます。 タイトルと説明を編集するには、タイトルリンクを選択して、計算指標ビルダーを開きます。 |
   | レポートスイート | 指標が最後に保存されたレポートスイートを示します。 |
   | 所有者 | カスタム指標の所有者を示します。管理者以外のユーザーは、自分が所有しているまたは自分が共有していた指標のみを表示できます。 |
   | タグ | 自分または自分と計算指標を共有しているユーザーによって指標に適用されたタグが表示されます。 |
   | 共有先 | 計算指標を共有している個人、グループ（管理者のみ）、またはすべて（管理者のみ）が表示されます。 <p>計算指標が共有されているときは、計算指標名の横に共有アイコンが表示されます。</p> |
   | 変更日 | カスタム指標が最後に変更された日付を示します。 |
   | 使用場所 | **注意：** この機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsのリリース手順については、 [Customer Journey Analytics機能リリース](/help/release-notes/releases.md).<p>計算指標が現在使用されている次のコンポーネントタイプを示します。</p> <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li></ul> 例えば、コンポーネントが 40 個のプロジェクトで使用され、2 個のアラートで使用されている場合、この列にはが表示されます [!UICONTROL **アラート (2)、プロジェクト (40)**]. <p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、または削除する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。 |
   | 前回の使用 | **注意：** この機能は、リリースの制限付きテスト段階にあり、お使いの環境ではまだ使用できない可能性があります。 機能が一般に利用できるようになったら、このメモは削除されます。Customer Journey Analyticsのリリース手順については、 [Customer Journey Analytics機能リリース](/help/release-notes/releases.md).<p>次のいずれかのコンポーネントタイプで計算指標が最後に使用された日付を表示します。</p> <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li></ul> <p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、または削除する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。 |

   {style="table-layout:auto"}
