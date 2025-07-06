---
description: 様々なセグメント化コンテナとその使用方法について説明します。
keywords: セグメント化：セグメント
title: セグメントコンテナ
feature: Segmentation
exl-id: f30d525b-32b7-47d5-b92d-24bf86d8a471
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '3563'
ht-degree: 96%

---


# セグメントコンテナ

セグメントは、訪問者の属性やサイトとのインタラクションに基づいて訪問者をフィルタリングするための条件を設定します。 セグメントに条件を設定するには、訪問者をその特性やナビゲーションの特徴に基づいて選別するフィルタールールを設定します。訪問者データをさらに分類するには、各訪問者の特定の訪問やページビューヒットに基づくフィルターを適用します。セグメントビルダーは、これらのサブセットを作成し、ネストされた階層的な訪問者、訪問またはヒット コンテナとしてルールを適用するためのシンプルなアーキテクチャを提供します。

[ セグメントビルダー ](/help/components/segmentation/segmentation-workflow/seg-build.md) で使用されるコンテナアーキテクチャによって、次が定義されます。

- 最も外側のコンテナとして ![User](/help/assets/icons/User.svg)**[!UICONTROL Visitor]** を使用し、訪問およびページビューをまたいで訪問者に固有の包括的なデータを含めます。
- ![訪問](/help/assets/icons/Visit.svg) ネストされた&#x200B;**[!UICONTROL 訪問]**&#x200B;コンテナを使用すると、訪問に基づいて訪問者のデータを分類するルールを設定できます。
- ![WebPage](/help/assets/icons/WebPage.svg) ネストされた **[!UICONTROL ヒット]** コンテナを使用すると、訪問者情報を個々のページビューに基づいて分類できます。

各コンテナでは、訪問者の履歴全体で訪問別に分類されたインタラクションのレポートを作成したり、個々のヒットを分類したりできます。

<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>
</table>

