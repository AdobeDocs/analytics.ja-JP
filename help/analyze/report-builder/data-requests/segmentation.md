---
description: Report Builder で Adobe Analytics のセグメントを追加、編集、適用およびフィルターする方法について説明します。
title: セグメントの管理
topic: Report builder
uuid: 4e4edc39-ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# セグメントの管理

Report Builder で Adobe Analytics のセグメントを追加、編集、適用およびフィルターする方法について説明します。

Report Builder のリクエストウィザードのステップ 1 に、セグメントを作成および管理できるセグメント化パネルが追加されました。

![](assets/seg_dialog.png)

## セグメントの追加または編集 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]Report Builder でセグメントを追加または編集するためのインターフェイスは、Microsoft Internet Explorer ウィンドウで Analytics のセグメントビルダーを起動します。Report Builderセッションはアクティブなままです。 この操作では、Internet Explorer以外のブラウザーはサポートされていません。

1. リクエストウィザードの手順1のセグメントパネルで、をクリックしま **[!UICONTROL Add]**&#x200B;す。
1. Internet Explorerウィンドウが開き、Analyticsのセグメントビルダーインターフェイスが開きます。 セグメントの作成方法について詳しくは、https://marketing.adobe.com/resources/help/en_US/analytics/segment/を参照して [ください](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/)。
1. セグメントを定義して保存した後、リクエストウィザードに戻ります。
1. 更新アイコンをクリックして、セグメントのリストを更新します。

>[!IMPORTANT]
>
>セグメント一覧はキャッシュされるため、一覧を更新しないと新しく作成したセグメントは表示されません。

## コンテキスト内セグメントの作成 {#section_6DD2C663B2854469AA1075438F907678}

レポート閲覧中に、表示されているディメンションを使ってセグメントを作成したい場合があります。これらのセグメントは、Report Builderインターフェイスから作成できます。 例えば、ページリクエストの出力からいくつかのページを選択し、これらの値に基づいてセグメントを作成します。

