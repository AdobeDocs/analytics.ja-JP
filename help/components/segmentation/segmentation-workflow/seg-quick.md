---
description: Analysis Workspaceのクイックセグメントの使用方法を説明します。
title: クイックセグメント
feature: Segmentation
role: User
exl-id: ce487fa0-dd81-44e4-a684-90979afaeb07
TQID: https://experienceleague.adobe.com/hxMHHZM2tzrv7RRhK3sToyihGG12i0KVzSzN8LNnlCk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 917804b359e040bc04282fe69e05a1a4b6e9bdc4
workflow-type: tm+mt
source-wordcount: 1292
ht-degree: 17%

---

# クイックセグメント


クイックセグメントを使用すると、[&#x200B; セグメントビルダー](seg-create.md)でセグメントを作成しなくても、Workspace プロジェクト内のデータをすばやく探索できます。



>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のクイックセグメント](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/applying-segments/quick-segments-in-analysis-workspace){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


クイックセグメントを使用する場合は、次の点に注意してください。

* クイックセグメントは、Workspace プロジェクトで直接作成されます。 そのため、クイックセグメントは、クイックセグメントを作成するWorkspace プロジェクトにのみ適用されます。 Workspace プロジェクトのクイックセグメントは、他のプロジェクトでは使用できず、他のユーザーと共有することはできません。
* クイックセグメントの一部として指定できる条件は3つだけです。
* クイックセグメントは、ネストされたコンテナや連続条件をサポートしていません。
* クイックセグメントは、共有Workspace プロジェクト内で編集できます。 そのため、他のユーザーは、これらのユーザーと共有したWorkspace プロジェクト内のクイックセグメントを編集できます。

## 作成

クイックセグメントはパネルに適用されます。 Workspace プロジェクトの各パネルに1つ以上のクイックセグメントを作成できます。 Analysis Workspaceなら、誰でもクイックセグメントを作成できます。

クイックセグメントを作成するには、次の手順に従います。

* パネルの上部にある![SegmentAdd](/help/assets/icons/FilterAdd.svg)を選択します。 <br/>次に、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)でセグメントを直接編集します。
* コンポーネントをコンポーネントパネルからパネルヘッダーのセグメントドロップゾーンにドラッグします。 ドロップしたら、セグメントにカーソルを合わせ、![編集](/help/assets/icons/Edit.svg)を選択して、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)でセグメントを編集します。

ドラッグ&amp;ドロップを使用してクイックセグメントを作成する場合は、次の点に注意してください。

* すべてのコンポーネントタイプがサポートされているわけではありません。 計算指標はサポートされておらず、セグメントを構築できるディメンションと指標のみがサポートされています。
* ディメンションと指標コンポーネントの場合、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)は&#x200B;**[!UICONTROL exists]**&#x200B;条件を自動的に作成します。 例えば、**[!UICONTROL City]**&#x200B;をドラッグ&amp;ドロップすると、条件&#x200B;**[!UICONTROL City]** **[!UICONTROL exists]**&#x200B;が作成されます。
* ディメンション値の場合、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)は自動的に&#x200B;**[!UICONTROL イコール]**&#x200B;条件を作成します。 例えば、**[!UICONTROL City]** ディメンション項目から&#x200B;**[!UICONTROL amsterdam]**&#x200B;をドラッグ&amp;ドロップすると、条件&#x200B;**[!UICONTROL City]** **[!UICONTROL equals]** `Amsterdam`が作成されます。
* **[!UICONTROL unspecified]**&#x200B;または&#x200B;**[!UICONTROL none]**&#x200B;をドラッグ&amp;ドロップすると、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)は&#x200B;**[!UICONTROL 存在しない]**&#x200B;条件を自動的に作成します。