<!--![](assets/sequential_segmentation_container_hierarchy.png)-->


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントコンテナ](https://video.tv.adobe.com/v/3429100?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 訪問者コンテナ

訪問者コンテナには、指定期間内に発生した訪問者による訪問とページビューがすべて含まれます。訪問者レベルのセグメントは、条件を満たすページと、訪問者が閲覧した（かつ、日付範囲の定義によって制限された）ページをすべて返します。訪問者コンテナレベルで生成されたレポートは最も広義のコンテナとして、すべての訪問のページビューを返し、複数回の訪問にわたる分析の生成を可能にします。したがって、訪問者コンテナは、定義された日付範囲に基づく変化の影響を最も受けやすくなります。

訪問者コンテナには、訪問者の履歴全体に基づく値が含まれます。

- 初回購入までの日数
- オリジナルの入口ページ
- オリジナルの参照ドメイン

## 訪問コンテナ

訪問コンテナでは、特定の web セッションのページインタラクション、キャンペーンまたはコンバージョンを識別できます。訪問レベルのセグメントは、条件を満たすページと、訪問セッションの一部として表示される（かつ、定義された日付範囲によってのみ制約される）他のすべてのページを返します。訪問コンテナは、ルールに合致すると訪問セッション全体の行動を取り込むので、最も一般的に使用されるコンテナです。訪問コンテナでは、セグメントの作成と適用に含める訪問と除外する訪問を定義できます。訪問コンテナを使用すると、同じ訪問でニュース＆スポーツセクションを閲覧した訪問者が何人いたか、または購入へのコンバージョンにつながったページが何ページあったかを容易に答えることができます。

訪問コンテナには、1 回の訪問あたりの発生件数に基づく値が含まれます。

- 訪問数
- 入口ページ
- 再来訪頻度
- パーティシペーション指標
- 線形的に割り当てられた指標

## ヒットコンテナ

ヒットコンテナは、セグメントに含めるまたは除外するページヒットを定義します。ヒットコンテナは、条件が成り立つ特定のクリックやページビューの識別に使用できるコンテナの中で最も範囲が狭いものです。単一のトラッキングコードを表示したり、サイトの特定のセクション内での行動を分離したりできます。また、アクションが発生したときの特定の値（注文が発生したときのマーケティングチャネルなど）を把握することもできます。

ヒットコンテナには、単一ページの分類に基づく値が含まれます。

- 製品
- リスト prop
- リスト eVar
- マーチャンダイジング eVar（イベントのコンテキスト内）

  >[!NOTE]
  >
  >このコンテナを持続的な値（eVar など）に対して使用すると、その値が持続するすべてのヒットがコンテナに取り込まれます。1 週間後に有効期限切れになるトラッキングコードがある場合、その値は、複数の訪問にわたって持続する可能性があります。

## 論理グループコンテナ

論理グループコンテナは、セグメントルール内の個別のコンテナを提供して、階層に基づかずにエンティティをフィルタリングするために使用できます。例えば、訪問者に基づいてフィルタリングするセグメント内にネストされたコンテナを提供するとします。この論理タイプでは、（トップレベルの訪問者コンテナを既に使用したので）階層を超えて選択した訪問者のみを選別する必要があります。詳しくは、[論理グループの例](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md)を参照してください。

## コンテナのネスト {#nest-containers}

セグメントコンテナを他のコンテナ内に作成する場合、本質的には、セグメントを他のセグメント内に作成しています。ネストされたコンテナでは、次のロジックが使用されます。

1. どのようなデータが含まれているかを、最も外側にあるコンテナによって調べます。この外部ルールと一致しないデータは、セグメント化レポートですべて削除されます。
1. ネストされたルールを残りのデータに適用します。ネストされたルールは、最初のルールで拒否されたヒットには適用されません。
1. ネストされたコンテナルールがすべて計算されるまで繰り返します。その結果、残りのデータが結果レポートに含まれます。

>[!NOTE]
>
>セグメント内にセグメントをネストすると（例えば、コンポーネント パネルからセグメント定義にセグメントをドラッグすると）、コンテナは、ドラッグしたセグメントルールのコピー（参照ではなく）とともに作成されます。

ネストは、コンテナ間でもコンテナ内のルール間でも使用できます。次に、各コンテナ内でネストできる要素を示します。

| コンテナ名 | コンテナ内でネストできる要素 |
|---|---|
| ヒット | イベントのみ |
| 訪問 | ヒットコンテナ、イベント |
| 訪問者。 | 訪問コンテナ、ヒットコンテナ、イベント |
| 論理グループ | 訪問者コンテナ、訪問コンテナ、ヒットコンテナ |

### 単一の定義に複数のコンテナを含める

新しい複合セグメントに複数のセグメントを含めると、データをさらに正確にできます。既存の 2 つのセグメントをドラッグすると、これらのセグメントは、訪問者のフィルタリングで「OR」ステートメントとして機能します。キャンバス内のすべてのコンテナがすべてのデータと確認され、いずれかまたはいくつかのコンテナと一致するデータがレポートに含まれます。

例えば、Country = United States の訪問コンテナと、Order = True の Visit コンテナをドラッグすると、

```
Country = United States + Order = True
```

次の順序で動作するセグメントが作成されます。

1. まず、データ全体を調べ、米国内のすべての訪問者を識別します。
2. 次に、すべてのデータを再度調べ、訪問者が注文したかどうかを確認します。
3. 次に、両方のデータセットがレポートに適用されます。

## 順次セグメントのコンテナ {#containers-sequential}

順次セグメントでは、階層的にネストされた[!UICONTROL 訪問者数]、[!UICONTROL 訪問回数]および[!UICONTROL ヒット数]（ページビュー数や他のディメンションを含む）などの同じ基本コンテナを使用します。

<table style="table-layout:fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>
</table>

<!--![](assets/nesting_container.png)-->

[!UICONTROL 訪問者数]は順次セグメントにおける最上位のコンテナとなり、[!UICONTROL 訪問回数]コンテナが[!UICONTROL 訪問者数]コンテナ内に含まれ、[!UICONTROL ヒット数]コンテナが[!UICONTROL 訪問者数]または[!UICONTROL 訪問回数]コンテナ内に含まれます。適切に順序付けされた順次セグメントを作成するには、この[コンテナ階層](/help/components/segmentation/seg-overview.md#section_7FDF47B3C6A94C38AE40D3559AFFAF70)を維持する必要があります。

**順次セグメントを作成するには**、コンテナをネストし、[!UICONTROL THEN] 演算子を使用して順次ロジックを結合します。この演算子では、訪問者のシーケンスに基づいて各コンテナが `true` であることが必要です。

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">THEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>
</table>

<!--![](assets/sequential_segmentation_nesting_3.png)-->

このコンテナ階層の唯一の例外は、[論理グループコンテナ](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md)を使用する場合です。[!UICONTROL 論理グループ]コンテナでは、コンテナ内で順序なしでヒットをネストして、イベントやディメンションを非順次に取り込むことができます。

<table style="table-layout:fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 訪問者</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">THEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Group_18_N.svg"/> グループ</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"/> ヒット数</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 訪問回数</td>
</tr>

</table>

<!--![](assets/logic_group_hierarchy.png)-->

## コンテナデータに基づくレポート {#reports}

コンテナを使用すると、セグメントを分類してレポートに適用するときに、レポート値に基づいて様々なデータを様々な方法でフィルタリングできます。

訪問者／訪問／ヒットコンテナの階層構造の各レベルで収集されるデータは、セグメントの作成方法に影響します。同じデータセットを使用して、同じセグメントを同じレポートに適用しても、レポートの生成時に基になるコンテナに応じて異なる値が得られます。コンテナレポートのレベルや、ヒット全体での値の永続化などの要素が、レポートの精度に大きな変化をもたらす可能性があります。

### コンテナデータの基本事項 {#container-data}

例えば、次の図に示す訪問者は、サイトの初回訪問時に、ランディングページとしてホームページを開き、さらに 3 つのページを訪問して購入にいたっています。別の訪問では、今回は商品ページを通じてランディングし、ホームページに移動した後、再度商品ページに移動し、冬用帽子を見た後で、セッションを終了しています。セグメントのコンテナごとに取り込まれたデータに応じて、レポートには様々な値が表示されます。

以下の `Pages equals Winter Coat` セグメントは、**ページレポート**&#x200B;に適用されます。


選択されたコンテナに基づき、レポートには、訪問者による以下の訪問とページビューに関する異なる結果が表示されます。

<table style="table-layout:auto; border: 0;">

<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;" colspan="4"><b>訪問 1</b></td>
</tr>
<tr>
<tr>
<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/>
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>ホーム</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物コート</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>購入額 100 ドル</td>
</tr>
<tr>
<td colspan="5">
</tr>
<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;"colspan="4"><b>訪問 2</b></td>
</tr>
<tr>
<tr style="border: 0;">

<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/>
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬用ブーツ</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>冬用帽子</td>

</table>


<!--![](assets/container_overview.png)-->

### ヒットコンテナからのレポート作成

この条件がヒットコンテナ内にある場合、レポートには *ページ = Winter Coats* が真になるページのみが示されます。1 ページのみが収集されるコンテナ内には、この条件と一致するページが 1 ページしかないので、冬用コートページのみが表示されます。

| ページ | ページビュー数 |
|---|--:|
| 冬物コート | 1 |

<!--![](assets/container_overview_PV.png)-->

ヒットコンテナからレポートを作成すると、様々なコンテナからのレポート作成がレポート値全体にどのような影響を及ぼすかを確認できます。セグメントレポートを表示すると、ページビュー数は訪問回数とほぼ同じになります（1 回の訪問で約 2,000 人の訪問者が重複するページを閲覧し、その結果がページビューの合計数になります）。また、ユニーク訪問者数は、訪問回数とほぼ同じです（約 2,000 人のユニーク訪問者が 2 回以上訪問しています）。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者： | **69,252 件**（351,292 件中）<br/>**67,554 件**（165,175 件中）<br/>**63,541 件**（113,169 件中） | **19％**<br/>**40％**<br/>**56％** |


<!--![](assets/container_report_PV.png)-->

>[!IMPORTANT]
>
>データの表示方法（ヒットコンテナ、訪問コンテナまたは訪問者コンテナのいずれからデータを表示したか）にかかわらず、この例では、訪問者数はどれも同じ 63,541 人です。どの方法でレポートを生成した場合でも、初回訪問者条件（冬用コートのページを表示した訪問者）は変わりません。このデータサブセットから、様々なレベルのレポートを作成します。

### 訪問コンテナからのレポート

この同じ条件が訪問コンテナ内にある場合、レポートには *ページ = Winter Coats* が真になる訪問のページがすべて示されます。これは冬用コートページをフィルタリングするだけでなく、指定の条件が真になる訪問で訪れた他のページもすべて収集します。この訪問者は、ホーム、製品および購入のページも訪れているので、訪問者コンテナデータを使用してレポートを作成する場合、これらの追加ページもレポートに示されます。

| ページ | ページビュー数 |
|---|--:|
| ホーム | 1 |
| 製品 | 1 |
| 冬物コート | 1 |
| 購入 | 1 |

<!--![](assets/container_overview_visit.png)-->

セグメント値を訪問コンテナから表示すると、ページビュー数が大幅に増加していることがわかります。これは、訪問コンテナからのレポートでは、条件を満たすすべてのページだけでなく、訪問で閲覧された他のページも（各訪問コンテナに収集されたすべてのページビューと共に）すべて識別されるからです。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者： | 351,292 件中&#x200B;**226,193 件** 165,175 件中&#x200B;<br/>**67,554 件** 113,169 件中&#x200B;<br/>**63,541 件** | **64%**<br/>**40%**<br/>**56%** |

<!--![](assets/container_report_Visit.png)-->

### 訪問者コンテナからのレポート

この同じ条件が訪問者コンテナ内にある場合、レポートには&#x200B;*ページ = Winter Coats* が真になる任意の訪問者が閲覧したページがすべて示されます。つまり、訪問者が冬用コートのページを閲覧した場合、訪問者コンテナ内のページ（他の訪問のページビューを含む）がすべて示されます。したがって、条件に一致しないページも、訪問者が以前閲覧したことがあるページなので、レポートに示されます。以前に発生し、条件を明確に満たしていなくても、訪問者コンテナに含まれるページは、レポートにすべて示されます。

| 訪問 1<br/>ページ | <br/>ページビュー数 |
|---|--:|
| ホーム | 1 |
| 冬物アパレル | 1 |
| 冬物コート | 1 |
| 購入 | 1 |

| 訪問 2<br/>ページ | <br/>ページビュー数 |
|---|--:|
| 冬物アパレル | 2 |
| 冬用ブーツ | 1 |
| 冬用帽子 | 1 |

| 訪問 1 + 訪問 2<br/>ページ | <br/>ページビュー数 |
|---|--:|
| 冬物アパレル | 3 |
| ホーム | 1 |
| 冬物コート | 1 |
| 購入 | 1 |
| 冬用ブーツ | 1 |
| 冬用帽子 | 1 |

<!--![](assets/container_overview_visitors.png)-->

セグメントを訪問者コンテナから表示すると、ページビュー数と訪問回数が増加していることがわかります。これは、訪問者レベルで考えると、訪問者が冬用コートのページを閲覧したのは 1 回のみであっても、（条件が true となるので）その訪問者に関する他のすべてのページビューと他のすべての訪問が収集されるからです。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者 | 351,292 件中&#x200B;**240,094 件** 165,175 件中&#x200B;<br/>**83,823 件** 113,169 件中&#x200B;<br/>**63,541 件** | **68%**<br/>**50%**<br/>**56%** |

<!--![](assets/container_report_Visitor.png)-->

これまでの説明をまとめると、様々なデータ分類に対するセグメント化の機能を理解することが、セグメント化が返すデータを解釈するうえで重要となります。

## コンテナに基づくレポート作成 {#reporting}

セグメントデータの分類にはそれぞれ、適用されるスコープがあります。ほとんどのレポート分類は&#x200B;*ページビュー*&#x200B;に基づきますが、重要性の高い多くのセグメントは&#x200B;*訪問*&#x200B;コンテナに基づき、重要性の低いセグメントは&#x200B;*訪問者*&#x200B;コンテナに基づきます。コンテナのスコープに基づくレポート作成について理解することが重要です。

`Page equals Winter Coats` セグメントの例を使用して、コンテナデータの適用方法と、データの範囲がセグメントタイプとどのように一致するかに基づいて、このセグメントの結果の例を以下に示します。

### 一致するセグメントルールに基づくセグメントコンテナ

データの固有スコープに対してセグメントコンテナを適用すると、行項目がセグメントルールと一致する、予測された結果が得られます。

- **ページが「Winter Coat」（冬用コート）に等しいヒットコンテナ**：このセグメントによって&#x200B;*ページ*&#x200B;レポートを表示すると、「Winter Coat」に等しい値のみが返されます。それ以外のページは、レポートからすべて除外されます。
- **入口ページが「Winter Apparel」（冬物衣料）に等しい訪問コンテナ**：このセグメントによって&#x200B;*入口ページ*&#x200B;レポートを表示すると、2 番目の訪問が返されます。これは、入口ページがセグメントルールと一致するからです。
- **通算訪問回数が 1 に等しい訪問コンテナ**：訪問を表示すると、初回訪問からのすべてのページビューがレポートに含まれます。これは、初回訪問がセグメントルールと一致するからです。

### 訪問コンテナレベルでのページビュー

多くのセグメントルールが 1 回の訪問あたりのページビューを識別します。このように識別された場合、単一のヒットがルールと一致するだけで、訪問者コンテナ全体が適用されます。訪問に基づくページビューは、1 回の訪問あたりのページビューに基づいてインサイトを提供するので、このセグメントレポートは特に重要です。

- **ページが「Winter Coat」（冬物コート）ページに等しい訪問コンテナ**：訪問者コンテナレベルでのページレポートには、冬物衣料ページの閲覧を含む訪問のすべてのページビューが表示されます。ページがセグメントルールと一致する場合は、その訪問に関連するページビューがすべてレポートに含まれます。
- **ページが「ホーム」ページに等しいコンテナに訪問します**。このセグメントを含むページレポートでは、2 回目の訪問では訪問者は「ホーム」ページを表示しなかったので、最初の訪問のデータのみが表示されます。
- **ページが「Winter Apparel」（冬物衣料）に等しい訪問者コンテナ**：このセグメントによるページレポートには、両方の訪問からのすべてのデータが抽出されます。これは、両方の訪問で訪問者が冬物衣料ページを閲覧したからです。

### ページビューよりも少ないヒット数を識別するセグメントコンテナ

分類スコープよりも小さいコンテナをセグメントで使用すると、予期しないデータが返されます。さらに小さい分類を使用すると、データのスコープからすべてのヒットが抽出されます。

- **入口ページが Product（商品）ページに等しいヒットコンテナ**：すべてのページが訪問の入口ページに関連し、訪問ベースの分類になります。このセグメントを使用すると、入口となるページの製品ページだけでなく、その訪問のすべてのヒットも抽出されます。
- **リスト変数 1 に値 1 が含まれるヒットコンテナ**：複数の値がリスト変数と同じヒットに定義されている場合、セグメントにはすべての変数値が含まれます。ヒットを分類する最小のセグメントコンテナはヒットコンテナなので、同じページビューで発生する値を分類する方法はありません。
- **ページが「Purchase」（購入）に等しいヒットコンテナ**：ページビューを指標として使用すると、購入ページのみが表示されます（予測された動作）。パーティシペーション指標は訪問ベースなので、売上高パーティシペーションレポートを使用すると、初回訪問のすべてのページが $100 を受け取ります。
- **ページが「Winter Coat」（冬物コート）に等しいヒットコンテナ**：ページビューを指標として使用すると、冬物コートページのみが表示されます（予測された動作）。このディメンションは持続的なディメンションを必要とするので、売上高パーティシペーションレポートを使用すると、どのページもクレジットを受け取りません。実際に購入が行われた（購入ページの）ページビューは、ヒットコンテナに含まれないので、売上高パーティシペーションレポートはどの項目にも与えられません。ただし、訪問コンテナからレポートを実行すると、その訪問のすべてのページビューが含まれて、セッションで閲覧されたページ全体で売上高パーティシペーション（$100）が分散されます。

## コンテナ間での持続性 {#persistence}

キャンペーン eVar や、参照ディメンションなど、ページの範囲間で持続するディメンションを使用したフィルタリングは、コンテナレベルで収集されるデータに影響します。精度の高いレポートを作成するには、こうしたフィルタリングについて理解する必要があります。

セグメントデータは、選択されたページ間でディメンションや適用される変数の持続性に応じて変化します。ページディメンションなどのディメンションは、ページレベルで一意の値を提供し、ヒットコンテナのデータに基づいてフィルタリングされます（[コンテナデータに基づくレポート](/help/components/segmentation/seg-overview.md)の例を参照してください）。また、参照ドメインディメンションなどのディメンションは、訪問の複数のページ間で持続します。例：`Referring Domain equals aol.com`。訪問期間などのディメンションや適用される変数は、訪問者の履歴全体に及びます。

<!--![](assets/RefDomain_aol.png)-->

ページディメンションとは異なり、参照ドメイン値は、この訪問の各ページに添付されます。例えば、次の訪問者は、ある参照元サイトから Home ページを訪問しています。したがって、この訪問のすべてのページに、同じ参照ドメイン値が割り当てられます。

`Referring Domain equals aol.com` 以下のセグメントは、**ページレポート**&#x200B;に適用されます。

<table style="table-layout:fixed; border: 0;">

<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;" colspan="4"><b>訪問 1</b></td>
</tr>
<tr>
<tr>
<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/><br/>aol.com
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>ホーム</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物コート</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>購入額 100 ドル</td>
</tr>
<tr>
<td colspan="5">
</tr>
<tr>
<td style="background-color: #E5E4E2;"></td>
<td style="background-color: #E5E4E2;"colspan="4"><b>訪問 2</b></td>
</tr>
<tr>
<tr style="border: 0;">

<td style="background-color: #E5E4E2;">
<img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/><br/>weather.com
</td>
<td style="background-color: #FFFFFF; "><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬用ブーツ</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><img align="right" src="https://spectrum.adobe.com/static/icons/ui_18/ArrowSize100.svg"/><br/>冬物アパレル</td>
<td style="background-color: #FFFFFF;"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg"><br/>冬用帽子</td>

</table>

<!--![](assets/container_overview_persist.png)-->

新しい訪問では、訪問者は別のサイトから参照されます。したがって、新しい訪問のすべてのページに、各ページビューの新しい参照ドメイン値が割り当てられます。

### ヒットコンテナからのレポート作成

同じ訪問のすべてのページビューに、同じ参照ドメイン値が割り当てられるので、`Referring Domain equsls 'aol.com'` となるヒットコンテナレベルでのレポートは、次の表に示すように、すべてのページを返します。

| 参照ドメイン = &#39;aol.com&#39; | ページビュー数 |
|----|---:|
| ホーム | 1 |
| 冬物アパレル | 1 |
| 冬物コート | 1 |
| 購入 | 1 |

<!--![](assets/container_overview_persist_Visit.png)-->

ヒットコンテナのデータを見ると、32,000 人を超える訪問者による 33,000 回を超える訪問回数で 92,000 回を超えるページビューが閲覧されています。平均では、訪問ごとのページビューは 3 回で、ほとんどすべての訪問がユニーク訪問者によって行われています。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者： | 351,165 件中&#x200B;**98,234 件** 165,173 件中&#x200B;<br/>**33,203 件** 113,110 件中&#x200B;<br/>**32,269 件** | **27%**<br/>**20%**<br/>**28%** |

<!--![](assets/container_report_persist_PV.png)-->

### 訪問コンテナからのレポート

この同じ条件が訪問コンテナでページレポート用にフィルタリングされると、`Referring Domain equals 'aol.com'` が true になる訪問のすべてのページが対象となります。参照ドメインの値は、訪問レベルで設定されるので、ページビューレベルと訪問レベルでのレポートは同じです。

| 参照ドメイン = &#39;aol.com&#39; | ページビュー数 |
|----|---:|
| ホーム | 1 |
| 冬物アパレル | 1 |
| 冬物コート | 1 |
| 購入 | 1 |

<!--![](assets/container_overview_persist_Visit.png)-->

どのページも、訪問に基づく同じ参照ドメイン値を持つため、訪問コンテナレベルからのレポートは、ページビューコンテナからのレポートと（ほとんど）同じです。データの異常が原因のオフセットが若干（98,234 対 98,248）があります。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者： | 351,165 件中&#x200B;**98,248 件** 165,173 件中&#x200B;<br/>**33,203 件** 113,110 件中&#x200B;<br/>**32,269 件** | **27%**<br/>**20%**<br/>**28%** |

<!--![](assets/container_report_persist_Visit.png)-->

### 訪問者コンテナからのレポート

訪問者コンテナから、ページレポートには、`Referring Domain equals 'aol.com'` がtrue である任意の訪問者が閲覧したページがすべて示されます。したがって、訪問者が（定義された期間内の）履歴のいずれかの時点で&#x200B;*「aol.com」*&#x200B;を参照ドメインとして持つ場合、訪問者コンテナに含まれるすべてのページ（他の訪問でのページビューを含む）が示されます。第一条件に一致しないページも、訪問者コンテナに含まれるページなので、レポートに一覧表示されます。訪問者コンテナ内のすべてのページは、以前に発生し、条件を特に満たしていない場合でも、レポートに一覧表示されます。

参照ドメインレポートでは、4 つのページビューで `Referring Domain equals 'aol.com'` が true ですが、訪問者がヒットした他のページでは `Referring Domain equals "weather.com"` が true です。「訪問者」コンテナから、「aol.com」が true の訪問者のリストを取得します。また、参照ドメインが「weather.com」であるページも表示されます。セグメント内の最初のリクエストに一致した値ではありません。

| 訪問 1<br/> 参照ドメイン =「aol.com」 | <br/>ページビュー数 |
|----|---:|
| ホーム | 1 |
| 冬物アパレル | 1 |
| 冬物コート | 1 |
| 購入 | 1 |

| 訪問 2<br/> 参照ドメイン =「weather.com」 | <br/>ページビュー数 |
|----|---:|
| 冬物アパレル | 2 |
| 冬物コート | 1 |
| 購入 | 1 |

| 訪問者コンテナ<br/>参照ドメイン =「aol.com」 | ページビュー数 |
|----|---:|
| 冬物衣料<br/>参照ドメイン：「aol.com」 | 1 |
| 冬物衣料<br/>参照ドメイン：「weather.com」 | 1 |
| ホーム<br/>参照ドメイン：「aol.com」 | 1 |
| 冬用コート<br/>参照ドメイン：「aol.com」 | 1 |
| 購入<br/>参照ドメイン：「aol.com」 | 1 |
| 冬用ブーツ<br/>参照ドメイン：「weather.com」 | 1 |
| 冬用帽子<br/>参照ドメイン：「weather.com」 | 1 |


<!--![](assets/container_overview_persist_Visitor.png)-->

訪問者コンテナのデータを表示すると、ページビューが（98,248 から 112,925 に）大幅に増加していることに注意してください。この増加は、訪問者によるすべてのページビュー（訪問者コンテナレベルで保存された他の参照ドメイン値を持つページを含む）がリストされたからです。さらに、その訪問者による追加の訪問数が 33,203 から 43,448 に増加しています。

| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphDonut_18_N.svg"/> | 指標 | # | ％ |
|---|---|--:|--:|
| | ページビュー：<br/>ビュー：<br/>ユニーク訪問者： | 351,165 件中&#x200B;**112,925 件** 165,173 件中&#x200B;<br/>**43,448 件** 113,110 件中&#x200B;<br/>**32,269 件** | **32%**<br/>**26%**<br/>**28%** |

<!--![](assets/container_report_persist_Visitor.png)-->

## 概要

- 訪問者コンテナは、少なくとも 1 つのページが条件を満たす訪問者に閲覧されたすべてのページを返します。したがって、あるページが 1 日目の 訪問 1 でしか閲覧されていない場合でも、その訪問者が複数の訪問で閲覧したすべてのページがデータに含まれます。
- 訪問コンテナは、訪問で表示されたすべてのページのうち、少なくとも 1 つのページが条件を満たすページを返します。したがって、あるページが 1 日目の 訪問 1 でしか閲覧されていない場合でも、訪問全体で閲覧されたすべてのページがデータに含まれます。
- セグメント化に使用する条件は、eVar またはその他のタイプの永続変数に基づいて行うように注意してください。例えば、「キャンペーンにメールを含む」という条件を使用すれば、キャンペーンは 7 日後に有効期限切れとなります。この場合、初回訪問時にキャンペーンが設定されると、キャンペーンはさらに 7 日間継続します。キャンペーンが初回訪問時にのみ設定された場合も、各訪問が含まれます。他の訪問も含まれます（これらの訪問がレポートの日付範囲に含まれている場合）。持続的な値を排除して含めないようにする場合は、イベントのインスタンスを使用するか、同等の Prop 変数があれば、その Prop 変数を使用します。
