---
title: Adobe AnalyticsのReport Builderハブとは
description: Report Builder ハブコンポーネントについて説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 61%

---

# Report Builder ハブ

Report Builder ハブを使用して、データブロックの作成、更新、管理を行います。

Report Builderハブには、作成ボタンと管理ボタン、コマンドリスト、クイック編集パネルが含まれています。

<img src="./assets/hub51.png" alt="Report Builder ハブ"/>


## ボタンの作成、管理、スケジュール

新しいデータブロックの作成、既存のデータブロックの管理、データブロックのスケジュール設定を行うには、「作成」、「管理」、「スケジュール」の各ボタンを使用します。

## コマンドパネル

コマンドパネルを使用して、選択したセルまたは以前のアクションと互換性のあるコマンドにアクセスします。

### コマンド

| 表示されるコマンド | 使用条件... | 目的 |
|------|------------------|--------|
| データブロックの作成 | ワークブック内で 1 つ以上のセルが選択されている。 | データブロックの作成に使用 |
| データブロックの編集 | 選択したセル範囲が、1 つのデータブロックのみの一部である。 | データブロックの編集に使用 |
| データブロックの更新 | 選択範囲に少なくとも 1 つのデータブロックが含まれている。コマンドは、選択範囲内のデータブロックのみを更新します。 | 1 つ以上のデータブロックの更新に使用 |
| すべてのデータブロックの更新 | ワークブックには、1 つ以上のデータブロックが含まれています。 | ワークブック内のすべてのデータブロックを更新するために使用 |
| ワークブックを送信 |   | ワークブックをスケジュールに従って送信します。 |
| データブロックのコピー | 選択したセルまたはセル範囲は、1 つ以上のデータブロックの一部です。 | データブロックのコピーに使用 |
| データブロックの削除 | 選択したセル範囲が、1 つのデータブロックのみの一部である。 | データブロックの削除に使用 |

## クイック編集パネル

スプレッドシートで 1 つ以上のデータブロックを選択すると、Report Builder に「クイック編集」パネルが表示されます。「クイック編集」パネルを使用して、1 つのデータブロック内のパラメーターを変更したり、複数のデータブロック内のパラメーターを同時に変更したりできます。

![Report Builderのクイック編集パネル ](./assets/hub2.png)

「クイック編集」セクションを使用して行った変更は、選択したすべてのデータブロックに適用されます。

### レポートスイート

データブロックは、選択したレポートスイートからデータを取り込みます。 ワークシートで複数のデータブロックが選択されていて、それらが同じレポートスイートからデータを取り込まない場合、「**レポートスイート**」リンクに *複数* と表示されます。

レポートスイートを変更すると、選択範囲内のすべてのデータブロックに新しいレポートスイートが採用されます。 データブロック内のコンポーネントは、ID に基づいて新しいレポートスイートと照合されます（例えば、```evars``` の照合）。 コンポーネントがデータブロック内に見つからない場合は、警告メッセージが表示され、コンポーネントがデータブロックから削除されます。

レポートスイートを変更するには、ドロップダウンメニューから新しいレポートスイートを選択します。

![ レポートスイートのドロップダウンメニューを表示するReport Builderハブ。](./assets/image16.png)

### 日付範囲

**[!UICONTROL 日付範囲]**&#x200B;は、選択したデータブロックの日付範囲を表示します。複数の日付範囲を持つ複数のデータブロックが選択されている場合、「**[!UICONTROL 日付範囲]**」リンクに「*複数*」と表示されます。

### フィルター

「**フィルター**」リンクには、選択したデータブロックで使用されているフィルタの概要リストを表示されます。複数のフィルターが適用された状態で複数のデータブロックが選択されている場合、「**フィルター**」リンクには、「*複数*」と表示されます。
