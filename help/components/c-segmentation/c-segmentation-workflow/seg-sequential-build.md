---
description: 順次セグメントは、ANDまたはORの代わりにTHEN演算子を使用して作成されます。 THENは、1つのセグメント条件が発生し、次に別のセグメント条件が発生することを意味します。 デフォルトでは、順次セグメントは、フィルター「全員を含む」を表示し、合致するすべてのデータを識別します。順次セグメントは、「シーケンスの前のみ」および「シーケンスの後のみ」オプションを使用して、さらに合致するヒットのサブセットにフィルタリングできます。
title: 順次セグメントの構築
topic: Segments
uuid: 7fb9f1c7-a738-416a-aaa2-d77e40fa7e61
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 順次セグメントの構築

順次セグメントは、ANDまたはORの代わりにTHEN演算子を使用して作成されます。 THENは、1つのセグメント条件が発生し、次に別のセグメント条件が発生することを意味します。 デフォルトでは、順次セグメントは、フィルター「全員を含む」を表示し、合致するすべてのデータを識別します。順次セグメントは、「シーケンスの前のみ」および「シーケンスの後のみ」オプションを使用して、さらに合致するヒットのサブセットにフィルタリングできます。

![](assets/before-after-sequence.png)

さらに、[After および Within 演算子](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)を使用して、特定の期間、精度およびチェックポイント間のカウントに順次セグメントを制限することができます。

## 全員を含む {#section_75ADDD5D41F04800A09E592BB2940B35}

「全員を含む」が設定されているセグメントを作成すると、そのセグメントでは指定されたパターン全体と一致するパスを識別します。これは、同じ訪問者が訪問したヒット（ページA）の後に別のヒット（ページB）が続く基本的なシーケンスセグメントの例です。 セグメントが「全員を含む」に設定されている。

![](assets/sequence-filter.png)

| 結果が次の場合： | シーケンス |
|--- |--- |
| 一致する | A -><br>A -> （別の訪問で）B<br>A -> D -> B |
| 一致しない | B -> A |

## シーケンスの前のみ、シーケンスの後のみ {#section_736E255C8CFF43C2A2CAAA6D312ED574}

オプションとフ **[!UICONTROL Only Before Sequence]** ィルタリ **[!UICONTROL Only After Sequence]** ングを使用して、指定したシーケンスの前後のデータのサブセットにセグメントを適用します。

* **シーケンスの前のみ**：シーケンスの前のすべてのヒットおよびシーケンス自体の最初のヒットが含まれます（例 1、3 を参照）。1 つのパスにシーケンスが複数回現れる場合、「シーケンスの前のみ」には、最後のシーケンスの最初のヒットおよびそれ以前のすべてのヒットが含まれます（例 2 を参照）。
* **シーケンスの後のみ**：シーケンスの後のすべてのヒットおよびシーケンス自体の最後のヒットが含まれます（例 1、3 を参照）。1 つのパスにシーケンスが複数回現れる場合、「シーケンスの後のみ」には、最初のシーケンスの最後のヒットおよびそれ以後のすべてのヒットが含まれます（例 2 を参照）。

例えば、B -> Dのシーケンスを考えてみましょう。この3つのフィルターは、次のようにヒットを識別します。

**例1:B -> D**

| 例 | A | B | C | D | E | 金 |
|---|---|---|---|---|---|---|
| 全員を含む | A | B | C | D | E | 金 |
| シーケンスの前のみ | A | B |  |  |  |  |
| シーケンスの後のみ |  |  |  | D | E | 金 |

**例2:B -> Dが複数回出現する**

| 例 | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| 全員を含む | A | B | C | D | B | C | D | E |
| シーケンスの前のみ | A | B | C | D | B |  |  |  |
| シーケンスの後のみ |  |  |  | D | B | C | D | E |

また、この概念をヒットの深さディメンションに当てはめてみましょう。

**例 3：ヒットの深さ 3 の後に 5**

![](assets/hit-depth.png)

## ディメンション制約 {#section_EAFD755F8E674F32BCE9B642F7F909DB}

「within」句の「THEN」ステートメントの間に、例えば「within 1 search keyword instance（1 個の検索キーワードのインスタンス内）」や「within 1 eVar 47 instance（1 個の eVar 47 インスタンス内）」というように追加できます。これにより、ディメンションの 1 個のインスタンス内にセグメントが制限されます。

