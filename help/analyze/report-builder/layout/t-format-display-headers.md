---
description: レポートに名前を付けたり、行ヘッダーと列ヘッダーの表示方法を設定したりすることができます。ピボットレイアウトとカスタムレイアウトで、「フォーマットオプション」のリンクから指定できます。
seo-description: レポートに名前を付けたり、行ヘッダーと列ヘッダーの表示方法を設定したりすることができます。ピボットレイアウトとカスタムレイアウトで、「フォーマットオプション」のリンクから指定できます。
seo-title: 表示ヘッダーのフォーマット
solution: Analytics
title: 表示ヘッダーのフォーマット
topic: Report Builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 表示ヘッダーのフォーマット

レポートに名前を付けたり、行ヘッダーと列ヘッダーの表示方法を設定したりすることができます。ピボットレイアウトとカスタムレイアウトで、「フォーマットオプション」のリンクから指定できます。

1. [!UICONTROL リクエストウィザード：ステップ 1] でリクエストを作成します。
1. Click **[!UICONTROL Next]**.
1. [!UICONTROL リクエストウィザード：ステップ 2] のフォームで、必要に応じて、リクエストにディメンションおよび指標データを追加します。
1. **[!UICONTROL 「フォーマットオプション]**」をクリックします。
1. [!UICONTROL 表示]オプションを設定します。

   | 要素 | 説明 |
   |--- |--- |
   | レポート名 | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | フィルターパラメーター | 検索フィルターなどのディメンションフィルターを表示します。 |
   | Segment | セグメントパラメーターを表示します。 |
   | データ最新性 | 直近いつまでのデータが含まれているかを表示します。For example:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   表示順については、ステップ 2 の[!UICONTROL 行ラベル]グリッドに項目が含まれる場合は、リクエストの最初の項目が表示されます。項目がない場合は、[!UICONTROL 列ラベル]グリッドの最初の項目が使用されます。行にも列にも項目がない場合は、[!UICONTROL 指標]グリッドにある最初の項目が表示されます。

   **行と列のヘッダーを表示：**&#x200B;項目を表示する行と列を追加します。

   バージョン 3.11 では、各項目に対してヘッダーを表示できました。バージョン 4 ではすべての項目が表示されるか、まったく表示されないかのいずれかになります。バージョン 3.11 で作成したリクエストをバージョン 4.x で開くと、Report Builder でステップ 2 が表示され、ヘッダーがなくなっている項目に対して、1 つのセルで範囲を更新するように求められます。

   **ヘッダーを Excel の自動フィルターに変更：**&#x200B;これは、行ヘッダーおよび列ヘッダーが表示されている場合のみ利用できます。この設定によって、Excel の自動フィルターが作成され、このリクエストに対して Report Builder が返すデータに付加されます。

   >[!NOTE]
   >
   >Excelはワークシートごとに1つの自動フィルタのみをサポートしています。自動フィルターが既に設定されているワークシートで新しい自動フィルターを作成した場合、Excel では警告が表示されずに既存の自動フィルターが置き換えられます。

   **自動アウトラインを実行：** Report Builder から返される日付をリストビューからツリービューに変換します。

   **このリクエストに名前を作成：**&#x200B;リクエストに対してユーザー指定の名前を入力できます。または、ステップ 1 で選択されたデフォルトの名前が使用されます。この名前は、[!UICONTROL リクエストマネージャー]で[!UICONTROL レポート]名として表示されます。詳しくは、 [リクエストの名前の設定](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D).

1. Click **[!UICONTROL OK]**.
