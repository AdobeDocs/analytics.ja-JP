---
description: パネルは、テーブルとビジュアライゼーションのコレクションです。
title: パネルの概要
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 57%

---

# パネルの概要

[!UICONTROL パネル] は、テーブルとビジュアライゼーションのコレクションです。パネルには、Workspace の左上のアイコンまたは [空欄パネル](blank-panel.md). パネルは、期間、レポートスイートまたは分析のユースケースに従ってプロジェクトを整理する場合に役立ちます。

## パネルタイプ

Analysis Workspace では、次のパネルタイプを利用できます。

| パネル名 | 説明 |
| --- | --- |
| [空のパネル](blank-panel.md) | 使用可能なパネルおよびビジュアライゼーションから選択し、分析を開始します。 |
| [クイックインサイトパネル](quickinsight.md) | フリーフォームテーブルとそれに伴うビジュアライゼーションを素早く作成し、インサイトを迅速に分析して取得できます。 |
| [Analytics for Target パネル](a4t-panel.md) | Analysis Workspace で Target アクティビティとエクスペリエンスを分析します。 |
| [アトリビューションパネル](attribution.md) | 任意のディメンションとコンバージョン指標を使用して、アトリビューションモデルをすばやく比較および視覚化します。 |
| [フリーフォームパネル](freeform-panel.md) | 無制限の比較および分類を実行し、ビジュアライゼーションを追加して豊かなデータのストーリーを示します。 |
| [メディア分平均オーディエンスパネル](average-minute-audience-panel.md) | ピーク表示の詳細と分類および比較機能を使用して、分平均オーディエンスを経時的に分析します。 |
| [メディアの同時視聴者数パネル](media-concurrent-viewers.md) | 同時実行のピークの詳細と分類および比較機能を使用して、経時的に同時視聴者を分析します。 |
| [メディア再生滞在時間パネル](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | 同時実行のピークの詳細と分類および比較機能を使用して、経時的に同時視聴者を分析します。 |
| [セグメント比較パネル](c-segment-comparison/segment-comparison.md) | すべてのデータポイントで 2 つのセグメントをすばやく比較し、関連性の高い違いを自動的に見つけます。 |

![](assets/panel-overview.png)

[!UICONTROL クリックインサイト]、[!UICONTROL 空白]、[!UICONTROL フリーフォーム]パネルは、分析を開始するのに最適です。[!UICONTROL Analytics for Target]、[!UICONTROL Attribution ]、[!UICONTROL メディア同時ビューア]および[!UICONTROL セグメント比較]は、より高度な分析に役立ちます。プロジェクトでは `"+"` ボタンが使用できるので、いつでも空白のパネルを追加できます。

デフォルトの開始パネルは[!UICONTROL フリーフォーム]パネルですが、[空白パネル](/help/analyze/analysis-workspace/c-panels/blank-panel.md)をデフォルトにすることも可能です。

## レポートスイート {#report-suite}

パネル内のテーブルとビジュアライゼーションは、パネルの右上で選択された [!UICONTROL レポートスイート] からデータを取得します。 また、レポートスイートでは、左パネルで使用できるコンポーネントも決定します。 プロジェクト内では、分析の使用例に応じて、1 つまたは[複数のレポートスイート](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=ja)を使用できます。 1 つのレポートスイートをプロジェクト内のすべてのパネルに適用するには、**パネルヘッダーを右クリックし、レポートスイートをすべてのパネルに適用**&#x200B;します。

レポートスイートのリストは、関連性に基づいて並べ替えられます。これらの関連性は、現在のユーザーがスイートを使用した最近のタイミングと頻度、および組織内でスイートを使用した頻度に基づき、アドビによって定義されます。

![](assets/panel-report-suite.png)

## カレンダー {#calendar}

パネルカレンダーは、パネル内のテーブルおよびビジュアライゼーションのレポート範囲を制御します。

>[!NOTE]
>（紫色の）日付範囲コンポーネントがテーブル、ビジュアライゼーションまたはパネルドロップゾーン内で使用されている場合は、パネルカレンダーがオーバーライドされます。

![](assets/panel-calendar.png)

パネルカレンダーの詳細設定で、分レベルの日付範囲を適用できます。何日にもわたる日付範囲でレポートを作成する場合、開始時刻は最初の日、終了時刻は範囲の最終日に適用されます。

## ドロップゾーン {#dropzone}

パネルドロップゾーンを使用すると、パネル内のすべてのテーブルおよびビジュアライゼーションにセグメントフィルターおよびドロップダウンフィルターを適用できます。 1 つのパネルに 1 つまたは複数のフィルターを適用できます。各フィルターの上のタイトルは、編集（鉛筆）マークをクリックすることで変更できます。また、右クリックして削除することもできます。

### セグメントフィルター

左パネルからパネルのドロップゾーンにセグメントをドラッグ＆ドロップして、パネルのフィルタリングを開始します。

![フィルター](/help/admin/admin/assets/filter.png)

### アドホックセグメントフィルター

セグメント以外のコンポーネントをドロップゾーンに直接ドラッグしてアドホックセグメントを作成し、セグメントビルダーへの移行に要する時間と手間を節約することもできます。 この方法で作成されたセグメントは、自動的にヒットレベルのセグメントとして定義されます。 これらの定義は、セグメントの隣の情報アイコン (I)、鉛筆の形をした編集アイコンの順にクリックし、セグメントビルダーで編集することで変更できます。

アドホックセグメントはクイックセグメントの一種で、プロジェクトのローカルセグメントです。 公開しない限り、左側のパネルに表示されません。

詳しくは、 [クイックセグメント](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### 静的ドロップダウンフィルター

ドロップダウンフィルターを使用すると、データを制御された方法で操作できます。 例えば、モバイルデバイスタイプにドロップダウンフィルターを追加して、パネルをタブレット、携帯電話、デスクトップ別にセグメント化できます。

ドロップダウンフィルターを使用して、多くのプロジェクトを 1 つに統合することもできます。 例えば、同じプロジェクトの多くのバージョンで異なる国セグメントが適用されている場合、すべてのバージョンを 1 つのプロジェクトに統合し、国ドロップダウンフィルターを追加できます。

![](assets/dropdown-filter-intro.png)

静的ドロップダウンフィルターを作成するには：

* ディメンション項目を使用するドロップダウンフィルターの場合は、左パネルで目的のディメンションの横にある右矢印アイコンをクリックします。 このアクションを実行すると、使用可能なすべてのディメンション項目が表示されます。 次を使用して、このリストから複数のディメンション項目を選択 `[Shift + Click]` または `[Ctrl + Click]`をクリックし、パネルドロップゾーンにドロップします。 **持ちながら`[Shift]`**.
* 指標、セグメント、日付範囲など、他のコンポーネントを使用するドロップダウンフィルターの場合は、 `[Shift + Click]` または `[Ctrl + Click]`. パネルドロップゾーンに選択をドロップします。 **持ちながら`[Shift]`**. このコンテキストでは、すべてのコンポーネントタイプがセグメントとして扱われます。
* 1 つのドロップダウンフィルターに含めることができるコンポーネントタイプは 1 つだけです。 選択範囲に複数のコンポーネントタイプを含める場合、コンポーネントタイプごとに個別のドロップダウンフィルターが作成されます。 例えば、選択範囲に指標とディメンション項目の両方を含めると、2 つの異なるドロップダウンフィルターが作成されます。 1 つのドロップダウンフィルターにはディメンション項目が含まれ、もう 1 つには指標が含まれます。

ドロップダウンリストからオプションの 1 つを選択して、パネル内のデータを変更します。 また、パネル内のデータをフィルターしないよう選択するには、 **[!UICONTROL フィルターなし]**.

![](assets/create-dropdown.png)

ドロップダウンフィルターを右クリックすると、次のオプションが表示されます。

* **[!UICONTROL ラベルを追加]**：プロジェクトにドロップダウンフィルターを追加すると、コンポーネント名にラベルが自動的に設定されます。 ラベルを削除した場合は、このオプションを使用して再度追加できます。
* **[!UICONTROL ラベルを削除]**：ドロップダウンフィルターの上にあるテキストを削除します。
* **[!UICONTROL ドロップダウンフィルターを削除]**：パネルからドロップダウンフィルターを削除します。

プロジェクトにドロップダウンフィルターを追加する方法について詳しくは、[ビデオをご覧ください](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=ja)。

### 動的ドロップダウンフィルター

動的ドロップダウンフィルターを使用すると、パネルのレポート範囲内のデータと、他のドロップダウンフィルターの値に基づいて、使用可能な値を決定できます。 例えば、 [国](/help/components/dimensions/countries.md) ディメンションと [市区町村](/help/components/dimensions/cities.md) ディメンション。 次の場所から国を選択すると、 [!UICONTROL 国] ドロップダウンリスト [!UICONTROL 市区町村] ドロップダウンリストは、その国内の市区町村のみが表示されるように動的に調整されます。

この同じ概念は、すべてのディメンションに適用され、パネルの日付範囲内に表示されるディメンション項目と選択したフィルターのみが表示されます。 静的ドロップダウンフィルターで選択したDimension項目は、動的ドロップダウンフィルターで使用できる値に影響します。 ただし、逆は true ではありません。動的ドロップダウンフィルターで選択したDimension項目は、静的ドロップダウンフィルターの使用可能な値には影響しません。

将来収集される特定のディメンション項目が予想される場合は、ディメンション項目の手動選択を使用できます。 また、動的ドロップダウンフィルターをクリアして、値が含まれないようにすることもできます。そのため、他の動的ドロップダウンフィルターにより多くの値を含めることができます。 選択 **[!UICONTROL すべてをリセット]** をクリックして、そのパネルのすべてのドロップダウンフィルターから選択をクリアします。

動的ドロップダウンフィルターを作成するには：

* 単一のディメンションをパネルドロップゾーンにドラッグ&amp;ドロップします **持ちながら`[Shift]`**.
* 動的ドロップダウンフィルターは、指標、セグメントまたは日付範囲では使用できません。
* ドロップダウンフィルターを右クリックし、「 」を選択します。 **[!UICONTROL フィルターを削除]** をクリックして削除します。

動的ドロップダウンフィルターを右クリックすると、静的ドロップダウンフィルターと同じオプションが表示されます。

## 右クリックメニュー {#right-click}

パネルの追加機能は、パネルのヘッダーを右クリックすると使用できます。

![右クリックメニュー](assets/right-click-menu.png)

次の設定があります。

| 設定 | 説明 |
| --- | --- |
| コピーしたパネル／ビジュアライゼーションを挿入 | コピーしたパネルやビジュアライゼーションをプロジェクト内の別の場所、または別のプロジェクトに貼り付け（「挿入」）できます。 |
| パネルをコピー | 右クリックしてパネルをコピーし、プロジェクト内の別の場所に挿入したり、別のプロジェクトに挿入したりできます。 |
| レポートスイートをすべてのパネルに適用 | アクティブなパネルレポートスイートをプロジェクト内のすべてのパネルに適用できます。 |
| パネルを複製 | 現在のビジュアライゼーションの完全な複製を作成して、修正できます。 |
| すべてのパネルを折りたたむ／展開 | すべてのプロジェクトパネルを折りたたんだり展開したりします。 |
| パネル内のすべてのビジュアライゼーションを折りたたむ／展開 | 現在のパネル内のすべてのビジュアライゼーションを折りたたんだり展開したりします。 |
| 説明を編集 | パネルの説明テキストを追加（または編集）します。 |
| パネルリンクを取得 | プロジェクト内の特定のパネルに他のユーザーを誘導することができます。受信者は、リンクをクリックした後、リンク先の正確なパネルにリダイレクトされる前にログインする必要があります。 |
