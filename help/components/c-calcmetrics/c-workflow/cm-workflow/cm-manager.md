---
description: 計算指標ページでは、共有、フィルタリング、タグ付け、承認、コピー、削除、お気に入りとしてマークするなど、指標をキュレーションする様々な方法を提供します。
title: 計算指標マネージャー
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 9%

---

# 計算指標マネージャー

計算指標ページでは、共有、フィルタリング、タグ付け、承認、コピー、削除、お気に入りとしてマークするなど、指標をキュレーションする様々な方法を提供します。

計算指標ページには、自分が所有し、自分と共有されているすべてのセグメントが表示されます。 管理者レベルのユーザーは、組織内のすべてのカスタム指標を表示できます。

<!-- add screenshot -->

## 計算指標マネージャーへのアクセス

1. Adobe Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **計算指標**] を選択します。

## 計算指標マネージャーで使用可能なアクション

計算指標マネージャーでは、次の操作を実行できます。

* [計算指標をフィルタリング](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [計算指標をお気に入りに登録](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [計算指標の承認](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [計算指標をタグ付け](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [計算指標の共有](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* 計算指標を CSV ファイルにエクスポートします。

* [計算指標をコピー](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* 計算指標の削除

## 列の設定

表示される列を設定することで、計算指標マネージャーで各計算指標に表示される情報を設定できます。

計算指標マネージャーに表示される列を設定するには：

1. Adobe Analyticsで、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL 計算指標]**」を選択します。

1. 計算指標マネージャーで「**列をカスタマイズ**」アイコン ![ 列をカスタマイズ」アイコン ](assets/customize-columns-icon.png) を選択し、計算指標マネージャーに表示する列を選択します。

   次の列を表示できます。

   | 列タイトル | 説明 |
   |---|---|
   | お気に入り | 各計算指標の横に星形アイコンが表示され、計算指標をお気に入りとしてマークできます。 詳しくは、[ 計算指標をお気に入りとしてマーク ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md) を参照してください。 |
   | タイトルと説明 | これらの値は、計算指標ビルダーで指定されます。 タイトルと説明を編集するには、タイトルリンクを選択して計算指標ビルダーを開きます。 |
   | レポートスイート | 最後に指標を保存したレポートスイートを示します。 |
   | 所有者 | カスタム指標の所有者を示します。管理者以外のユーザーには、自分が所有している指標または自分と共有されていた指標のみが表示されます。 |
   | タグ | 自分または自分と計算指標を共有したユーザーが指標に適用したタグを表示します。 |
   | 共有先 | 計算指標を共有した個人またはグループ（管理者のみ）またはすべて（管理者のみ）をリストします。 <p>計算指標を共有すると、計算指標名の横に共有アイコンが表示されます。</p> |
   | 変更日 | カスタム指標が最後に変更された日付を示します。 |
   | 使用場所 | 計算指標が現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、計算指標が 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 components**] と表示されます。 <p>この列の値を選択すると、計算指標が使用されている場所（例：[!UICONTROL **プロジェクト （40）**]、[!UICONTROL **アラート （2）**]）の分類が表示されます。 さらに、計算指標が使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、「[!UICONTROL **プロジェクト （40）**]」リンクを選択します。</p><p>次の各領域には、その領域で使用されている計算指標のインスタンス数が表示されます。</p> <ul><li>[!UICONTROL **プロジェクト**]<p>[ 計算指標ビルダーで作成 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) された計算指標が含まれ、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイック計算指標として作成 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) された計算指標が含まれ、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **アラート**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder名</li><li>最終アクセス日</li><li>最終アクセス日の IMS ユーザー ID</li><li>最終アクセス日のユーザー名</li></ul><p>Report Builder情報をご覧いただく場合、2024 年 9 月より利用案内をご利用いただけます。</p></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**] 列はデフォルトでは表示されません。 [ 列を設定 ](#configure-columns) して表示します。</li><li>計算指標の定義に別の計算指標が含まれている場合、その計算指標の使用は [!UICONTROL **使用**] 列に表示されません。 計算指標が別のタイプのコンポーネント（セグメントなど）の定義に含まれている場合、その使用状況は [!UICONTROL **使用**] 列に表示されます。</li><li>この情報には、API またはData Warehouseからの使用は含まれません。</li><li>この列に特定のコンポーネントに関するデータがないが、そのデータに [!UICONTROL **前回の使用**] 日付が含まれている場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に [ データ要素 ](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。</p> |
   | 前回の使用 | 計算指標が次のいずれかの領域で最後に使用された日付を表示します。 <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li></ul> <p>この情報は、コンポーネントが組織内のユーザーにとって価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報には、API、Report Builder、Data Warehouseからの使用は含まれません。</li><li>一部のコンポーネントでは、2023 年 9 月より前にコンポーネントが最後に使用されていた場合、この列にデータが含まれないことがあります。</li><li>この情報は、システム管理者のみが使用できます。</li></ul><p>この情報と共に [ データ要素 ](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。 |

   {style="table-layout:auto"}
