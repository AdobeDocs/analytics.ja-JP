---
description: 計算指標ビルダーは、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 指標の作成
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a6b7622562ced9d28229e094f027c8d0ee79532b
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 47%

---

# 指標の作成

Adobe Analyticsのキャンバスにディメンション、指標、セグメントおよび関数をドラッグ&amp;ドロップすると、コンテナ階層のロジック、ルールおよび演算子に基づいてカスタム指標を作成できます。 この統合開発ツールでは、シンプルまたは複雑な計算指標を作成および保存できます。

## 計算指標の作成を開始する

計算指標の作成は、次のいずれかの方法で開始できます。

* Analysis Workspaceで、プロジェクトを開き、「 」を選択します。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 指標を作成]**.
* Analysis Workspaceで、プロジェクトを開き、 **プラス** 横のアイコン [!UICONTROL **指標**] セクションをクリックします。
* In [!DNL Analytics]に移動します。 **[!UICONTROL コンポーネント]** > **[!UICONTROL 計算指標]**&#x200B;を選択し、「 **[!UICONTROL +追加]** をクリックします。

## 計算指標ビルダーの領域

次の画像と付属の表は、計算指標マネージャの主な機能の一部を説明しています。

![](assets/cm_builder_ui.png)

| 画像内の場所 | 名前と関数 |
|---|---|
| 1 | **タイトル：** 指標の名前は必須です。 名前を付けていない指標は保存できません。 |
| 2 | **説明：** ユーザーにわかりやすい説明を入力して、その用途を示し、類似のものと区別するために使用されているものを示します。 <p>この説明はレポート内にも表示されます。説明には数式を記述しないことをお勧めします。その代わりに、この指標を使うべき状況と使ってはいけない状況について記述してください（数式は、指標の作成時に「概要」という見出しの下に生成されます。そのため、この説明に数式を追加する必要はありません）。 </p> |
| 3 | **形式：** 小数、時間、割合、通貨から選択できます。 |
| 4 | **小数点以下の桁数：** レポートに表示する小数点以下の桁数を示します。 指定可能な小数点以下の桁数の最大値は 10 です。 |
| 5 | **上昇傾向を次の形式で表示：** この指標の極性設定は、Analytics が指標の上昇傾向を良い（緑）と見なすか悪い（赤）と見なすかを示します。 そのため、レポートのグラフは、上昇傾向の場合に緑または赤で表示されます。 |
| 6 | **タグ：** タグ付けは、指標を整理するのに適しています。 すべてのユーザーがタグを付けることができます。指標には 1 つ以上のタグを適用できます。ただし、自分が所有しているまたは自分が共有していたセグメントに対するタグのみを表示できます。どのような種類のタグを作成する必要がありますか。次に、便利なタグのいくつかを示します。<ul><li>**チーム名**（ソーシャルマーケティング、モバイルマーケティングなど）。</li><li>**プロジェクト** （分析タグ）を使用できます。</li><li>**カテゴリ**&#x200B;女性用のものなど。地域。</li><li>**ワークフロー**（承認待ちなど）（特定のビジネスユニット向けの）キュレーション</li></ul> |
| 7 | **概要:** <p>「概要」の数式は、指標の定義を変更すると更新されます。この数式は、左側の指標レールで、指標の上にマウスポインターを置いて <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> アイコン </p> |
| 8 | **定義：** ここで、指標/計算指標、セグメントまたは関数をドラッグして、計算指標を作成します。 <ul><li>計算指標をドラッグすると、指標の定義が自動的に展開されます。 </li> <li>コンテナを使用して定義をネストできます。ただし、セグメントコンテナとは異なり、これらのコンテナは数式のように機能し、演算の順序を指定します。 </li> </ul> |
| 9 | **演算子：** 除算 ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) はデフォルトの演算子です。他にも、+、 — および x の演算子があります。 |
| 10 | **プレビュー：** 考えられるエラーに関する簡単な情報を提供します。 プレビューには過去 90 日の情報が表示されます。これは、指標に適したコンポーネントを選択したかどうかを最初に判断するための手段です。予期しない結果が生じた場合は、指標の定義を見直す必要があります。 |
| 11 | **製品の互換性:** <p>「製品の互換性」は、指標が「<a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=ja"  >現在のデータ</a>」、「処理済みのデータ」またはマーケティングチャネルレポートのみ（ファーストタッチ配分）のいずれと互換性があるかを示します。 <p>注意：「現在のデータ」はすべての指標をサポートしているわけではありません。セグメントまたは関数を含む指標は「現在のデータ」との互換性がありません。<a href="/help/components/c-calcmetrics/cm-compatibility.md"  >さらに詳しく... </a> </p> </p> |
| 12 | **追加：** すべてのタイプの計算指標について、コンテナおよび静的な数値を定義に追加できます。 高度な計算指標の場合、セグメントおよび関数も追加できます。 <ul><li>コンテナは数式のように機能し、演算の順序を指定します。そのため、コンテナ内の項目は、次の演算の前に処理されます。</li><li>コンテナにセグメントをドラッグすると、そのコンテナ内のすべての項目がセグメント化されます。（高度な計算指標のみ）</li><li>コンテナでは複数のセグメントを積み重ねることができます。</li></ul> |
| 13 | **歯車アイコン（指標タイプ、アトリビューション）:** 指標の横にある歯車アイコンをクリックすると、 <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > 指標タイプとアトリビューションモデル </a>. |
| 14 | **新規：** 新しいセグメントなどの新しいコンポーネントを作成できます ( 新しいセグメントを作成する場合は、 <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > セグメントビルダー </a>.) |
| 15 | **コンポーネントを検索：** この検索バーでは、ディメンション、指標、セグメント（高度な計算指標のみ）および関数（高度な計算指標のみ）を検索できます。 |
| 16 | **Dimensionのリスト：** （セグメントビルダーで）シンプルなセグメントを作成するために、計算指標ビルダーから離れる代わりに、「Page = Homepage」と入力した場合は、Page にドラッグして、計算指標ビルダーから直接「Homepage」を選択できます。<p>これにより、セグメントを利用する計算指標の作成が容易になります。</p> |
| 17 | **指標のリスト：** 指標は次の 3 つのカテゴリに分類されます。 <ul> <li>標準指標 (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>計算指標 ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">指標テンプレート ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) — リストの最下部に表示されます。 </li> </ul> <p>指標の上にマウスポインターを置くと、右側に情報アイコンが表示されます。 <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />に移動します。このアイコンをクリックすると、次の情報が表示されます。 </p><ul> <li>指標の計算を行うための数式。 </li><li>指標の傾向のプレビュー </li><li>編集（鉛筆）アイコン <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> 右上に表示されます。計算指標ビルダーが表示され、この計算指標を編集できます。 </li></ul> |
| 18 | **セグメントのリスト：** （高度な計算指標のみ）管理者は、このリストにログイン会社で作成されたすべてのセグメントを表示します。 管理者以外のユーザーの場合は、自分が所有するセグメントおよび共有しているセグメントがこのリストに表示されます。<a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=ja"  >さらに詳しく... </a> |
| 19 | **関数のリスト：** （高度な計算指標のみ）関数は次の 2 つのリストに分かれています。 <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > 基本 </a> （最も頻繁に使用されます）および <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > 詳細 </a>. |
| 20 | **レポートスイートの選択：** 別のレポートスイートに切り替えることができます。 |

{style="table-layout:auto"}
