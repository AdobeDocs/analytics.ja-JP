---
title: メディア再生滞在時間パネル
description: Analysis Workspaceのメディア再生滞在時間パネルの使用方法と解釈方法。
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 74ef44c4afba6d2dffb2b10fa473baee3be16a23
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 49%

---

# メディア再生滞在時間パネル

Media Analyticsのお客様は、再生に費やした時間を分析して、同時実行のピークが発生した場所やドロップオフが発生した場所を把握し、コンテンツや閲覧者のエンゲージメントの質に関する貴重な情報を提供し、ボリュームや規模のトラブルシューティングや計画に役立てます。

Analysis Workspaceでの再生滞在時間は、特定の時点でのメディアストリームの視聴に費やされた時間で、一時停止、バッファー、開始時間が含まれます。

メディア再生滞在時間パネルを使用すると、同時実行のピークに関する詳細と分類および比較機能を備えた、経時的な再生の分析が可能です。 メディア再生滞在時間パネルにアクセスするには、Media Analyticsコンポーネントが有効なレポートスイートに移動します。 次に、左端のパネルアイコンをクリックし、 パネルを Analysis Workspace プロジェクトにドラッグします。

また、このパネルには、24時間未満で選択および表示できる新機能がカレンダーに含まれています。 パネル全体に対してこれを実行したり、連続した期間を使用してセグメントを作成して、プログラムやプログラムのセクション間での視聴者のリードイン/リードアウトを追跡できます。 これらの日付セグメントを少なくとも2つ配置すると、「日付順序の表示」のラジオボタンオプションが表示されます。このオプションは、共通のx軸開始で行を重ねるか、特定のx軸開始で順に表示します。

## パネル入力 {#Input}

次の入力設定を使用して、メディア再生滞在時間パネルを設定できます。

| 設定 | 説明 |
|---|---|
| パネルの日付範囲 | パネルの日付範囲のデフォルトは「今日」です。  一度に 1 日または複数の月を表示するように編集できます。<br>この視覚化は、1440 行のデータに制限されています（たとえば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は自動的に更新され、日付範囲全体に対応します。 |
| 精度 | 精度のデフォルトは「分」です。<br>この視覚化は、1440 行のデータに制限されています（たとえば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は自動的に更新され、日付範囲全体に対応します。 |
| パネルの要約数値 | 再生滞在時間の日付や時間の詳細を確認するには、概要番号を使用できます。 最大値は、ピーク同時実行性の詳細を示します。 最小値は、トラフの詳細を示します。  合計は、選択範囲の合計再生時間を加算します。 パネルのデフォルトでは、最大値のみが表示されますが、最小値、合計値、またはこれら3つの任意の組み合わせを表示するように変更できます。<br>内訳を使用している場合は、それぞれの概要番号が表示されます。 |
| シリーズの分類 | オプションとして、セグメント、ディメンション、ディメンション項目または日付範囲でビジュアライゼーションを分類できます。 <p> - 一度に 10 行まで表示できます。 分類は 1 つのレベルに制限されます。</p><p> - ディメンションをドラッグすると、選択したパネルの日付範囲に基づいて、上位のディメンション項目が自動的に選択されます。</p> - 日付範囲を比較するには、2 つ以上の日付範囲をシリーズ分類フィルターにドラッグします。 |
| 時刻の形式 | 再生に費やされた時間は、時間:Minutes:秒（デフォルト）または分（整数で表示され、0.5で切り上げられます）で表示できます。 |
| 日付順の表示 | 少なくとも2つの日付範囲セグメントをシリーズ分類として配置した場合は、オーバーレイ（デフォルト）または順次を選択するオプションが表示されます。 共通のX軸の始点を持つ線が並行して表示され、連続してX軸の始点を持つ線が表示されます。 データが整列する場合（例えば、セグメント1が午後8:44に終了し、セグメント2が午後8:45に開始する）、行が順に表示されます。 |

### デフォルトのビュー

![デフォルトのビュー](assets/mpts_default_view.png)

## パネル出力 {#Output}

メディア再生滞在時間パネルは、折れ線グラフと概要の数値を返し、再生滞在時間の最大値、最小値、合計の詳細が含まれます。 パネルの上部に、選択したパネル設定を示す概要行が表示されます。

右上の編集鉛筆アイコンをクリックすると、いつでもパネルを編集および再構築できます。

シリーズの分類を選択した場合は、折れ線グラフに線と次の各項目の概要番号が表示されます。

![メディア再生時間の出力](assets/mpts_outputs1.png)

### データソース

このパネルで使用できる指標は、再生滞在時間のみです。

| 指標 | 説明 |
|---|---|
| 再生滞在時間 | 一時停止、バッファー、開始時間など、選択した精度で視聴されたコンテンツの合計時間:minutes:秒（または分）。 |

## よくある質問（FAQ） {#FAQ}

| 質問 | 回答 |
|---|---|
| フリーフォームテーブルはどこにありますか？ データソースの確認方法を教えてください。 | <p></p><p>このビューでは、フリーフォームテーブルは使用できません。  折れ線グラフを右クリックし、CSVファイルをダウンロードすることで、データソースをダウンロードできます。</p> |
| <p>精度が変更されたのはなぜですか？</p> | <p>この視覚化は、1440 行のデータに制限されています（たとえば、分レベルの粒度で 24 時間）。日付範囲と精度の組み合わせの結果が 1440 行を超える場合、精度は日付範囲全体に対応するように自動的に更新されます。</p><p></p><p>大きい日付範囲から小さい日付範囲に変更する場合、日付範囲が変更されると、精度は許容できる最小の詳細に更新されます。 より高い精度を表示するには、パネルを編集して再構築します。</p> |
| <p></p><p>ビデオ名、セグメント、コンテンツタイプなどの比較方法を教えてください。</p> | <p>単一のビジュアライゼーションでこれらを比較するには、セグメント、ディメンションまたは特定のディメンション項目をシリーズ分類フィルターにドラッグします。</p><p></p><p>ビューの分類は 10 個に制限されています。  10 を超える表示をおこなうには、複数のパネルを使用する必要があります。</p> |
| 日付範囲の比較方法を教えてください。 | 単一のビジュアライゼーション内の日付範囲を比較するには、2 つ以上の日付範囲をドラッグして、シリーズの分類を使用します。  これらの日付範囲は、パネルの日付範囲より優先されます。 |
| ビジュアライゼーションのタイプを変更する方法を教えてください。 | <p></p><p>このパネルでは、時系列の線のビジュアライゼーションのみが可能です。</p> |
| 異常値検出を実行できますか？ | <p></p><p>いいえ。このパネルでは異常値検出は利用できません。</p> |