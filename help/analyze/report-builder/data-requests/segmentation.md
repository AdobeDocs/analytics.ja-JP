---
description: Report Builder で Adobe Analytics のセグメントを追加、編集、適用およびフィルターする方法について説明します。
seo-description: Report Builder で Adobe Analytics のセグメントを追加、編集、適用およびフィルターする方法について説明します。
seo-title: セグメントの管理
solution: Analytics
title: セグメントの管理
topic: Report Builder
uuid: 4e4edc39- ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# セグメントの管理

Report Builder で Adobe Analytics のセグメントを追加、編集、適用およびフィルターする方法について説明します。

Report Builder のリクエストウィザードのステップ 1 にセグメント化パネルが追加されました。このパネルでは、次のことを実行できます。セグメントの作成と管理を参照してください。

![](assets/seg_dialog.png)

## セグメントの追加または編集 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Report Builderのセグメントのインターフェイスを追加または編集するには、Microsoft Internet ExplorerウィンドウでAnalyticsセグメントビルダーを起動します。Report Builder のセッションはアクティブな状態に維持されます。ブラウザーを Internet Explorer 以外に変更することはできません。

1. In the segment panel of Step 1 of the Request Wizard, click **[!UICONTROL Add]**.
1. Internet Explorer のウィンドウが起動し、Analytics セグメントビルダーインターフェイスが開きます。セグメントの作成方法について詳しくは[https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) を参照してください。
1. セグメントを定義して保存したら、リクエストウィザードに戻ります。
1. 更新アイコンをクリックして、セグメント一覧を更新します

>[!IMPORTANT]
>
>このリストはキャッシュされ、更新しない限り新しく作成したセグメントは表示されません。

## コンテキスト内セグメントの作成 {#section_6DD2C663B2854469AA1075438F907678}

レポート閲覧中に、表示されているディメンションを使ってセグメントを作成したい場合があります。Report Builder インターフェイスからこのようなセグメントを作成できます。例えば、ページリクエスト出力からいくつかのページを選択し、それらの値に基づいてセグメントを作成できます。

1. セグメントに含めるレポート出力項目を選択します。
1. 右クリックして&#x200B;**[!UICONTROL 次の中にコンテキスト内セグメントを作成]を選択し、適切なコンテナ（ヒット数コンテナ、訪問コンテナ、訪問者コンテナ）を指定します。**

   ![](assets/seg_in_context.png)

   コンテナについて詳しくは、[セグメント化ガイド](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)を参照してください。

1. セグメントビルダーの UI が Internet Explorer で起動します。セグメントビルダーの UI に指定したコンテナおよびフィルターが反映されます。
1. セグメントに名前と説明を追加し、保存します。
1. Report Builder に戻り、更新アイコンをクリックして、セグメントの一覧を更新します。
1. これで、このセグメントを適用する準備が整いました。

## セグメントの検索および適用 {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

