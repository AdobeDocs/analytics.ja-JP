---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストの一般設定
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 26%

---

# Data Warehouse リクエストの一般設定

Data Warehouse を作成する際には、様々な設定オプションを使用できます。次の情報は、リクエストの一般設定を指定する方法を示しています。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouse リクエストの一般設定を指定するには：

1. **[!UICONTROL ツール]**/**[!UICONTROL Data Warehouse]**/&lbrace; 追加 [!UICONTROL **を選択して、Adobe AnalyticsでData Warehouse リクエストの作成を開始し**] す。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouse リクエスト ページで、「[!UICONTROL **一般設定**]」タブを選択します。

   ![レポートの宛先タブ](assets/dw-general-settings.png)

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | リクエスト名 | リクエストを管理する際に、Data Warehouseのメインページにこの名前が表示されます。 |
   | 日付範囲 | レポートに含める日付範囲を選択します。 <p>カスタムの日付またはプリセットの日付範囲を選択できます。 プリセットの範囲は、レポートが送信された日付に関連しています。</p><p>次のプリセットオプションを使用できます。</p><ul><li>Today</li><li>昨日</li><li>過去 7 日間</li><li>過去 30 日間</li><li>今週</li><li>先週</li><li>過去 2 週間</li><li>過去 3 週間</li><li>過去 4 週間</li><li>今月</li><li>先月</li><li>過去 1 時間</li></ul> |
   | 精度 | 時間の精度。 設定できる値は「なし」、「時間」、「日」、「週」、「月」、「四半期」、「年」です。<p>レポートの精度には、追加の処理時間が必要です。 1 年間にわたって毎月の精度でレポートを作成する場合、毎月のレポートリクエストを送信すると、レポートの処理がはるかに高速になります。</p><p>**メモ：** Data Warehouse リクエストで精度を適用する場合、「日付」列がレポートに追加されます。 選択した精度に応じて、日付の形式は次のように変わります。</p><ul><li>**時間単位の精度**:<ul> <li>**形式**:`mmmm d, yyyy` 時間 `H`</li><li>**例**:20XX 年 1 月 1 日、0 時 </li></ul><li>**毎日の精度**:<ul> <li>**形式**：`mmmm d, yyyy`</li><li>**例**:20XX 年 1 月 1 日</li></ul><li>**毎週の精度**:<ul> <li>**形式**:`w, yyyy` 週</li><li>**例**:1 週目、20XX </li></ul><li>**月ごとの精度**:<ul> <li>**形式**：`mmmm yyyy`</li><li>**例**:20XX 年 1 月 </li></ul><li>**四半期ごとの精度**:<ul> <li>**形式**:`q` Quarter `yyyy`</li><li>**例**：第 1 四半期 20XX </li></ul><li>**年単位の精度**:<ul> <li>**形式**：`yyyy`</li><li>**例**:20XX</li></ul> |
   | 組織内のユーザーに利用できるようにする | すべての Data Warehouse リクエストは、ユーザーとシステム管理者にのみ表示されます。 組織内のすべてのユーザーにリクエストを表示する場合は、このオプションを有効にします。 <p>このオプションを有効にすると、組織内の他のユーザーがリクエストの作成や更新に役立てることができます。</p> |

   {style="table-layout:auto"}

1. 「[!UICONTROL **レポートを作成**]」タブで、Data Warehouse リクエストの設定を続けます。 詳しくは、[Data Warehouse リクエストのレポートの作成 &#x200B;](/help/export/data-warehouse/create-request/dw-request-build-report.md) を参照してください。
