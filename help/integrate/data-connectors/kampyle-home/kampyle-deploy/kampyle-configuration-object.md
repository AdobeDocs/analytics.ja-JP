---
description: 統合ウィザードを完了したら、統合設定オブジェクトをWebプロパティにデプロイする必要があります。
seo-description: 統合ウィザードを完了したら、統合設定オブジェクトをWebプロパティにデプロイする必要があります。
seo-title: 統合設定オブジェクトのデプロイ
solution: Analytics
title: 統合設定オブジェクトのデプロイ
uuid: e951c864-2914-4324-9f03-5069d4f75d99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploy the Integration Configuration Object{#deploy-the-integration-configuration-object}

統合ウィザードを完了したら、統合設定オブジェクトをWebプロパティにデプロイする必要があります。

多くの場合、統合設定オブジェクトをデプロイする最も簡単な方法は、Adobe Analytics導入コードに組み込むことです。

>[!NOTE]
>
>Adobe TagManagerまたはDynamic Tag Managementを使用してAdobe Analyticsをデプロイする場合、そのツールを使用して統合設定オブジェクトを簡単に追加できます。

1. Navigate to the **[!UICONTROL Resources]** &gt; **[!UICONTROL Support]** tab of the integration.
1. **[!UICONTROL Kampyle統合コード（JS）]** リソースをダウンロードして保存します。コードは、次のようになります。

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 次のいずれかの方法を使用してコードをデプロイします。

       |** Adobe TagManagerまたはDynamic Tag Managementを使用します。**|コードを追加するには、tag managementインターフェイスを使用します。|
       |---|---|
       | **In all other cases** | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |
   
