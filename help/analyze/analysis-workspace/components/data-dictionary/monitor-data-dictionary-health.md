---
description: 管理者は、データ要素の正常性を監視する責任があります。これには、コンポーネントがデータを収集しているか、承認されているか、説明が含まれているか、重複がないかが含まれます。
title: データ要素の正常性の監視
feature: Components
role: Admin
hide: true
hidefromtoc: true
source-git-commit: b0a3ee6785bdc2f3e9a55e42591b4846984934b6
workflow-type: ht
source-wordcount: '236'
ht-degree: 100%

---

# データ要素の正常性の監視

{{release-limited-testing}}

Analytics 管理者は、正常なデータ要素を保持する責任があります。

## 正常なデータ要素の特徴

正常なデータ要素とは、すべてのコンポーネントが次のとおりであることです。

* 使用され、データを収集している

* ユーザーが最適な使用方法を把握できるように役立つ説明が含まれている

* 不要な重複が発生しない

* 管理者によって承認されている

## データ要素の正常性の確認

データ要素で正常性の問題を特定するには：

1. Analysis Workspace プロジェクトを開きます。

1. Analysis Workspace の左側にある「データ要素」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![データ要素の管理者表示](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいレポートスイートが選択されます。

1. 「[!UICONTROL **要素の正常性**]」タブで、次のいずれかのオプションの横にある「[!UICONTROL **表示**]」を選択します。

   * [!UICONTROL **コンポーネントの説明がありません**]

   * [!UICONTROL **コンポーネントに重複があります**]

   * [!UICONTROL **コンポーネントにデータが接続されていません**]

   選択した内容に応じて、適切なフィルターがデータ要素に適用され、関連するコンポーネントのみが表示されます。

1. 任意のコンポーネントを編集して、データ要素の正常性を改善します。データ要素でコンポーネントを編集する方法については、[データ要素でのコンポーネントエントリの編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)を参照してください。