Reports &amp; Analytics、Ad Hoc Analysis、Report Builder または Data Warehouse で作成したすべてのセグメントがこのセグメント一覧に表示されます。To refresh the list, click the Refresh icon ( ![](assets/refresh_icon.png).

リクエストに 1 つ以上のセグメントを適用できます。これには順次セグメントも含まれます。

1. **[!UICONTROL 「セグメント」]** ドロップダウンリストに移動し、「[!UICONTROL セグメント]を選択**"ボックスの小さい下矢印をクリックして、すべてのセグメントを表示します。

   ![](assets/seg_list.png)

1. 適用するセグメントのチェックボックスをオンにします。

>[!NOTE]
>
>管理者または管理者以外のユーザーの場合、Report Builderでは、自分が所有しているセグメントおよび自分が共有しているセグメントのみを表示できます。（Reports &amp; Analytics のユーザーインターフェイスでは、管理者は組織内のすべてのセグメントが表示されます）。

## セグメントのフィルタリング {#section_376E986D3E684999A7CDB08E53854159}

フィルターアイコン（**）をクリックして、セグメントを**&#x200B;フィルター![します。](assets/segment_filter.png)

次のフィルターを利用できます。

| フィルター名 | 説明 |
|---|---|
| タグ | タグでセグメントをフィルターできます。タグフィルターでは、AND 演算子が使用されます。2 つのタグのチェックボックスをオンにすると、右側のペインに、**両方の**&#x200B;タグが付けられているセグメントが表示されます。 |
| 所有者 | 所有者でセグメントをフィルターできます。所有者フィルターでは、OR 演算子が使用されます。2 人の所有者のチェックボックスをオンにすると、右側のペインに、**いずれかの**&#x200B;所有者が所有するセグメントが表示されます。 |
| その他のフィルター／「*レポートスイート名*」のみ | If you apply the "Only *report suite name*" filter in the Segment Builder in [!DNL marketing reports & analytics], and then display the Advanced Filter in [!DNL report builder], the Advanced filter will display the segment for the selected report suite only. |
| その他のフィルター／自分が所有 | 自分が所有しているセグメントをすべて表示します。 |
| その他のフィルター／自分と共有 | 自分と共有されているすべてのセグメントが表示されます。 |
| その他のフィルター／お気に入り | お気に入りとしてマークしたすべてのセグメントが表示されます。 |
| その他のフィルター／承認済み | 正式に承認されたすべてのセグメントが表示されます。 |

## ワークブックへのセグメントコントロールの追加 {#section_E3E5149A8464441FA5445A98DBD520AC}

セグメントコントロールを追加すると、リクエストウィザードに移動することなく、ワークブック内からセグメントを切り替えることができるようになります。

1. Click the Control icon ( ![](assets/control_icon.png)) next to the segment drop-down.

   ![](assets/seg_control.png)

1. Check all the segments that you want to appear in the segment control, or check **[!UICONTROL Select All]**.
1. Notice the option **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * このオプションを有効にすると、このコントロールを使用するすべてのリクエストが自動で更新されます。
   * このオプションを有効にしないと、リクエストの設定は更新されますが、リクエストのデータは更新されません。

1. セグメントコントロールの左上のセルの場所を指定します。
1. 「**[!UICONTROL OK]」をクリックすると、指定した場所にセグメントコントロールが表示されます。**

   ![](assets/seg_control2.png)

## セグメントの一覧の更新 {#section_22E4A86789444B4A998532396B476EFB}

Any time you add a new segment or edit an existing one, you should click the Refresh icon ( ![](assets/refresh_icon.png) to refresh the cached list of segments.

## 複数のリクエストにわたるセグメントの管理 {#section_C3D63FCBE1A94369A319243313B03C93}

v5.4 より前の Report Builder を使用すると、ユーザーは複数のリクエストのセグメントを変更できます。ただし、この処理は、通常、既存のセグメントを置き換えます。セグメントの追加によって各リクエストに既に割り当てた以前のセグメントのセットが削除されるので、ユーザーは、各リクエストに 1 つの新しいセグメントを追加することはできませんでした。

Report Builder 5.4 を使用すると、複数のリクエストでセグメントの追加、削除、置換、全置換をおこなうことができます。

1. ワークブックで複数のリクエストを選択します。
1. Right-click and select **[!UICONTROL Edit Requests]** &gt; **[!UICONTROL By Segment]**.

   ![](assets/edit_by_segment.png)

1. グループを編集ダイアログで、次の 4 つのオプションのうちいずれかを選択します。

   | オプション | 説明 |
   |---|---|
   | セグメントの追加 | 1 つまたは複数のセグメントを選択して、現在のセグメントのリストに追加できます。 |
   | セグメントを置換 | 1 つまたは複数のセグメントで置き換えるセグメントを選択できます。 |
   | すべてのセグメントを次で置換 | 現在のセグメントから置換する 1 つまたは複数のセグメントを選択できます。 |
   | セグメントを削除 | リクエストからセグメントを削除できます。 |