ルールの間に「Within ディメンション」句を設定したセグメントでは、その句を満たすシーケンスにデータを制限できます。制約が「Within 1 page（1 ページ内）」に設定されている以下の例を参照してください。

![](assets/sequence-filter4.png)

| 結果が次の場合： | シーケンス |
|--- |--- |
| 一致する | A -> B |
| 一致しない | A -> C -> B （B は A から 1 ページ以内ではなかったため）<br>**注：**ディメンションの制限を取り除くと、「A -> B」と「A -> C -> B」の両方が一致します。 |

## 単純なページビューシーケンス

あるページを訪問者し、別のページを閲覧した訪問者を特定します。 以前、過去、または中間の訪問セッション、または間に発生したページ表示の時間や数に関係なく、ヒットレベルのデータによってこのシーケンスがフィルタリングされます。

**例**：訪問者がページ A を閲覧し、さらに、同じまたは別の訪問内でページ B を閲覧します。

**使用例**

次に、セグメントの使用例を示します。

1. 訪問者は、スポーツのサイト表示にフットボールランディングページをし、次にバスケットボールランディングページを順次表示しますが、同じ訪問である必要はありません。 これにより、キャンペーンはフットボールシーズン中にフットボールの視聴者にバスケットボールのコンテンツをプッシュするように求められます。
1. 自動車小売業者は、顧客忠誠度ページにランディングし、その後、その訪問中または別の訪問中にビデオページに移動した訪問者の関係を識別します。

**このセグメントを作成**

You nest two page rules within a top-level [!UICONTROL Visitor] container and sequence the page hits using the [!UICONTROL THEN] operator.

![](assets/segment_sequential_1.png)

## 複数の訪問にまたがる訪問者シーケンス

キャンペーンからフォールアウトしたが、別のセッションでこのページビューのシーケンスに戻ってきた訪問者を識別します。

**例**：訪問者がある訪問でページ A を閲覧し、その後別の訪問でページ B を閲覧した。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* 訪問者がニュースサイトのスポーツページに移動し、別のセッションでスポーツページが再訪されます。
* ある衣料品店では、あるセッションでランディングページにランディングし、別のセッションでチェックアウトページに直接移動した訪問者間の関係を確認します。

**このセグメントを作成**

This example nests two **[!UICONTROL Visit]** containers within the top-level **[!UICONTROL Visitor]** container and sequences the segment using the [!UICONTROL THEN] operator.

![](assets/visitor_seq_across_visits.png)

## 混合レベルシーケンス

不明な訪問回数の間に 2 つのページを閲覧し、さらに別の訪問で 3 ページ目を閲覧した訪問者を識別します。

**例**：訪問者は 1 回以上の訪問でページ A に続き、ページ B を訪問し、さらに別の訪問でページ C を訪問した。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* 訪問者は最初にニュースサイトを訪問し、次に同じ訪問で表示ページを訪問します。 別の訪問で、訪問者は天気ページを訪問します。
* 小売業者は、訪問者が「メイン」ページを入力し、「マイアカウント」ページに移動するユーザーを定義します。 別の訪問では、買い物かごページを表示します。

**このセグメントを作成**

1. 左側のパネルから2つのページディメンションを最上位レベルのコンテナにドロップ [!UICONTROL Visitor] します。
1. 2追加つの間のTHEN演算子。
1. /をクリ **[!UICONTROL Options]** ック **[!UICONTROL Add container]** し、レベルの下に [!UICONTROL Visit] コンテナを追加し、演 [!UICONTROL Visitor] 算子を使用して順番に並べ [!UICONTROL THEN] ます。

![](assets/mixed_level_checkpoints.png)

## 集計コンテナ

コンテナ内に複数の [!UICONTROL Hit] コンテナを追加すると、同じタイプのコンテナ間で適切な演算子を使用し、ページや訪問回数などのルールやディメンションを使用して、ページ表示を定義し、コンテナ内にシーケンスディメンションを指定でき [!UICONTROL Visitor][!UICONTROL Hit] ます。 ヒットレベルでロジックを適用すると、コンテナ内の同じレベルのヒットに対する一致を制限および組み合わせて、様々なセグメントタ [!UICONTROL Visitor] イプを作成できます。

