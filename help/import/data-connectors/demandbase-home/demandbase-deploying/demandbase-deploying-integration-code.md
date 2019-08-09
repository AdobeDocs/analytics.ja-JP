---
description: 統合ウィザードを完了したら、統合コードをAdobe Analytics導入コード（s_ code）にデプロイする必要があります。
seo-description: 統合ウィザードを完了したら、統合コードをAdobe Analytics導入コード（s_ code）にデプロイする必要があります。
seo-title: 統合コードのデプロイ
title: 統合コードのデプロイ
uuid: b3fbda0b-4ed3-4967-84ee-6c66564606e7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 統合コードのデプロイ{#deploying-the-integration-code}

統合ウィザードを完了したら、統合コードをAdobe Analytics導入コード（s_ code）にデプロイする必要があります。

>[!NOTE]
>
>Adobe TagManagerまたはDynamic Tag Managementを使用してAdobe Analyticsをデプロイした場合、これらのツールのいずれかを使用して統合コードを簡単に追加できます。

1. **[!UICONTROL 「サポート]** 」タブに移動し、統合のリソース領域から `integration code v2_0_1` リソースをダウンロードして保存します。

1. 該当する場合は、コードに必要な変更を加えてください。詳しくは、統合コードの [変更](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855)を参照してください。
1. Adobe Analytics導入コードにまだ存在しない場合は、Integrateモジュールを含めます。詳しくは、Integrateモジュール [のインクルード](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e)を参照してください。
1. 次のいずれかの方法を使用してコードをデプロイします。

   * コードを追加するには、Adobe TagManagerまたはDynamic Tag Managementを使用します。
   * または、Adobe Analytics導入コードの更新を担当する組織リソースにコードを配信します。

>[!IMPORTANT]
>
>実稼動環境にデプロイする前に、開発/ステージング環境でこの統合のデプロイメントをテストしてください。

