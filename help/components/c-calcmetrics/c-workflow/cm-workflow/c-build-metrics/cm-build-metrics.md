---
description: 計算指標ビルダーは、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 指標の作成
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a1567366c9fad42b3836f43c681d5380e97b09f3
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 96%

---

# 指標の作成 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="Analysis Workspace、Report Builder など、この計算指標を使用できる Customer Journey Analytics の場所を示します。一部の計算指標は、実験では使用できません。"
>additional-url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="実験で計算指標を使用"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="外部 ID を変更すると、ビジネスインテリジェンスツールなどの外部ソースでの計算指標の表示方法に影響する可能性があります"

<!-- markdownlint-enable MD034 -->

Adobe Analytics には、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成できる、キャンバスが用意されています。この統合開発ツールでは、シンプルまたは複雑な計算指標を作成および保存できます。

## 計算指標の作成の開始

計算指標ビルダーを使用して、計算指標を作成または編集できます。 この方法で作成すると、コンポーネントリストで計算指標を使用できるようになります。このリストは、組織全体のプロジェクトで使用できます。または、[ 指標 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md) の [ 単一プロジェクトの計算指標の作成 ](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) の説明に従って、計算指標が作成されたプロジェクトでのみ使用できる計算指標をすばやく作成することができます。

計算指標ビルダーにアクセスして、コンポーネントリストで使用できる計算指標の作成を開始します。

1. 次のいずれかの方法で、計算指標ビルダーにアクセスします。

   * Analysis Workspace で、プロジェクトを開いて、**[!UICONTROL コンポーネント]**／**[!UICONTROL 指標を作成]**&#x200B;を選択します。
   * Analysis Workspace でプロジェクトを開き、左側のパネルの「[!UICONTROL **指標**]」セクションの横にある&#x200B;**プラス**&#x200B;アイコンを選択します。
   * [!DNL Adobe Analytics] で、**[!UICONTROL コンポーネント]**／**[!UICONTROL 計算指標]**&#x200B;に移動し、計算指標ページの上部にある「**[!UICONTROL + 追加]**」を選択します。

