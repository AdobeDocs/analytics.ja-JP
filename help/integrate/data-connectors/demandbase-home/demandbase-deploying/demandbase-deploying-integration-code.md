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
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

統合ウィザードを完了したら、統合コードをAdobe Analytics導入コード（s_ code）にデプロイする必要があります。

>[!NOTE]
>
>Adobe TagManagerまたはDynamic Tag Managementを使用してAdobe Analyticsをデプロイした場合、これらのツールのいずれかを使用して統合コードを簡単に追加できます。

1. **[!UICONTROL 「サポート]** 」タブに移動し、統合のリソース領域から `integration code v2_0_1` リソースをダウンロードして保存します。

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Adobe Analytics導入コードにまだ存在しない場合は、Integrateモジュールを含めます。For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. 次のいずれかの方法を使用してコードをデプロイします。

   * コードを追加するには、Adobe TagManagerまたはDynamic Tag Managementを使用します。
   * または、Adobe Analytics導入コードの更新を担当する組織リソースにコードを配信します。

>[!IMPORTANT]
>
>実稼動環境にデプロイする前に、開発/ステージング環境でこの統合のデプロイメントをテストしてください。

