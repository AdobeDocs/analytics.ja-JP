---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouseの一般設定のリクエスト
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
TQID: https://experienceleague.adobe.com/-FIw9vHeGpDbpd09GgRQqgK-5-srLyNCjDCLLhPBEYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 29%

---

# Data Warehouseの一般設定のリクエスト

Data Warehouse を作成する際には、様々な設定オプションを使用できます。 次の情報では、リクエストの一般的な設定の設定方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouse リクエストの一般的な設定を行うには、次の手順を実行します。

1. Adobe AnalyticsでData Warehouse リクエストの作成を開始するには、**[!UICONTROL ツール]**/**[!UICONTROL Data Warehouse]**/[!UICONTROL **追加**]&#x200B;を選択します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新規Data Warehouse リクエストページで、「[!UICONTROL **一般設定**]」タブを選択します。

   ![レポートの宛先タブ](assets/dw-general-settings.png)

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | リクエスト名 | この名前は、リクエストを管理する際に、メインのData Warehouse ページに表示されます。 |
   | 日付範囲 | レポートに含める日付範囲を選択します。 <p>カスタム日付またはプリセットの日付範囲を選択できます。 プリセット範囲は、レポートの送信日を基準としています。</p><p>次のプリセットオプションを使用できます。</p><ul><li>今日</li><li>昨日</li><li>最近の 7 日間</li><li>最近の 30 日間</li><li>今週</li><li>先週</li><li>最近の 2 週間</li><li>最近の 3 週間</li><li>過去 4 週間</li><li>今月</li><li>先月</li><li>過去 1 時間</li></ul> |
   | 精度 | 時間の精度： 設定できる値は「なし」、「時間」、「日」、「週」、「月」、「四半期」、「年」です。<p>レポートの詳細を確認するには、さらに多くの処理時間が必要です。 年間を通じて月単位で詳細なレポートを作成する場合、月単位でレポートリクエストを送信すると、レポートの処理が大幅に高速化します。</p><p>**メモ：** Data Warehouse リクエストで精度を適用すると、「日付」列がレポートに追加されます。 選択した精度に応じて、日付形式は次のように変更されます。</p><ul><li>**時間単位の精度**:<ul> <li>**形式**: `mmmm d, yyyy`時間`H`</li><li>**例**: 1月1日、20XX、時間0 </li></ul><li>**1日の精度**:<ul> <li>**形式**：`mmmm d, yyyy`</li><li>**例**: 20XX年1月1日</li></ul><li>**週単位の精度**:<ul> <li>**形式**：週`w, yyyy`</li><li>**例**：週1、20XX </li></ul><li>**月間精度**:<ul> <li>**形式**：`mmmm yyyy`</li><li>**例**: 1月20XX日 </li></ul><li>**四半期ごとの精度**:<ul> <li>**形式**: `q`四半期`yyyy`</li><li>**例**：第1四半期20XX </li></ul><li>**年間粒度**:<ul> <li>**形式**：`yyyy`</li><li>**例**: 20XX</li></ul> |
   | 組織内のユーザーに利用できるようにする | すべてのデータウェアハウスのリクエストは、ユーザーとシステム管理者のみが表示できます。 組織内のすべてのユーザーがリクエストを表示できるようにする場合は、このオプションを有効にします。 <p>このオプションを有効にすると、組織内の他のユーザーにリクエストの作成や更新を支援してもらいたい場合に便利です。</p> |

   {style="table-layout:auto"}

1. 引き続き、「[!UICONTROL **レポートを作成**]」タブでData Warehouse リクエストの設定を行います。 詳しくは、「[Data Warehouse リクエストのレポートを作成する](/help/export/data-warehouse/create-request/dw-request-build-report.md)」を参照してください。
