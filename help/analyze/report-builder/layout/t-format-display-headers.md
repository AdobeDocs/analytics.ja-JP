---
description: レポートに名前を付けたり、行ヘッダーと列ヘッダーの表示方法を設定したりすることができます。ピボットレイアウトとカスタムレイアウトで、「フォーマットオプション」のリンクから指定できます。
title: 表示ヘッダーのフォーマット
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 表示ヘッダーのフォーマット

レポートに名前を付けたり、行ヘッダーと列ヘッダーの表示方法を設定したりすることができます。ピボットレイアウトとカスタムレイアウトで、「フォーマットオプション」のリンクから指定できます。

1. でリクエストを作成しま [!UICONTROL Request Wizard: Step 1]す。
1. クリック **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. クリック **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | 要素 | 説明 |
   |--- |--- |
   | レポート名 | リクエストウィザード：ステップ 1 内のツリーから選択したレポートタイプ名（例：[!DNL Traffic Report]）か、「[!DNL Name this Request]」フィールドに入力した名前のいずれかが表示されます。 |
   | フィルターパラメーター | 検索フィルターなどのディメンションフィルターを表示します。 |
   | セグメント | セグメントパラメーターを表示します。 |
   | データ最新性 | 直近いつまでのデータが含まれているかを表示します。例：データ最新性：ページビュー数（1.5時間前）、出口数（30分前）。現在のデータ処理について詳しくは、[オプション](/help/analyze/report-builder/options.md)を参照してください。 |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **行と列のヘッダーを表示：**&#x200B;項目を表示する行と列を追加します。

   バージョン 3.11 では、各項目に対してヘッダーを表示できました。バージョン 4 ではすべての項目が表示されるか、まったく表示されないかのいずれかになります。バージョン 3.11 で作成したリクエストをバージョン 4.x で開くと、Report Builder でステップ 2 が表示され、ヘッダーがなくなっている項目に対して、1 つのセルで範囲を更新するように求められます。

   **ヘッダーを Excel の自動フィルターに変更：**&#x200B;これは、行ヘッダーおよび列ヘッダーが表示されている場合のみ利用できます。この設定によって、Excel の自動フィルターが作成され、このリクエストに対して Report Builder が返すデータに付加されます。

   >[!NOTE]
   >
   >Excel がサポートするのは、1 ワークシートあたり 1 つの自動フィルターのみです。自動フィルターが既に設定されているワークシートで新しい自動フィルターを作成した場合、Excel では警告が表示されずに既存の自動フィルターが置き換えられます。

   **自動アウトラインを実行：** Report Builder から返される日付をリストビューからツリービューに変換します。

   **このリクエストに名前を作成：**&#x200B;リクエストに対してユーザー指定の名前を入力できます。または、ステップ 1 で選択されたデフォルトの名前が使用されます。この名前は、に名前と [!UICONTROL Report] して表示されま [!UICONTROL Request Manager]す。 See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. クリック **[!UICONTROL OK]**.