作成したクイックセグメントは、パネルの上部に表示されます。 クイックセグメントの左バーには、薄い薄い水色のバーがあります。 [&#x200B; クイックセグメントビルダー](#quick-segment-builder)を使用してクイックセグメントを編集モードにすると、クイックセグメントの背景が薄い青色になります。

パネルで作成したクイックセグメントの結果は、パネルの一部であるすべてのビジュアライゼーションに（AND ロジックを使用して）適用されます。


## 管理

クイックセグメントを管理するには、特定の&#x200B;**[!UICONTROL クイックセグメント]**&#x200B;にカーソルを合わせます。

* ![編集](/help/assets/icons/Edit.svg)を選択して[&#x200B; クイックセグメントビルダー](#quick-segment-builder)を開き、クイックセグメントを編集します。
* ![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択して、ポップアップを開きます。 ポップアップには、セグメントに関する情報が表示されます。 **[!UICONTROL すべてのプロジェクトで使用できるようにし、コンポーネントリストに追加できます]** コンポーネントパネルの![&#x200B; セグメント &#x200B;](/help/assets/icons/Segmentation.svg) **[!UICONTROL セグメント]** コンポーネントリストにセグメントを追加するには、 **[!UICONTROL クイックセグメントを保存]** ダイアログが表示され、セグメントの名前を指定するよう求められます。 「**[!UICONTROL 保存]**」を選択して続行します。 [!UICONTROL &#x200B; クイックセグメント &#x200B;]が&#x200B;**[!UICONTROL セグメント]**&#x200B;に変わります。 [&#x200B; クイックセグメントビルダー](#quick-segment-builder)を使用してセグメントを編集することはできません。 代わりに、[&#x200B; セグメントビルダー](seg-build.md)を使用して、セグメントを通常のセグメントとして編集する必要があります。

## クイックセグメントビルダー

クイックセグメントビルダーの例については、以下を参照してください。 この例では、`Interaction Channel = Website  AND Online Orders is greater than 1`というタイトルのクイックセグメントに対してビルダーが開きます。 上部のクイックセグメントは、**[!UICONTROL 平均注文額ダッシュボード]** パネルおよび内のすべてのビジュアライゼーションに適用されます。

![クイックセグメントビルダー](assets/quick-segment-builder.png)

クイックセグメントビルダーは、次の領域とボタンで構成されています。

### ヘッダー領域

ヘッダー領域によって、クイックセグメントの名前、タイプ、範囲が決まります。 また、クイックセグメントの結果のビジュアルも表示されます。

| 要素 | 説明 |
|---|---|
| **[!UICONTROL 名前]** | 名前は、クイックセグメント定義から自動的に取得されます。 |
| **[!UICONTROL _指標_]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![&#x200B; アラート &#x200B;](/help/assets/icons/Alert.svg) | クイックセグメントから得られる指標データのプレビュービジュアル。 全体のデータがクイックセグメントの結果にどの程度含まれているかを示す棒グラフとパーセンテージがinsightに表示されます。 ![&#x200B; アラート &#x200B;](/help/assets/icons/AlertRed.svg)は、クイックセグメントがデータを返さないことを示します。 |
| **[!UICONTROL 含む]**<br/>**[!UICONTROL 除外]** | ドロップダウン ![ChevronDown](/help/assets/icons/ChevronDown.svg)から、クイックセグメントの結果をパネルのデータに含めるか除外するかを選択します。 |
| **[!UICONTROL イベント &#x200B;]**<br/>**[!UICONTROL &#x200B; セッション &#x200B;]**<br/>**[!UICONTROL 人物]**<br/>**[!UICONTROL 製品]** | ドロップダウンメニュー![ChevronDown](/help/assets/icons/ChevronDown.svg)から、クイックセグメントの範囲を選択します。 [&#x200B; サブヒット分析](/help/components/segmentation/sub-hit.md)のユースケースに&#x200B;**[!UICONTROL 製品]**&#x200B;を使用します。<ul><li>製品ディメンションまたは製品指標をクイックセグメントパネルにドラッグすると、**[!UICONTROL 製品]** コンテナが自動的に選択され、デフォルトの&#x200B;**[!UICONTROL ヒット]** コンテナは使用されません。 この動作により、ヒット全体ではなく、個々の製品に対してセグメントの範囲が維持されます。</li><li>製品レベルとヒットレベルの両方のコンポーネントを単一のセグメントルールにドラッグすると、システムは、最も高い（最小の）共有コンテナである&#x200B;**[!UICONTROL ヒット]** コンテナを使用します。 セグメントルールに含まれるすべてのコンポーネントが製品レベルの場合、**[!UICONTROL 製品]** コンテナが使用されます。</li></ul> |

### 条件領域

条件領域では、条件（最大 3 つまで）を指定します。 各条件に対して、次の項目を指定できます。

| 要素 | 説明 |
|---|---|
| **[!UICONTROL ディメンション]**<br/>**[!UICONTROL 指標]**<br/>**[!UICONTROL 日付範囲]** | ディメンション、指標または日付範囲の条件を指定するかどうかをドロップダウンメニュー![ChevronDown](/help/assets/icons/ChevronDown.svg)から選択します。 |
| **[!UICONTROL *コンポーネント&#x200B;*]** | 条件のコンポーネントフィールド。 コンポーネントを&#x200B;[!UICONTROL *入力して追加*]&#x200B;したり、リストからコンポーネントを選択したり、コンポーネントパネルからコンポーネントをドラッグ＆ドロップしたりすることができます。 条件のコンポーネントフィールドにドロップできるのは、類似のコンポーネントのみです。 例えば、ディメンション条件では、コンポーネントパネルからディメンションコンポーネントのみをドロップできます。 <br/>また、既存のコンポーネントをドラッグ＆ドロップして置き換えることもできます。<br/>コンポーネントフィールドからコンポーネントを削除するには、![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択します。 |
| **[!UICONTROL *演算子&#x200B;*]** | コンポーネントの演算子。 詳しくは、[演算子](../seg-reference/seg-operators.md)を参照してください。 ディメンションと指標でのみ使用できます。 |
| **[!UICONTROL *value *]** | 条件の値。 選択した演算子に応じて、リストから値を選択するか、値を入力します。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | クイックセグメントから条件を削除する場合に選択します。 |

### ボタン

| ボタン | 説明 |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | 複数の条件を定義した場合にのみ使用できます。 条件の間のドロップダウンメニュー![ChevronDown](/help/assets/icons/ChevronDown.svg)から選択します。 選択によって、クイックセグメントのブーリアンロジックが決まります。 条件が 3 つある場合は、ロジックを混在させることはできません。 ブール論理は **[!UICONTROL AND]** または **[!UICONTROL OR]** のいずれかです。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | クイックセグメントに別の条件を追加します。 このボタンは、クイックセグメントに1つまたは2つの条件を定義した場合にのみ使用できます。 |
| **[!UICONTROL 適用]** | クイックセグメントに変更を適用します。 |
| **[!UICONTROL ビルダーを開く]** | **[!UICONTROL 確認を求めるメッセージが表示されます。よろしいですか？]** ダイアログ： **[!UICONTROL OK]**&#x200B;を選択した場合、[&#x200B; クイックセグメントビルダー](#quick-segment-builder)でセグメントを変更できなくなりました。クイックセグメントの名前は&#x200B;**[!UICONTROL セグメント]**&#x200B;に変更され、左バーは青色で薄くなります。<br/>通常の[&#x200B; セグメントビルダー](seg-build.md)が開き、「**[!UICONTROL このセグメントをすべてのプロジェクトで使用できるようにし、コンポーネントリストに追加する]**」オプションが表示されます。 <ul><li>このオプションを選択して&#x200B;**[!UICONTROL 適用]**&#x200B;を選択すると、コンポーネントパネルの![&#x200B; セグメント &#x200B;](/help/assets/icons/Segmentation.svg) **[!UICONTROL セグメント]** コンポーネントリストにセグメントが追加されます。</li><li>このオプションを選択せずに&#x200B;**[!UICONTROL 適用]**&#x200B;を選択した場合、セグメントはWorkspace プロジェクト専用のセグメントのままになります。</li></ul> |
| **[!UICONTROL キャンセル]** | クイックセグメントの作成または編集をキャンセルする場合に選択します。 |

## クイックセグメントとセグメントの比較

クイックセグメントには、名前が付けられています。 クイックセグメントをすばやくインラインで作成および編集し、パネルですぐに効果を確認できます。

セグメントには、クイックセグメントと比較して次のような利点があります。

* セグメントは、あらゆるWorkspace プロジェクトで利用できます
* セグメントは、ネストされた階層的な[&#x200B; コンテナ &#x200B;](../seg-containers.md)とシーケンス（[&#x200B; シーケンシャルセグメント &#x200B;](seg-sequential-build.md)を使用）を使用して、より複雑な処理をサポートします。
