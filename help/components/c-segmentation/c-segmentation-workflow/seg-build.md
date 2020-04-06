---
description: セグメントビルダーのキャンバスには、指標ディメンション、セグメントおよびイベントをドラッグ&ドロップして、コンテナ階層のロジック、ルールおよび演算子に基づいて訪問者をセグメント化する機能があります。 この統合開発ツールを使用すると、訪問やページヒットを対象として訪問者の属性やアクションを識別する、簡単な、または複雑なセグメントを作成し、保存できます。
title: セグメントの構築
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# セグメントビルダー

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. この統合開発ツールを使用すると、訪問やページヒットを対象として訪問者の属性やアクションを識別する、簡単な、または複雑なセグメントを作成し、保存できます。

>[!IMPORTANT]
>
>ディメンションアトリビューションモデルは、2019 年 6 月のリリースで導入されました。以下の「Web UI 機能」の #6 を参照してください。

セグメントビルダーにアクセスする方法はいくつかあります。

* **Analyticsのトップナビゲーション**://をク **[!UICONTROL Analytics]** リック **[!UICONTROL Components]** しま **[!UICONTROL Segments]**&#x200B;す。
* **[!UICONTROL Analysis Workspace]**:/をク **[!UICONTROL Analytics]** リッ **[!UICONTROL Workspace]**&#x200B;クし、プロジェクトを開いて、/をクリ **[!UICONTROL + New]** ックしま **[!UICONTROL Create Segment]**&#x200B;す。
* **[!UICONTROL Reports & Analytics]**:/をク **[!UICONTROL Analytics]** リック **[!UICONTROL Reports]**&#x200B;し、既存のレポートを開き、左側のナビゲーションでセグメント ![](assets/segment_icon.png) アイコンをクリックして、をクリックしま **[!UICONTROL Add]**&#x200B;す。
* **[!UICONTROL Ad Hoc Analysis]**:Ad Hoc [分析](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments)。
* **[!UICONTROL Report Builder]**: [追加Report Builderでセグメントを編集します](https://marketing.adobe.com/resources/help/ja_JP/arb/segmentation.html)。

## セグメントビルダーのユーザーインターフェイス {#concept_643F2DF74C544796B58F4656ABC5F726}

を使用す [!UICONTROL Segment Builder] ると、訪問やページヒットの訪問者属性やアクションを識別する、単純な、または複雑なセグメントを作成できます。 階層ロジック、ルールおよび演算子に基づいて訪問者をセグメント化するために、指標ディメンション、イベントまたは他のセグメントをドラッグ&amp;ドロップするキャンバスが提供されます。

## Web UI機能 {#section_F61C4268A5974C788629399ADE1E6E7C}

Web UI( [!UICONTROL Segment Builder] またはAd Hoc分析の [Java UI](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md))でセグメントを作成および編集できます。 ルール定義やコンテナを追加して、セグメントの絞り込み、積み重ね、ネストを行って、セグメントを絞り込むことができます。 また、現在のセグメント定義から生じたページ表示数、訪問回数、個別訪問者数を検証することもできます。 次に、今後のニーズに合わせてセグメントを保存します。

セグメントビルダーにアクセスするには、次の方法があります:

* 既存のレポートを表示して、左側のナビゲーションでセグメントアイコン ![](assets/segment_icon.png) をクリックします。In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* セグメントマネージャ内で既存のセグメントタイトルをクリックし、そのセグメントをセグメントビルダーで編集します。

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**:セグメントに名前を付けたり、名前を変更したりできます。
1. **[!UICONTROL Description]**:セグメントの説明を入力します。 セグメントを共有したい場合は、説明を入力する必要があります。
1. **[!UICONTROL Tags]**:作成して [いるセグメントに](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) 、既存のタグのリストから選択するか、新しいタグを作成してタグを付けます。
1. **[!UICONTROL Definitions]**:セグメントの作成と設定、 [ルールの追加](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)、ネストとシーケンスコンテナ。 コンテナを選択し、ディメンション、セグメントまたは指標を定義にドラッグ＆ドロップすることで、新しいセグメントの説明を提供できます。
1. **[!UICONTROL Show]**:(トップコンテナの選択)。最上位レベルの [コンテナ](/help/components/c-segmentation/seg-overview.md) (、 [!UICONTROL Visitor]、 [!UICONTROL Visit][!UICONTROL Hit])を選択します。 デフォルトのトップレベルのコンテナは、ヒットコンテナです。
1. **[!UICONTROL Options]**:（ギア）アイコン

   * **[!UICONTROL + Add container]**:セグメント定義に新しいコンテナ(最上位コンテナの下)を追加できます。
   * **[!UICONTROL + Add container from selection]**:[定義]フィールドで選択したコンテナ（複数）から新しい要素を作成できます。
   * **[!UICONTROL Exclude]**:1つ以上のディメンション、セグメントまたは指標を除外して、セグメントを定義できます。

1. **[!UICONTROL Attribution Models]**:ディメンションセグメント用。 ディメンションモデルは、フロービジュアライゼーションをサポートするディメンションなど、順次セグメント化で特に便利です。

   * **[!UICONTROL Repeating]** (（デフォルト）:ディメンションのインスタンスと永続化された値が含まれます。
   * **[!UICONTROL Instance]**: ディメンションのインスタンスが含まれます.
   * **[!UICONTROL Non-repeating instance]**: ディメンションの一意のインスタンス (繰り返さない) が含まれます.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]**:ディメンションがディメンションリスト（オレンジ色のサイドバー）からドラッグ&amp;ドロップされます。
1. **[!UICONTROL Comparison]**:選択した演算子を使用して、値を比較および制限できます。
1. **[!UICONTROL Value]**:ディメンション、セグメント、指標に対して入力または選択した値。
1. **[!UICONTROL And/Or/Then]**:演算子を [!UICONTROL AND/OR/THEN] コンテナまたはルール間で割り当て THEN 演算子は、[順次セグメントを定義](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)します。
1. **[!UICONTROL Metric]**:（緑のサイドバー）指標リストからドラッグ&amp;ドロップした指標。
1. **[!UICONTROL Comparison]** 演算子：選択した演算子を使用して、値を比較および制限できます。
1. **[!UICONTROL Value]**:ディメンション、セグメント、指標に対して入力または選択した値。
1. **[!UICONTROL X]**：（削除）セグメント定義のこの部分を削除できます。
1. **[!UICONTROL Save]** または **[!UICONTROL Cancel]**:セグメントを保存またはキャンセルします。 After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**:ディメンション、セグメントまたは指標のリストを検索します。
1. **[!UICONTROL Dimensions]**:(リスト)ヘッダーをクリックして展開します。
1. **[!UICONTROL Metrics]**:ヘッダーをクリックして展開します。
1. **[!UICONTROL Segments]**:ヘッダーをクリックして展開します。
1. **[!UICONTROL Report suite selector]**:このセグメントを保存するレポートスイートを選択できます。 セグメントは、すべてのレポートスイートで利用できます。
1. **[!UICONTROL Segment Preview]**:主要指標をプレビューして、有効なセグメントがあるかどうか、およびセグメントの範囲を確認できます。 このセグメントを適用した場合に表示されるデータセットの分類を表します。 データセットに対するセグメント実行の、、およびの一致の数と割合を示す3つの同心円と [!UICONTROL Hits]リスト [!UICONTROL Visits]が表示さ [!UICONTROL Visitors] れ、3つの同心円と1つのデータセットが表示されます。 このグラフは、セグメント定義を作成または変更した直後に更新されます。
1. **[!UICONTROL Product Compatibility]**:作成したセグメントと互換性があるAdobe Analytics製品(分析ワークスペース、 [!UICONTROL Reports & Analytics]Ad Hoc分析、Data Warehouse)のリストを提供します。 ほとんどのセグメントは、すべての製品と互換性があります。 ただし、演算子とディメンションの一部が、すべてのAnalytics製品(特に [Data Warehouse)と互換性があるわけではありません](/help/components/c-segmentation/seg-reference/seg-compatibility.md)。 このグラフは、セグメント定義を変更するとすぐに更新されます。

日付範囲が埋め込まれているセグメントの動作は、今後も Analysis Workspace と [!UICONTROL Reports & Analytics] では異なります。ワークスペースでは、日付範囲が埋め込まれているセグメントがパネルの日付範囲より優先されます。これに対して、[!UICONTROL Reports & Analytics] では、レポートの日付範囲とセグメントの埋め込みの日付範囲が重なる期間のみが対象期間になります。

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**:（画面に表示されません）このオプションは、このセグメントの保存先のレポートスイートがExperience Cloudに対して有効になっ [ている場合にのみ表示されます](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)。 By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. 公開するためには、セグメントタイトルと説明が必須です。

>[!NOTE]Analytics では、公開されたセグメントを編集または削除できます。セグメントが使用中の場合は、セグメントを編集すると、警告メッセージが表示されます。Adobe [!DNL Target] によって使用されている公開したセグメントは削除できません。

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>処理で追加の遅れが生じないように、Analytics から共有されるオーディエンスの数は、20 までに制限する必要があります。AnalyticsからExperience Cloudに共有されるオーディエンスは、2,000万人を超える個別メンバーを超えることはできません。 また、キャッシュのため、Analyticsで削除されたレポートスイートは、Experience Cloudに削除が表示されるまで12時間かかります。

>[!IMPORTANT]
>
>訪問者が Analytics から共有されるオーディエンスの資格を得てから、その情報が [!DNL Advertising Cloud]、[!DNL Target] および [!DNL Campaign] で対応可能になるまでに、24～48 時間の遅延があります。

## セグメントの構築 {#build-segments}

1. ディメンション、セグメントまたは指標イベントを左側のパネルからフィールドにドラッグ [!UICONTROL Definitions] します。

   ![](assets/drag_n_drop_dimension.png)

   要素をドラッグすると、デフォル [!UICONTROL Hit] トの最上位コンテナが表示されま [!UICONTROL Definitions]す。 You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. ドロップダウンメニューから[演算子](/help/components/c-segmentation/seg-reference/seg-operators.md)を設定します。
1. 選択した項目に対して値を入力または選択します。
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. コンテナを配置し、ルールを設定した後、右上の検証グラフでセグメントの結果を確認します。 バリデーターは、作成したセグメントに一致するページ表示、訪問および個別訪問者の割合と絶対数を示します。
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

[セグメントマネージャ](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md)に移動し、複数の方法でセグメントにタグ付け、共有、管理できます。

## コンテナの作成とネスト {#section_1C38F15703B44474B0718CEF06639EFD}

[コンテナのフレームワークを作成](/help/components/c-segmentation/seg-overview.md)し、論理ルールと演算子を配置できます。

1. クリック **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   新しい [!UICONTROL Hit] コンテナが開き、 [!UICONTROL Hit] (ページ表示)が識別されません。

   ![](assets/new_container.png)

1. 必要に応じてコンテナタイプを変更します。
1. ディメンション、セグメントまたはイベントを左ペインからコンテナにドラッグします。
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OR**

   1つ以上のルールを選択し、/をクリッ **[!UICONTROL Options]** クしま **[!UICONTROL Add container from selection]**&#x200B;す。 選択が別個のコンテナに変換されます。

## セグメントでの日付範囲の使用 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

実施中のキャンペーンやイベントに関する質問に回答するため、日付範囲の周期を含むセグメントを構築できます。

例えば、「過去 60 日間に購入したすべてのユーザー」を含むセグメントを容易に構築できます。

訪問コンテナを作成し、その中に、AND演算子を [!UICONTROL Last 60 days] 使用して、時間範囲と指 [!UICONTROL Orders is greater than or equal to 1]標を追加します。

![](assets/date-ranges.png)

## セグメントの積み重ね {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

セグメントを積み重ねると、各セグメントの条件を「And」演算子を使用して組み合わせ、結合した条件を適用できます。

例えば、「携帯電話ユーザー」セグメントと「米国の地域」セグメントを積み重ねると、米国の携帯電話ユーザーのデータのみが返されます。

これらのセグメントは、セグメントライブラリに含めることができる構成要素またはモジュールと考え、ユーザが見た目に合わせて使用できます。 これにより、必要なセグメント数を大幅に減らすことができます。 例えば、次の40個のセグメントがあるとします。

* 異なる国（US_mobile、Germany_mobile、France_mobile、Brazil_mobileなど）の携帯電話ユーザーの場合は20
* 異なる国のタブレットユーザー用に20個（US_tablet、Germany_tablet、France_tablet、Brazil_tabletなど）

セグメントの積み重ねを使用すると、セグメント数を22個に減らし、必要に応じて積み重ねることができます。 次のセグメントを作成する必要があります。

* モバイルユーザー向けの1つのセグメント
* タブレットユーザー用の1つのセグメント
* 異なる地域向けに20個のセグメント

>[!NOTE]2 つのセグメントを積み重ねると、デフォルトで、それらのセグメントが AND ステートメントで結合されます。これはORステートメントに変更できません。

1. セグメントビルダーに移動します。
1. セグメントのタイトルと説明を入力します。

   手順の結果 1Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   手順の結果 1積み重ねるセグメントをセグメント定義キャンバスにドラッグ&amp;ドロップします。 次に、既存のセグメント「タブレットからの訪問」と「米国の地域」を積み重ねたセグメントの例を示します。

   ![](assets/seg_stack2.png)

1. セグメントを保存します。

   手順の結果

## セグメントテンプレートの使用 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

テンプレートは、事前設定済みの古いスイートセグメントを表します。

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. セグメントアイコン ![](assets/segment_icon.png) をクリックして、

セグメントパネルを表示します。セグメントテンプレートがセグメントテンプレートの下部に表示されます。リスト テンプレート名の左側にあるフォルダーアイコンで区別できます。

![](assets/seg_template.png)

これらのテンプレートは、定義キャンバスにドラッグし、定義済みの状態で使用したり、変更したりできます。

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> テンプレート名 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 買い物かごを放棄 </td> 
   <td colname="col2">表示を買い物かごに追加したが、何も注文しなかった訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 この順次セグメントのルールは、 <p> 買い物かごへの追加がnullでない </p> <p>次に </p> <p>注文が0に等しい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 初回訪問回数 </td> 
   <td colname="col2">表示した訪問者のデータが最大1回訪問されました。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>訪問回数が 1 と等しい </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非購入者 </td> 
   <td colname="col2">表示訪問者に参加していないイベントのデータ。 セグメント定義では、コンテナは訪問者です。 このセグメントでは、「除外」論理を使用します。 ルールは <p>注文がnullではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非直帰数 (非バウンス) </td> 
   <td colname="col2">表示訪問者のデータ。 セグメント定義では、コンテナは訪問者。 このセグメントでは、「除外」論理を使用します。 ルールは <p>単一アクセスがnullではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 有料検索 </td> 
   <td colname="col2">表示データは、有料検索から訪問者に送信されました。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>「有料検索が1」です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 購入者 </td> 
   <td colname="col2">表示訪問者に参加したイベント。 セグメント定義では、コンテナは訪問者です。 ルールは <p>注文がnullではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 再来訪 </td> 
   <td colname="col2">表示訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>訪問回数が1より大きい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 直帰数 </td> 
   <td colname="col2"> 表示中に複数のページ表示を送信する場合でも、単一のページ値が表示される訪問の訪問データ。 出口リンクイベントを持つ直帰数がセグメントに含まれます。セグメント定義では、コンテナは「訪問」です。 ルールは <p>「直帰数が 1」です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閲覧された製品が買い物かごに追加表示されなかった </td> 
   <td colname="col2">表示を表示したが、訪問者に買い物かごが追加されなかった製品の買い物かごデータ。 セグメント定義では、コンテナは「訪問」です。 この順次セグメントのルールは、 <p>製品表示がnullでない </p> <p>次に </p> <p> 買い物かごへの追加数が0に等しい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> キャンペーンからの訪問回数 </td> 
   <td colname="col2">表示が参照する訪問者のキャンペーンデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>トラッキングコードがnullではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> モバイルデバイスからの訪問 </td> 
   <td colname="col2">表示を使用する訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>モバイルデバイスがnullではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自然検索からの訪問 </td> 
   <td colname="col2">表示データは、有料検索訪問者以外の検索データから取得されます。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>「有料検索が0」です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> モバイル以外のデバイスからの訪問 </td> 
   <td colname="col2">表示を使用していない訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 このセグメントでは、「除外」論理を使用します。 ルールは <p>モバイルデバイスタイプが携帯電話に等しい </p> <p>または </p> <p>「モバイルデバイスタイプがタブレットに等しい」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話からの訪問回数 </td> 
   <td colname="col2">表示を使用する訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>デバイスタイプが携帯電話に等しい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジンからの訪問回数 </td> 
   <td colname="col2">表示が参照する訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>転送者タイプが検索エンジンに等しい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソーシャルサイトからの訪問 </td> 
   <td colname="col2">表示データは、ソーシャルサイトが参照する訪問者から取得されます。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>転送者タイプがソーシャルネットワークに等しい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> タブレットからの訪問回数 </td> 
   <td colname="col2">表示を使用する訪問者のデータ。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>「デバイスタイプがタブレットに等しい」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者 ID cookie の訪問 </td> 
   <td colname="col2">表示データを訪問者からサイトに送信し、サイトで永続的なcookieが必要となる場合。 セグメント定義では、コンテナは「訪問」です。 ルールは <p>永続的なcookieが1に等しい。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 例：キャンペーン訪問者セグメント {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

頻繁に使用されるセグメントの例を示します。

多くの顧客は、特定の反応を示した訪問者の指標を見たいと思っています。 キャンペーン訪問者セグメントを作成すると、このデータを簡単に取得できます。

このセグメントをセグメントビルダーで作成するということは、トップレベルの訪問コンテナから、キャンペーンディメンション(この場合はキャンペーン名)をドラッグすることです。

![](assets/seg_campaign_visitor.png)

（オプション）すべてのキャンペーン関連セグメントを簡単にフィルタリングする場合は、このセグメントにキャンペーンタグを適用することもできます。