**例**:訪問者は、ページ表示のシーケンスの最初のヒット（この例ではページD）の後にページAを訪問し、その後、訪問回数に関係なく、ページBまたはページCのいずれかを訪問した。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* ある訪問でメインランディングページに移動し、次の訪問で男性用衣料品ページの表示を行い、次に別の訪問で女性用ランディングページまたは子供用の表示を行う訪問者を識別します。
* e-zineは、ある訪問でホームページに、別の訪問でスポーツページ、別の訪問でオピニオンページに移動した訪問者を収集します。

**このセグメントを作成**

1. 最上位レベルの [!UICONTROL Visitor] コンテナとしてコンテナを選択します。
1. 2レ追加ベルのコンテナ- [!UICONTROL Hit]and演算子で同じレベルで結合された適切な数値ディメンション [!UICONTROL Hit] を持つディメ [!UICONTROL AND] ンション [!UICONTROL OR] 。
1. コンテナ内で、 [!UICONTROL Visit] 別のコンテナを追加し、ま [!UICONTROL Hit] たは演算子で結合された2つの追加 [!UICONTROL Hit] コンテナをネ [!UICONTROL OR] スト [!UICONTROL AND] します。

   演算子を使用して、これらのネストさ [!UICONTROL Hit] れたコンテナのシーケンスを [!UICONTROL THEN] 作成します。

![](assets/aggregate_checkpoints2.png)

## 順次セグメントの「ネスト」

By placing checkpoints at both the [!UICONTROL Visit] and [!UICONTROL Hit] level, you can constrain the segment to meet requirements within a specific visit as well as a specific hit.

**例**：訪問者がページ A に訪問した後、その同じ訪問内でページ B に訪問し、さらに別の訪問でページ C にアクセスした。

**このセグメントを作成**

1. Underneath a top-level [!UICONTROL Visit] container, drag in two page dimensions.
1. 両方のルールを複数選択し、/をク **[!UICONTROL Options]** リックし **[!UICONTROL Add container from selection]** て、ルールを [!UICONTROL Visit] コンテナに変更
1. 演算子で結合し [!UICONTROL THEN] ます。
1. ヒットコンテナをコンテナのピアとして作成し、ペ [!UICONTROL Visit] ージディメンションをドラッグします。
1. 別の演算子を使用して、ネストされた [!UICONTROL Visit] コンテナ内のシーケ [!UICONTROL Hit] ンスをコンテナと結 [!UICONTROL THEN] 合します。

![](assets/nesting_sequential_seg.png)

## ヒットの除外

セグメントルールには、ルールを使用して特にデータを除外、除外、ま [!UICONTROL Visitor]たは除外 [!UICONTROL Visit]しない限り、す [!UICONTROL Hit] べてのデータが含ま [!UICONTROL Exclude] れます。 これにより、一般的なデータを消去し、より焦点を絞ったセグメントを作成できます。 また、見つかったグループを除くセグメントを作成して、残りのデータセットを識別できます。例えば、注文を行った成功した訪問者を含むルールを作成し、「非購入者」を識別するために除外できます。 ただし、ほとんどの場合、特定の値を含む値をターゲットするルールを使用するよりも、部分的な値を除外するルールを作 [!UICONTROL Exclude] 成する方がよいでしょう。

次に例を示します。

* **ページの除外**。 セグメントルールを使用して、レポートから特定のページ(例： *`Home Page`*)を除去し、ページが「ホームページ」に等しい場合に除外するヒットルールを作成します。 このルールでは、このルール以外のすべての値が自動的にホームページされます。
* **参照ドメインの除外**。 Google.comの参照ドメインのみを含み、他のすべての参照ドメインを除外するルールを使用します。
* **非購入者の識別**。 注文件数が0より大きい場合を識別し、その後を除外しま [!UICONTROL Visitor]す。