1. セグメントにするレポート出力項目を選択します。
1. Right-click to select **[!UICONTROL Create In-Context Segment in]** and specify the right container (Hits Container, Visits Container, Visitor Container).

   ![](assets/seg_in_context.png)

   コンテナについて詳しくは、セグメント化ガイドを参 [照してください](https://marketing.adobe.com/resources/help/ja_JP/analytics/segment/)。

1. セグメントビルダーのUIがInternet Explorerで起動します。 セグメントビルダーのUIが、指定したコンテナとフィルターで初期化されます。
1. セグメントに名前と説明を追加したら、保存します。
1. report builderに戻り、更新アイコンをクリックして、セグメントのリストを更新します。
1. これで、このセグメントを適用する準備が整いました。

## セグメントの検索と適用 {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

Reports &amp; Analytics、Ad Hoc Analysis、Report Builder または Data Warehouse で作成したすべてのセグメントがこのセグメント一覧に表示されます。一覧を更新するには、更新アイコン（![](assets/refresh_icon.png)）をクリックします。

任意のリクエストに1つまたは複数のセグメントを適用できます。 これには、順次セグメントも含まれます。

1. Go to the **[!UICONTROL Segment]** drop-down list and click the small down arrow in the **[!UICONTROL Choose Segment]** box to display all the segments.

   ![](assets/seg_list.png)

1. 適用するセグメントのチェックボックスをオンにします。

>[!NOTE]管理者であるかどうかにかかわらず、Report Builder では、自分が所有しているセグメント、および自分へ共有されているセグメントのみが表示されます（Reports &amp; Analytics のユーザーインターフェイスでは、管理者は組織内のすべてのセグメントが表示されます）。

## セグメントのフィルタリング {#section_376E986D3E684999A7CDB08E53854159}

フィルターアイコン（**）をクリックして、セグメントを**&#x200B;フィルター![](assets/segment_filter.png)します。

次のフィルターを使用できます。

| フィルター名 | 説明 |
|---|---|
| タグ | 特定のタグを使用してセグメントをフィルターできます。 タグフィルターではAND演算子が使用されます。 2つのタグを選択すると、右側のパネルに、両方のタグが付いたセグメントが表 **示さ** れます。 |
| 所有者 | 所有者別にセグメントをフィルターできます。 所有者のフィルターはOR演算子を使用します。 2人の所有者のチェックボックスをオンにすると、右側のパネルに、いずれかの所有者が所有するセグメントが **表示さ** れます。 |
| その他のフィルター/レポ *ートスイート名のみ* | [!DNL marketing reports & analytics] のセグメントビルダーで「*レポートスイート名*」のみのフィルターを適用し、[!DNL report builder] のアドバンスフィルターを表示すると、アドバンスフィルターには選択されたレポートスイートのセグメントのみが表示されます。 |
| その他のフィルター／自分が所有 | 自分が所有しているすべてのセグメントを表示します。 |
| その他のフィルター／自分と共有 | 他のユーザーが共有しているすべてのセグメントを表示します。 |
| その他のフィルター/お気に入り | お気に入りに登録したセグメントをすべて表示します。 |
| その他のフィルター／承認済み | 正式に     承認されたセグメントをすべて表示します。 |

## ワークブックへのセグメントコントロールの追加 {#section_E3E5149A8464441FA5445A98DBD520AC}

セグメントコントロールを追加すると、リクエストウィザードに移動することなく、ワークブック内からセグメントを切り替えることができるようになります。

1. セグメントのドロップダウンの横にあるコントロールアイコン（![](assets/control_icon.png)）をクリックします。

   ![](assets/seg_control.png)

1. セグメントコントロールに表示するすべてのセグメントを選択するか、チェックしま **[!UICONTROL Select All]**&#x200B;す。
1. オプションに注意してくだ **[!UICONTROL Automatically refresh linked requests upon item selection]**&#x200B;さい。

   * オンにすると、このコントロールを使用するすべてのリクエストが更新されます。
   * 選択しない場合、関連するリクエストパラメーターは更新されますが、リクエストは更新されません。

1. セグメントコントロールの左上のセルの位置を指定します。
1. をクリック **[!UICONTROL OK]** すると、指定した場所にセグメントコントロールが表示されます。

   ![](assets/seg_control2.png)

## セグメントのリストの更新 {#section_22E4A86789444B4A998532396B476EFB}

新規セグメントを追加したり、既存のセグメントを編集したりした場合は、更新アイコン（![](assets/refresh_icon.png)）をクリックして、キャッシュされたセグメント一覧を更新する必要があります。

## 複数のリクエストにわたるセグメントの管理 {#section_C3D63FCBE1A94369A319243313B03C93}

v5.4より前のReport Builderでは、複数のリクエストに対するセグメントの変更が可能でした。 ただし、このプロセスは、常に既存のセグメントを置き換えます。 セグメントを追加すると、各リクエストに既に割り当てられていた以前のセグメントのセットが削除されるので、各リクエストに新しいセグメントを1つ追加したい場合は、この操作を実行できませんでした。

Report Builder 5.4では、複数のリクエスト内のすべてのセグメントの追加、削除、置換および置換を行うことができます。

1. ワークブック内の複数のリクエストを選択します。
1. 右クリックし、/を選 **[!UICONTROL Edit Requests]** 択します **[!UICONTROL By Segment]**。

   ![](assets/edit_by_segment.png)

1. グループを編集ダイアログで、次の4つのオプションのいずれかを選択します。

   | オプション | 説明 |
   |---|---|
   | 追加セグメント | 現在のセグメントのリストに追加する1つ以上のセグメントを選択できます。 |
   | セグメントを置換 | 1つ以上のセグメントで置き換えるセグメントを選択できます。 |
   | すべてのセグメントを次で置換 | 現在のセグメントを置き換える1つ以上のセグメントを選択できます。 |
   | セグメントの削除 | リクエストからセグメントを削除できます。 |