1. [計算指標ビルダーの領域](#areas-of-the-calculated-metrics-builder)に進みます。

## 計算指標ビルダーの領域

次の画像と付属の表では、計算指標ビルダーの主な領域と機能の一部について説明します。

![](assets/cm_builder_ui.png)

| 画像内の場所 | 名前と機能 |
|---|---|
| 1 | **タイトル：**&#x200B;指標には必ず名前を付ける必要があります。名前を付けていない指標は保存できません。 |
| 2 | **説明：**&#x200B;指標の用途を示し、類似した指標と区別するための、ユーザーにわかりやすい説明を入力します。 <p>この説明はレポート内にも表示されます。説明には数式を記述しないことをお勧めします。その代わりに、この指標を使うべき状況と使ってはいけない状況について記述してください（数式は、指標の作成時に「概要」という見出しの下に生成されます。そのため、この説明に数式を追加する必要はありません）。 </p> |
| 3 | **形式：**&#x200B;小数、時間、割合、通貨から選択できます。 |
| 4 | **小数点以下の桁数：**&#x200B;レポートに表示する小数点以下の桁数を示します。指定可能な小数点以下の桁数の最大値は 10 です。 |
| 5 | **上昇傾向を次の形式で表示：**&#x200B;この指標の両極性の設定は、Analytics が指標の上昇傾向を良い（緑）または悪い（赤）のどちらと見なすべきかを示します。そのため、レポートのグラフは、上昇傾向の場合に緑または赤で表示されます。 |
| 6 | **タグ：**&#x200B;タグ付けは、指標を管理するための便利な方法です。すべてのユーザーがタグを付けることができます。指標には 1 つ以上のタグを適用できます。ただし、自分が所有しているまたは自分が共有していたセグメントに対するタグのみを表示できます。どのような種類のタグを作成する必要がありますか。次に、便利なタグのいくつかを示します。<ul><li>**チーム名**：ソーシャルマーケティング、モバイルマーケティングなど。</li><li>**プロジェクト**&#x200B;タグ（分析タグ）：入口ページ分析など。</li><li>**カテゴリ**：女性向け、地域など。</li><li>**ワークフロー**：承認対象、（特定の事業単位用に）キュレーション済みなど</li></ul> |
| 7 | **概要：** <p>概要の数式は、指標の定義を変更するたびに更新されます。この数式は、左側の指標パネルにも表示されます（指標にポインタを合わせて <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> アイコンをクリックした場合）。 </p> |
| 8 | **定義：**&#x200B;ここで、指標／計算指標、セグメントまたは関数をドラッグして、計算指標を作成します。 <ul><li>計算指標をドラッグすると、指標の定義が自動的に展開されます。 </li> <li>コンテナを使用して定義をネストできます。ただし、セグメントコンテナとは異なり、これらのコンテナは数式のように機能し、演算の順序を指定します。 </li> </ul> |
| 9 | **演算子：**&#x200B;除算（ <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" />）がデフォルトの演算子です。他にも、+、-、x の演算子があります。 |
| 10 | **プレビュー：**&#x200B;考えられるエラーを簡単に確認できます。プレビューには過去 90 日の情報が表示されます。これは、指標に適したコンポーネントを選択したかどうかを最初に判断するための手段です。予期しない結果が生じた場合は、指標の定義を見直す必要があります。 |
| 11 | **製品の互換性**：「製品の互換性」は、指標が「<a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=ja"  >現在のデータ</a>」、「処理済みのデータ」またはマーケティングチャネルレポートのみ（ファーストタッチ配分）のいずれと互換性があるかを示します。 <p>注意：「現在のデータ」はすべての指標をサポートしているわけではありません。セグメントまたは関数を含む指標は「現在のデータ」との互換性がありません。<a href="/help/components/c-calcmetrics/cm-compatibility.md"  >さらに詳しく... </a> </p> </p> |
| 12 | **追加：**&#x200B;すべてのタイプの計算指標の場合、コンテナおよび静的な数値を定義に追加できます。高度な計算指標の場合、セグメントおよび関数も追加できます。 <ul><li>コンテナは数式のように機能し、演算の順序を指定します。そのため、コンテナ内の項目は、次の演算の前に処理されます。</li><li>コンテナにセグメントをドラッグすると、そのコンテナ内のすべての項目がセグメント化されます。（高度な計算指標のみ）</li><li>コンテナでは複数のセグメントを積み重ねることができます。</li></ul> |
| 13 | **歯車アイコン（指標タイプ、アトリビューション）：**&#x200B;指標の横にある歯車アイコンをクリックすると、<a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  >指標タイプとアトリビューションモデル</a>を指定できます。 |
| 14 | **新規：**&#x200B;新しいセグメントなど新しいコンポーネントを作成できます（新しいセグメントを作成する場合は、<a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  >セグメントビルダー</a>が表示されます）。 |
| 15 | **コンポーネントを検索：**&#x200B;この検索バーを使用して、ディメンション、指標、セグメント（高度な計算指標のみ）および関数（高度な計算指標のみ）を検索できます。 |
| 16 | **ディメンションのリスト：**（セグメントビルダーで）シンプルなセグメント（例：「Page = Homepage」）を作成するときに、計算指標ビルダーから離れずに、直接ディメンション（例：Page）をドラッグしてアイテム（例：Homepage）を選択できます。<p>これにより、セグメントを利用する計算指標の作成が容易になります。</p> |
| 17 | **指標のリスト：**&#x200B;指標は、次の 3 つのカテゴリに分類されます。 <ul> <li>標準指標（<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>計算指標（ <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />） </li><li id="li_8735E76637ED4C3F983731A66E04C93E">指標テンプレート（ <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />）- リストの一番下。 </li> </ul> <p>指標にポインタを合わせると、右側に情報アイコン <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" /> が表示されます。このアイコンをクリックすると、次の情報が表示されます。 </p><ul> <li>指標の計算を行うための数式。 </li><li>指標の傾向のプレビュー </li><li>編集（鉛筆）アイコン <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" />（右上）をクリックすると、この計算指標を編集するための計算指標ビルダーが表示されます。 </li></ul> |
| 18 | **セグメントのリスト：**（高度な計算指標のみ）管理者の場合は、ログイン会社で作成されたすべてのセグメントがこのリストに表示されます。管理者以外のユーザーの場合は、自分が所有するセグメントおよび共有しているセグメントがこのリストに表示されます。<a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=ja"  >さらに詳しく... </a> |
| 19 | **関数のリスト**：（高度な計算指標のみ）関数は、<a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  >基本</a>（最も頻繁に使用される）と<a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  >高度</a>の 2 つのリストに分割されます。 |
| 20 | **レポートスイートセレクター：**&#x200B;別のレポートスイートに切り替えることができます。 |

{style="table-layout:auto"}