この演 [!UICONTROL Exclude] 算子を使用して、特定の訪問またはヒットが実行されないシーケンスを識別できます。訪問者。 [!UICONTROL Exclude Checkpoints] は、論理グループに含めること [もできます](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。

### チェックポイント間の除外

あるチェックポイントが他の 2 つチェックポイント間で明示的に発生しなかった場合に訪問者をセグメント化する論理を強制します。

**例**：ページ A の後、ページ C を訪問したが、ページ B を訪問しなかった訪問者。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* 訪問者が表示されます。
* ある自動車小売業者は、メインランディングページを訪問した後、車両ページに移動せずに、直接「興味なし」キャンペーンに移動した顧客間の関係を確認します。

**このセグメントを作成**

単純な順次セグメント、混合レベルの順次セグメント、またはネストされた順次セグメントの場合と同様にセグメントを作成し、コンテナ要素に [!UICONTROL EXCLUDE] 演算子を設定します。The example below is an aggregate segment where the three [!UICONTROL Hit] containers are dragged to the canvas, the [!UICONTROL THEN] operator assigned to join the container logic, then exclude the middle page view container to include only visitors that went from page A to Page C in the sequence.

![](assets/exclude_between_checkpoints.png)

### シーケンスの開始時の除外

除外チェックポイントが順次セグメントの最初にある場合、除外されないヒットが最初に閲覧される前に、除外されるページは閲覧されないものとして扱われます。

**例**：訪問者はページ A を訪問し、ページ B を訪問しなかった。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* 訪問者がページAを訪問し、ページBを訪問しなかった。
* あるレストランでは、メインランディングページを避けて、注文ページに直接移動した常連ユーザーを表示したいと考えています。

**このセグメントを作成**

トップレベルのコンテナ内に2つの個別のヒット訪問者を作成します。 次に、最初の演 [!UICONTROL EXCLUDE] 算子のコンテナ。

![](assets/exclude_beginning_sequence.png)

### シーケンスの終了時の除外

除外チェックポイントがシーケンスの最後にある場合、訪問者シーケンスが終了するまで、除外されない最後のチェックポイントと訪問者シーケンスの最後の間でチェックポイントは発生しません。

**例**：訪問者は、現在の訪問または後続の訪問で、ページ A を訪問したが、ページ B は訪問しなかった。

**使用例**

次に、このタイプのセグメントの使用例を示します。

* 訪問者がページAを訪問し、ページBを訪問しなかった。
* あるレストランでは、メインランディングページを避けて、注文ページに直接移動した常連ユーザーを表示したいと考えています。

**このセグメントを作成**

Build a simple sequence segment by dragging two [!UICONTROL Hit] containers to the canvas and connecting them using the [!UICONTROL THEN] operator. Then assign the [!UICONTROL EXCLUDE] operator to the second [!UICONTROL Hit] container in the sequence.

![](assets/exclude_end_sequence.png)

## 論理グループコンテナ

「論理グループ」コンテナは、条件を単一の順次セグメントチェックポイントにグループ化する場合に必要です。特別な「論理グループ」コンテナは、順次セグメント化でのみ使用でき、前の順次チェックポイントの後、および後続の順次チェックポイントの前に、条件が満たされるようにします。論理グループチェックポイント内の条件は、どの順序でも満たすことができます。これに対し、非順次コンテナ（ヒット、訪問、訪問者）は、シーケンス全体で条件を満たす必要がないので、THEN 演算子と組み合わせて使用した場合に得られる結果は直観的ではありません。
The [!UICONTROL Logic Group] container was designed to treat *several checkpoints as a group*, *without any ordering* among the grouped checkpoints. つまり、そのグループ内のチェックポイントの順序は決まっていません。For example, you can&#39;t nest a [!UICONTROL Visitor] container within a [!UICONTROL Visitor] container. But instead, you can nest a [!UICONTROL Logic Group] container within a [!UICONTROL Visitor] container with specific [!UICONTROL Visit]-level and [!UICONTROL Hit]-level checkpoints.

>[!NOTE] は、 [!UICONTROL Logic Group] 順次セグメント内でのみ定義できます。つまり、演算子が [!UICONTROL THEN] 式内で使用されます。

| コンテナの階層 | イラスト | 定義 |
|---|---|---|
| 標準的なコンテナ階層 | ![](assets/nesting_container.png) | ヒット数、 [!UICONTROL Visitor] 訪問回数、および [!UICONTROL Visit] コンテナ [!UICONTROL Hit] に基づいてセグメントを抽出するために、コンテナ内で、と訪問者が順にネストされます。 |
| 標準的なコンテナ階層 | ![](assets/logic_group_hierarchy.png) | 標準のコンテナ階層は、コンテナの外部でも必要で [!UICONTROL Logic Group] す。 しかし、コンテナ内 [!UICONTROL Logic Group] では、チェックポイントの順序や階層を確立する必要はありません。これらのチェックポイントは、訪問者が任意の順序で満たす必要があります。 |

論理グループは大変な作業に見える場合があります。論理グループの使用方法に関するベストプラクティスを以下に示します。

**論理グループコンテナまたはヒット／訪問コンテナのどちらが適していますか。**
順次チェックポイントをグループ化する場合、「コンテナ」は「論理グループ」になります。ただし、これらの順次チェックポイントが 1 回のヒットまたは訪問の範囲内で発生する必要がある場合は、「ヒット」または「訪問」コンテナが必要です。（もちろん、1 回のヒットが複数のチェックポイントにクレジットを提供しない場合、「ヒット」は順次チェックポイントのグループに対しては意味を持ちません。）

**論理グループは順次セグメントの作成を簡略化しますか。**
はい、できます。次の質問に回答すると想定します。**訪問者には、ページ B、ページ C、またはページ A の後にページ D が表示されましたか？**

このセグメントは、論理グループコンテナを使用せずに構築できますが、この作業は複雑で面倒です。
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

次に示すように、論理グループコンテナを使用すると、このセグメントを簡単に作成できます。

![](assets/logic-grp-example.png)


### 論理グループセグメントの作成 {#section_A5DDC96E72194668AA91BBD89E575D2E}

他のコンテナと同様 [!UICONTROL Logic Group] 、コンテナは内で複数の方法で構築できま [!UICONTROL Segment Builder]す。 ネストする推奨される方法を次に示 [!UICONTROL Logic Group] します。

1. 左のパネルから、ディメンション、イベントまたはセグメントをドラッグします。
1. 最上位のコンテナを [!UICONTROL Visitor] コンテナ
1. デフォルトで [!UICONTROL AND] 挿入され [!UICONTROL OR] るOR演算子をTHEN演算子に変更します。
1. コンテナ(ディメ [!UICONTROL Hit] ンション、イベントまたは項目)を選択し、/をクリ **[!UICONTROL Options]** ックしま **[!UICONTROL Add container from selection]**&#x200B;す。
1. Click the container icon and select **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. You can now set the [!UICONTROL Hit] within the [!UICONTROL Logic Group] container without regard to hierarchy.

### 任意の順序での論理グループのチェックポイント

Using the [!UICONTROL Logic Group] lets you meet conditions within that group that reside outside of the sequence. This allows you to build segments where a [!UICONTROL Visit] or [!UICONTROL Hit] container happens irrespective of the normal hierarchy.

**例**：訪問者はページ A を訪問した後で、ページ B とページ C を任意の順序で訪問した。

**このセグメントを作成**

Page B and C are nested in a [!UICONTROL Logic Group] container within the outer [!UICONTROL Visitor] container. The [!UICONTROL Hit] container for A is then followed by the [!UICONTROL Logic Group] container with B and C identified using the [!UICONTROL AND] operator. Because it is in the [!UICONTROL Logic Group], the sequence is not defined and hitting both page B and C in any order makes the argument true.

![](assets/logic_group_any_order2.png)

**別の例**：訪問者は、ページ B またはページ C を訪問してから、ページ A を訪問した。

![](assets/logic_group_any_order3.png)

このセグメントは、論理グループのチェックポイント（B または C）の 1 つ以上と一致する必要があります。また、論理グループの条件は、同じヒットで満たされる場合も、複数のヒットをまたいで満たされる場合もあります。

### 論理グループの最初の一致

Using the [!UICONTROL Logic Group] lets you meet conditions within that group that reside outside of the sequence. この順不同の最初の一致セグメントでは、 [!UICONTROL Logic Group] ルールが最初にページBまたはページCのページ表示、次にページAの必要な表示として識別されます。

**例**：訪問者は、ページ B または ページ C のどちらかを訪問した後で、ページ A を訪問した。

**このセグメントを作成**

Page B and page C dimensions are grouped within a [!UICONTROL Logic Group] container with the [!UICONTROL OR] operator selected, then the [!UICONTROL Hit]container identifying a page view of page A as the value.

![](assets/logic_group_1st_match.png)

### 論理グループの除外の AND

Build segments using the [!UICONTROL Logic Group] where multiple page views are aggregated to define what pages were necessary to be hit while other pages were specifically missed. ****

**例**：訪問者はページ A を訪問し、ページ B または C は明示的に訪問せずに、ページ D をヒットした。

**このセグメントを作成**

このセグメントを作成するには、左のパネルからディメンション、イベントおよび事前ビルドセグメントをドラッグします。「[論理グループセグメントの作成](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)」を参照してください。

内で値をネストした後、 [!UICONTROL Logic Group]コンテナ内のボ **[!UICONTROL Exclude]** タンをクリック [!UICONTROL Logic Group] します。

![](assets/logic_exclude_and.png)

### 論理グループの除外の OR

Build segments using the [!UICONTROL Logic Group] where multiple page views are aggregated to define what pages were necessary to be hit while other pages were specifically missed.

**例**：ページ A を訪問した訪問者が、ページ A の前にページ B もページ C も訪問していない。

**このセグメントを作成**

The initial B and C pages are identified in a [!UICONTROL Logic Group] container that is excluded, and then followed by a hit to page A by the visitor.

このセグメントを作成するには、左のパネルからディメンション、イベントおよび事前ビルドセグメントをドラッグします。

内で値をネストした後、 [!UICONTROL Logic Group]コンテナ内のボ **[!UICONTROL Exclude]** タンをクリック [!UICONTROL Logic Group] します。

![](assets/logic_exclude_or.png)

## 期間内および時間後セグメントの作成

各ヘッダー [!UICONTROL Within] のヘッ [!UICONTROL After] ダーに組み込まれているAND演算子を使用して、時間、イベントおよびカウントを定義します。

![](assets/then_within_operators.png)

とのコンテナを使用し、精度とカウントを指定することで、一致を指 [!UICONTROL Within] 定し [!UICONTROL After] た期間に制限できます。 The [!UICONTROL Within] operator is used to specify a max limit on the amount of time between two checkpoints. The [!UICONTROL After] operator is used to specify a minimum limit on the amount of time between two checkpoints.

### AfterおよびWithin演算子 {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

期間は、精度を表す 1 つの大文字の後に、その精度の繰り返し回数を表す数値を記述して指定します。

**[!UICONTROL Within]** はエンドポイントを含みます（エンドポイント以下）。

**[!UICONTROL After]** はエンドポイントを含みません（エンドポイントを超える）。

| 演算子 | 説明 |
|--- |--- |
| AFTER | After 演算子は、2 つのチェックポイントの間隔の最小値を指定するために使用します。After 値を設定すると、セグメントの適用時にこの時間制限が開始されます。例えば、ページ A を訪問したが、1 日後までページ B を訪問しなかった訪問者を識別するためにコンテナに After 演算子を設定した場合、訪問者がページ A を離れた時点からカウントが開始します。訪問者をこのセグメントに含めるには、ページ A を離れてからページ B を閲覧するまでに、最低 1440 分（1 日）が経過する必要があります。 |
| WITHIN | Within 演算子は、2 つのチェックポイントの間隔の最大値を指定するために使用します。例えば、コンテナに対して Within 演算子を設定し、ページ A を訪問した後 1 日以内にページ B を訪問した訪問者を特定する場合、訪問者がページ A を離れた時点からカウントが開始します。訪問者がこのセグメントに含まれるには、訪問者はページ B を開くまで最長で 1 日の時間があります。訪問者をこのセグメントに含めるには、ページ B への訪問が、ページ A を離れてからページ B を閲覧するまでの 1440 分（1 日）以内に発生する必要があります。 |
| AFTER／WITHIN | After と Within の両方の演算子を使用する場合に重要になるのが、両方の演算子が順次的ではなく並行的に開始および終了するという点です。例えば、コンテナを <br>`After = 1 Week(s) and Within = 2 Week(s)`<br> に設定したセグメントを作成すると、このセグメントで訪問者を識別する条件が満たされるのは 1 ～ 2 週間の期間のみです。最初のページヒットの時点から、両方の条件が適用されます。 |

### After 演算子の使用

* 後の時間では、年、月、日、時間および分を基準にして、一致する訪問を追跡できます。
* 「後の時間」は、このような細かい精度が定義さ [!UICONTROL Hit] れる唯一のレベルであるコンテナにのみ適用できます。

**例**：訪問者がページ A に訪問し、その 2 週間後以降にページ B に訪問した。

![](assets/time_between_after_operator.png)

**セグメントの作成**:このセグメントは、2つのセグメントを持つ [!UICONTROL Visitor] コンテナを追加して作 [!UICONTROL Hit] 成します。 これにより、[!UICONTROL THEN] 演算子を設定し、[!UICONTROL AFTER] 演算子のドロップダウンを展開して、週の数値を設定できます。

![](assets/after_operator.png)

**一致する**

「2 週間後」と指定した状態で、ページ A へのヒットが 2019 年 6 月 1 日の 0 時 1 分 に発生し、その後、次のページ B へのヒットが 2019 年 6 月 15 日の 0 時 1 分（14 日後）までに発生した場合。

| ヒットA | ヒットB | 一致 |
|--- |--- |--- |
| **A** ヒット：2019 年 6 月 1 日 0 時 1 分 | **B** ヒット：2019 年 6 月 15 日 0 時 1 分 | **一致**：2019 年 6 月 1 日の「後」（2 週間後）に発生しているので、この時間制限は一致すると見なされます。 |
| **A** ヒット：2019 年 6 月 1 日 0 時 1 分 | **B** ヒット：2019 年 6 月 8 日 0 時 1 分、B ヒット：2019 年 6 月 15 日 0 時 1 分 | **一致しない**：ページ B の最初のヒットが、2 週間より後であることを求めている制約と矛盾するので、一致しないと見なされます。 |

### Within 演算子の使用

* [!UICONTROL Within] 年、月、日、時間、分を使用して一致する訪問を追跡できます。
* [!UICONTROL Within] は、そのような細かい精度が定義さ [!UICONTROL Hit] れる唯一のレベルなので、コンテナにのみ適用できます。

>[!IMPORTANT]
>
>「within」句の「THEN」ステートメントの間に、例えば「within 1 search keyword instance（1 個の検索キーワードのインスタンス内）」や「within 1 eVar 47 instance（1 個の eVar 47 インスタンス内）」というように追加できます。これにより、ディメンションの 1 個のインスタンス内にセグメントが制限されます。

**例**：ページ A に訪問した訪問者が、5 分以内にページ B を訪問した。

![](assets/time_between_within_operator.png)

**セグメントの作成**:このセグメントは、セグメントを追加し、 [!UICONTROL Visitor] コンテナを2つドラッグして作成 [!UICONTROL Hit] します。 次に、[!UICONTROL THEN] 演算子を設定し、[!UICONTROL AFTER] 演算子のドロップダウンを展開して、間隔（ヒット、ページビュー、訪問、分、時、日、週、月、四半期または年）を設定できます。

![](assets/within_operator.png)

**一致する**

この時間制限以内に一致が発生する必要があります。式を指定して、訪問者のページ A へのヒットが 0 時 1 分に発生した場合、その後のページ B へのヒットが 0 時 6 分またはそれ以前（5 分後まで）に発生した場合は一致と見なされます。ちょうど指定した時間である場合も一致と見なされます。

### Within 演算子と After 演算子

[!UICONTROL Within] および [!UICONTROL After] は、セグメントの両端でエンドポイントの最大値と最小値を指定するために使用します。

**例**：訪問者がページ A に訪問し、2 週間後以降、1 ヶ月以内にページ B に訪問した。

![](assets/time_between_using_both_operators.png)

**セグメントの作成**:セグメント内で2つのコンテナを順に並べて、セ [!UICONTROL Hit] グメントを作 [!UICONTROL Visitor] 成します。 Then set the [!UICONTROL After] and [!UICONTROL Within] operators.

![](assets/within_after_together.png)

**一致する**

2019 年 6 月 1 日にページ A をヒットした後、2019 年 6 月 15 日 0 時 1 分より後、2019 年 7 月 1 日より&#x200B;*前に*&#x200B;戻った訪問者がこのセグメントに含まれます。「除外間隔の [時間」と比較します](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。

演算子と [!UICONTROL After] 演算子 [!UICONTROL Within] を組み合わせて使用して、順次セグメントを定義できます。

![](assets/time_between_within_after.png)

この例では、2 回目の訪問で 2 週間後から 1 ヶ月までの間にページ B にヒットしています。
