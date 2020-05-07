---
description: Analysis Workspace でコホートを作成し、コホート分析レポートを実行します。
keywords: Analysis Workspace
title: コホート分析レポートの実行
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 79849c574909543d74e2935e493008927700585d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 74%

---


# Configure a [!UICONTROL Cohort Analysis] report

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. **[!UICONTROL Analysis Workspace で、左側のパネルのビジュアライゼーション]**&#x200B;アイコンをクリックし、**[!UICONTROL コホートテーブル]**&#x200B;をキャンバスにドラッグします。

   ![](assets/cohort-table.png)

1. 以下のテーブルに従って、**[!UICONTROL インクルージョン条件]**、**[!UICONTROL リターン条件]**、**[!UICONTROL コホートタイプ]**、**[!UICONTROL 設定]**&#x200B;を定義します。

| 要素 | 説明 |
|--- |--- |
| **[!UICONTROL 包含条件]** | 最大で、10 個のインクルージョンセグメントおよび 3 個のインクルージョン指標を適用できます。指標は、ユーザーをコホートのどこに配置するかを指定します。例えば、インクルージョン指標が「注文」の場合、コホート分析の期間中に注文したユーザーのみが最初のコホートに含まれます。<br>指標間のデフォルトの演算子は「AND」ですが、「OR」に変更することもできます。また、これらの指標に対して数値的なフィルタリングを追加することもできます。例えば、「訪問数 >= 1」のように設定することもできます。</br> |
| **[!UICONTROL リターン条件]** | 最大で、10 個のリターンセグメントおよび 3 個のリターン指標を適用できます。この指標は、ユーザーが保持されたか（リテンション）、保持されなかったか（チャーン）を示します。例えば、リターン指標が「ビデオ視聴回数」の場合、その後の期間（コホートに追加された後の期間）にビデオを視聴したユーザーのみが保持されているとして表されます。保持を定量化するその他の指標は「訪問回数」です。 |
| **[!UICONTROL 精度]** | 日、週、月、四半期および年の時間の精度。 |
| **[!UICONTROL タイプ]** | **[!UICONTROL リテンション]**（デフォルト）：リテンションコホートでは、訪問者のコホートが時間の経過に伴ってどの程度サイトやアプリに戻ってきたかを測定します。これは常に使用されてきた標準的なコホートで、サイトやアプリに戻り、リピートする行動を示します。A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL チャーン&#x200B;]**：チャーン（「訪問低下」や「フォールアウト」とも呼ばれます）コホートでは、訪問者のコホートが時間の経過に伴ってサイトやアプリからどの程度フォールアウトしたかを測定します。「チャーン = 1 - リテンション」となります。[!UICONTROL チャーンは、顧客がどの程度戻ってこなかったかを示すことで、定着度および改善のチャンスを示す良い指標となります。]チャーンを使用して、注目すべき領域（どのコホートセグメントに注目すべきか）を分析し、特定できます。A[!UICONTROL Churn]Cohort is indicated by the color red in the table (similar to fallout in our**[!UICONTROL  Flow ]**visualization).</br> |
| **[!UICONTROL 設定]** | **[!UICONTROL ローリング計算]**：「含む」列（デフォルト）ではなく、直前の列に基づいてリテンションまたはチャーンを計算できます。[!UICONTROL ローリング計算では、「リターン」の期間の計算方法が変わります。]通常の計算では、直前の期間で該当するコホートに含まれていたかどうかにかかわらず、インクルージョン期間に含まれる「リターン」条件を満たすユーザーが独立して検出されます。Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL リターン条件は、選択した期間に至るまでの各期間に適用されます。]</br><br>**[!UICONTROL 待ち時間テーブル&#x200B;]**: 待ち[!UICONTROL 時間]テーブルは、インクルージョンイベントが発生する前後の経過時間を測定します。[!UICONTROL 待ち時間は、イベント前後の分析に役立ちます。]For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the[!UICONTROL Latency]table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the[!UICONTROL Latency]Table are calculated by users who meet the[!UICONTROL Inclusion]criteria on the inclusion period and then meet the[!UICONTROL Return]criteria in the periods before the inclusion period. Note that[!UICONTROL Latency]tables and[!UICONTROL Custom Dimension]Cohort cannot be used together.</br><br>**[!UICONTROL カスタムディメンションコホート]**：時間に基づくコホート（デフォルト）ではなく、選択したディメンションに基づくコホートを作成します。多くのユーザーは、時間以外の基準でコホートを分析することを必要としています。新しいカスタムディメンションコホート機能を使用することで、任意のディメンションに基づいて柔軟にコホートを作成できます。マーケティングチャネル、キャンペーン、製品、ページ、地域などのディメンションや、Adobe Analytics のその他のディメンションを使用して、これらのディメンションの様々な値に基づいてリテンションがどのように変化しているかを表示します。The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL カスタムディメンションコホートオプションを選択した後、任意のディメンションをドロップゾーンにドラッグ＆ドロップします。]これにより、同じ期間で類似のディメンション項目を比較できます。例えば、都市、製品、キャンペーンなどを並べて比較できます。上位 14 のディメンション項目が返されます。ただし、フィルター（ドラッグされたディメンションの右側にマウスポインターを置くとこの機能を使用できます）を使用して、必要なディメンション項目のみを表示できます。A [!UICONTROL Custom Dimension] Cohort cannot be used with the [!UICONTROL Latency] Table feature.</br> |

1. 歯車アイコンをクリックして、**[!UICONTROL コホートテーブル設定]**&#x200B;を調整します。

| 設定 | 説明 |
| 割合のみ表示 | 数値を削除し、割合のみを表示します。|
| パーセントを最も近い整数に丸める | パーセント値を小数値ではなく、最も近い整数に丸めます。|
| 平均パーセント行を表示 | テーブルの先頭に新しい行を挿入し、各列の値の平均を加算します。|

## Build the [!UICONTROL Cohort Analysis] report

1. 「**[!UICONTROL 作成]**」をクリックします。

   ![手順の結果](assets/cohort-report.png)

   このレポートは、注文した訪問者（*`Included`*&#x200B;列）と、その後の訪問でサイトに戻った訪問者を表示します。時間の経過に伴う訪問者数の減少は、問題の目印となり、行動を起こすことを可能にします。
1. （オプション）選択範囲からセグメントを作成します。

   複数のセルを選択して（連続または不連続）、右クリックし、「**[!UICONTROL 選択からセグメントを作成]**」をクリックします。

1. [セグメントビルダー](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md)で、セグメントをさらに編集して、「**[!UICONTROL 保存]**」をクリックします。

   The saved segment is available for use in the [!UICONTROL Segment] panel in [!UICONTROL Analysis Workspace].
1. コホートプロジェクトに名前を付けて保存します。
1. （オプション）[プロジェクトコンポーネントをキュレーションおよび共有](/help/analyze/analysis-workspace/curate-share/curate.md)します。

   >[!NOTE]
   >
   >キュレーションを使用する前に、プロジェクトを保存する必要があります。

