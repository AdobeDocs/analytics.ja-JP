---
description: 計算指標ページでは、指標を様々な方法で管理できます。例えば、共有、フィルタリング、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。
title: 計算指標マネージャー
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: cfae0661dfa9c61daea33c3a52204793ce3d35c1
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%

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
   | 使用場所 | 計算指標が現在使用されているコンポーネントの数を示します。 <p>例えば、計算指標が 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は次のように表示されます。 [!UICONTROL **42 個のコンポーネント**]. <p>この列の値を選択して、計算指標が使用されている場所の分類を確認します ( 例： [!UICONTROL **プロジェクト (40)**], [!UICONTROL **アラート (2)**]) をクリックします。</p><p>計算指標は、次のいずれかのコンポーネントタイプで使用できます。</p> <ul><li>アラート</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。</p><p>The [!UICONTROL **使用場所**] デフォルトでは、列は表示されません。 [列の設定](#configure-columns) をクリックして表示します。</p> |
   | 前回の使用 | 次のいずれかのコンポーネントタイプで計算指標が最後に使用された日付を表示します。 <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li></ul> <p>この情報は、コンポーネントが組織内のユーザーにとって有用かどうか、どこで使用されているか、削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この情報には、API、Report Builder、Data Warehouseの使用方法は含まれません。</p><p>以下を使用すると、 [データ辞書](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) お客様の組織でのコンポーネントの使用方法を追跡し、より深く理解するのに役立つこの情報と共に使用します。 |

   {style="table-layout:auto"}
