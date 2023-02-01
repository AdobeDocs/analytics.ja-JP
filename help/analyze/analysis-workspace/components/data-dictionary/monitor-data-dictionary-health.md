---
description: 管理者は、データディクショナリの正常性の監視を担当します。 これには、コンポーネントがデータを収集しているかどうか、承認されているかどうか、説明が含まれているかどうか、および重複が発生していないかどうかが含まれます。
title: データ辞書の正常性の監視
feature: Components
role: Admin
source-git-commit: 5bfbc3059526527e35f26b750d048efebee68e9e
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# データ辞書の正常性の監視

{{release-limited-testing}}

Analytics 管理者は、正常なデータディクショナリの維持を担当します。

## 正常なデータディクショナリの特性

健全なデータディクショナリは、すべてのコンポーネントで構成されます。

* 使用中で、データを収集中

* ユーザーが最適な使用方法を把握できるよう、役に立つ説明を含めます

* 不要な重複が発生しない

* 管理者によって承認されている

## データディクショナリの正常性を確認してください

データディクショナリでヘルスの問題を特定するには、次の手順を実行します。

1. Analysis Workspaceプロジェクトを開きます。

1. Analysis Workspaceの左側にあるデータディクショナリアイコンを選択します。 ( データディクショナリへのアクセスの代替方法については、「データディクショナリへのアクセス」を参照してください。 [データディクショナリの概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   データディクショナリウィンドウが表示されます。

   ![データ辞書の管理ビュー](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいレポートスイートが選択されていることを確認します。

1. の [!UICONTROL **辞書のヘルス**] タブ、選択 [!UICONTROL **表示**] をクリックします。

   * [!UICONTROL **コンポーネントに説明がありません**]

   * [!UICONTROL **コンポーネントに重複があります**]

   * [!UICONTROL **コンポーネントにデータが接続されていません**]

   選択した内容に応じて、適切なフィルターがデータディクショナリに適用され、関連するコンポーネントのみが表示されます。

1. 任意のコンポーネントを編集して、データディクショナリの正常性を改善します。 データディクショナリ内のコンポーネントの編集方法について詳しくは、 [データディクショナリ内のコンポーネントエントリの編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).