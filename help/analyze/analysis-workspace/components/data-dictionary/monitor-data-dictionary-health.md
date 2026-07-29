---
description: 管理者は、データ辞書の正常性を監視する責任があります。 これには、コンポーネントがデータを収集しているか、承認されているか、説明が含まれているか、重複がないかが含まれます。
title: データ辞書の正常性の監視
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 100%

---

# データ辞書の正常性の監視 {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="プライマリコンポーネントを共有"
>abstract="このオプションを選択すると、プライマリコンポーネントは、複製コンポーネントにアクセスできるすべてのユーザー（所有者と、コンポーネントが共有されているすべてのユーザー）と共有されます。 その後、これらのユーザーは、今後のプロジェクトのコンポーネントリストからプライマリコンポーネントを選択できます。 ただし、統合された重複コンポーネントの所有者であっても、コンポーネントを編集できません。 <br/>このオプションは、プライマリコンポーネントがセグメント、計算指標または日付範囲である場合にのみ使用できます。 指標とディメンションは、すべてのユーザーが常に使用できます。
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="置き換えられた重複を削除"
>abstract="このオプションを選択すると、統合された重複は使用できなくなります。 重複を引き続き使用する場合は、このオプションの選択を解除します。"

<!-- markdownlint-enable MD034 -->

Analytics 管理者は、正常なデータ辞書を保持する責任があります。

## 正常なデータ辞書の特徴

正常なデータ辞書とは、すべてのコンポーネントが次のとおりであることです。

* 使用され、データを収集している

* ユーザーが最適な使用方法を把握できるように役立つ説明が含まれている

* 不要な重複が発生しない

* 管理者によって承認されている

## データ辞書の正常性の確認

データ辞書で正常性の問題を特定するには：

1. Analysis Workspace プロジェクトを開きます。

1. Analysis Workspace の左側にある「データ辞書」アイコンを選択します （データ辞書にアクセスする別の方法については、[データ辞書の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ辞書へのアクセス」を参照してください）。

   データ辞書ウィンドウが表示されます。

   ![データ辞書の管理者表示](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいレポートスイートが選択されます。

1. 「[!UICONTROL **要素の正常性**]」タブで、次のいずれかのオプションの横にある「[!UICONTROL **表示**]」を選択します。

   * [!UICONTROL **コンポーネントの説明がありません**]

   * [!UICONTROL **コンポーネントに重複があります**]

   * [!UICONTROL **コンポーネントにデータが接続されていません**]

   選択した内容に応じて、適切なフィルターがデータ辞書に適用され、関連するコンポーネントのみが表示されます。

1. 任意のコンポーネントを編集して、データ辞書の正常性を改善します。 データ辞書でコンポーネントを編集する方法については、[データ辞書でのコンポーネントエントリの編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)を参照してください。
