---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: Data Warehouseリクエストの一般設定
feature: Data Warehouse
source-git-commit: ea4c1ae21f2c83bad92723e6ffd2e706fac5e1e8
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 26%

---

# Data Warehouseリクエストの一般設定

>[!AVAILABILITY]
>
>この記事 ( およびこの節の他のData Warehouse記事 ) で説明するData Warehouse機能の一部は、リリースの制限付きテスト段階でのみ使用でき、お使いの環境ではまだ使用できない場合があります。
>
>すべてのお客様がまだ利用できない機能について、およびこれらの機能のリリースのタイムラインについて詳しくは、 [リリースノート](/help/release-notes/latest.md).
>
>このメモは、機能が一般入手可能になったら削除されます。Analytics リリースプロセスについて詳しくは、[Adobe Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。

設定リクエストを作成する際には、様々な設定オプションをData Warehouseできます。 次の情報では、要求の一般的な設定方法を説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Data Warehouse要求の一般設定を構成するには：

1. Adobe AnalyticsでData Warehouseリクエストの作成を開始するには、「 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **一般設定**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-general-settings.png)

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | リクエスト名 | この名前は、リクエストを管理する際にメインData Warehouseページに表示されます。 |
   | 日付範囲 | レポートに含める日付範囲を選択します。 <p>カスタム日付、または事前設定された日付範囲を選択できます。 プリセット範囲は、レポートの送信日に相対的な日付です。</p><p>次のプリセットオプションを使用できます。</p><ul><li>Today</li><li>昨日</li><li>過去 7 日間</li><li>過去 30 日間</li><li>今週</li><li>先週</li><li>最近の 2 週間</li><li>最近の 3 週間</li><li>最近の 4 週間</li><li>今月</li><li>先月</li><li>過去 1 時間</li></ul> |
   | 精度 | <!--what does this setting do? It's not the schedule/frequency... --> 時間の精度。 設定できる値は「なし」、「時間」、「日」、「週」、「月」、「四半期」、「年」です。<p>精度をレポートするには追加の処理時間が必要になります。1 年間の月の精度をレポートする場合、月ごとにレポートリクエストを送信するとレポートプロセスがより高速に処理されます。</p> |

   {style="table-layout:auto"}

1. 引き続き、 [!UICONTROL **レポートの作成**] タブをクリックします。 詳しくは、 [Data Warehouse要求用のレポートの作成](/help/export/data-warehouse/create-request/dw-request-build-report.md).