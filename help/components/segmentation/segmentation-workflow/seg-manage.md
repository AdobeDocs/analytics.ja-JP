---
description: セグメントマネージャでは、セグメントを様々な方法で管理できます。例えば、共有、フィルターを適用、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。
title: セグメントの管理（セグメントマネージャー）
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 27%

---

# セグメントマネージャー

セグメントマネージャでは、セグメントを様々な方法で管理できます。例えば、共有、フィルターを適用、タグ付け、承認、コピー、削除およびお気に入りへの登録が可能です。

Analytics セグメントマネージャには、自分が所有しているすべてのセグメントと、自分が共有しているセグメントが表示されます。管理者レベルのユーザーは、組織内のすべてのセグメントを表示できます。この概要では、セグメントマネージャーのユーザーインターフェイスと機能を説明します。

![ セグメントマネージャー ](assets/segments-manager.png)

## セグメントマネージャーへのアクセス

1. Adobe Analyticsで、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL セグメント]**」を選択します。

   または

   既存のレポートで、左側のナビゲーション ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) にあるセグメントアイコンを選択し、「**[!UICONTROL 管理]**」を選択します。

## セグメントマネージャーで使用可能なアクション

セグメントマネージャーでは、次の操作を実行できます。

* [セグメントのフィルタリング](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [セグメントのお気に入りへの登録](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [セグメントの承認](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [セグメントのタグ設定](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [セグメントの共有](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* セグメントを CSV ファイルに書き出します。

* [セグメントのコピー](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [セグメントの削除](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## 列の設定

表示される列を設定することで、セグメントマネージャーで各セグメントに表示される情報を設定できます。

セグメントマネージャーで表示可能な列を設定するには：

1. Adobe Analyticsで、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL セグメント]**」を選択します。

1. セグメントマネージャーで **列をカスタマイズ** アイコン ![ 列をカスタマイズのアイコン ](assets/customize-columns-icon.png) を選択してから、セグメントマネージャーに表示する列を選択します。

   次の列を表示できます。

   | 列タイトル | 説明 |
   |---|---|
   | タイトルと説明 | これらの値は、セグメントビルダーで指定されます。 タイトルと説明を編集するには、タイトルリンクを選択してセグメントビルダーを開きます。 |
   | お気に入り | 各セグメントの横に星形アイコンが表示され、セグメントをお気に入りとしてマークできます。 詳しくは、[ セグメントをお気に入りとしてマークする ](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md) を参照してください。 |
   | レポートスイート | この列には、セグメントが最後に保存されたレポートスイートが示されます。 |
   | 所有者 | セグメントの所有者が示されます。管理者以外のユーザーは、自分が所有しているまたは自分が共有していたセグメントのみを表示できます。 |
   | タグ（列の選択でチェックされていないので、列は表示されていません） | 自分または自分とセグメントを共有しているユーザーによってセグメントに適用されたタグ。 |
   | 共有先 | 自分がセグメントを共有している個人、グループまたは全員が表示されます。グループまたは全員を表示できるのは管理者のみです。 <p>セグメントが自分または自分と共有されている場合、セグメント名の横に共有アイコンが表示されます。</p> |
   | 変更日 | セグメントが最後に修正された日付を表示します。 |
   | 使用場所 | セグメントが現在使用されている場所と、各領域で使用されている回数を表示します。 <p>例えば、セグメントが 40 件のプロジェクトと 2 件のアラートで使用されている場合、この列の値は [!UICONTROL **42 components**] と表示されます。</p> <p>この列の値を選択すると、セグメントが使用されている場所（例：[!UICONTROL **プロジェクト （40）**]、[!UICONTROL **アラート （2）**]）の分類が表示されます。 さらに、セグメントが使用されている項目のリストを表示できます。 例えば、使用されているプロジェクトのリストを表示するには、「[!UICONTROL **プロジェクト （40）**]」リンクを選択します。</p><p>次の各領域には、その領域で使用されているセグメントのインスタンス数が表示されます。</p>  <ul><li>[!UICONTROL **プロジェクト**]<p>[ セグメントビルダーで作成 ](/help/components/segmentation/segmentation-workflow/seg-build.md) されたセグメントが含まれており、すべてのプロジェクトで使用できます。</p></li><li>[!UICONTROL **アドホックコンポーネント**]<p>[ クイックセグメントとして作成 ](/help/analyze/analysis-workspace/components/segments/quick-segments.md) されたセグメントを含み、1 つのプロジェクト内でのみ使用できます。</p></li><li>[!UICONTROL **スケジュールされたプロジェクト**]</li><li>[!UICONTROL **モバイルスコアカード**]</li><li>[!UICONTROL **注釈**]</li><li>[!UICONTROL **アラート**]</li><li>[!UICONTROL **計算指標**]</li><li>[!UICONTROL **Report Builder**]<p>このオプションを選択すると、次のデータ列を含む CSV ファイルがダウンロードされます。</p><ul><li>Report Builder名</li><li>最終アクセス日</li><li>最終アクセス日の IMS ユーザー ID</li><li>最終アクセス日のユーザー名</li></ul><p>Report Builder情報をご覧いただく場合、2024 年 9 月より利用案内をご利用いただけます。</p></li></ul><p>この情報は、コンポーネントが組織内のユーザーにとって価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報は、システム管理者のみが使用できます。</li><li>[!UICONTROL **使用**] 列はデフォルトでは表示されません。 [ 列を設定 ](#configure-columns) して表示します。</li><li>セグメントの定義に別のセグメントが含まれている場合、そのセグメントの使用は [!UICONTROL **使用**] 列に表示されません。 セグメントが別のタイプのコンポーネント（計算指標など）の定義に含まれている場合、その使用状況は [!UICONTROL **使用**] 列に表示されます。</li><li>この情報には、API またはData Warehouseからの使用は含まれません。</li><li>この列に特定のコンポーネントに関するデータがないが、そのデータに [!UICONTROL **前回の使用**] 日付が含まれている場合、そのコンポーネントは保存されずに分析で使用された可能性があります。</li><li>使用状況に関する情報は、2023年9月より提供されます。</li></ul><p>この情報と共に [ データ要素 ](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。</p> |
   | 前回の使用 | 次のいずれかのコンポーネントタイプでセグメントが最後に使用された日付を表示します。 <ul><li>アラート</li><li>計算指標</li><li>プロジェクト</li><li>スケジュールされたプロジェクト</li><li>セグメント</li></ul> <p>この情報は、コンポーネントが組織内のユーザーにとって価値があるかどうか、コンポーネントが使用されている場所、コンポーネントを削除または変更する必要があるかどうかを判断するのに役立ちます。</p><p>この列を表示する際は、次の点を考慮してください。</p><ul><li>この情報には、API、Report Builder、Data Warehouseからの使用は含まれません。</li><li>一部のコンポーネントでは、2023 年 9 月より前にコンポーネントが最後に使用されていた場合、この列にデータが含まれないことがあります。</li><li>この情報は、システム管理者のみが使用できます。</li></ul><p>この情報と共に [ データ要素 ](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) を使用すると、組織でコンポーネントがどのように使用されているかを追跡し、よりよく理解できます。 |

   {style="table-layout:auto"}

## ハウツービデオ {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

この [Adobe Analytics の ビデオ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=ja)では、セグメントマネージャの使用方法の概要を説明しています。


