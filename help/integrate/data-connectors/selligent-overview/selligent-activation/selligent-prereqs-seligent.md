---
description: 統合を導入する前に、保証アカウントから提供する必要のある情報を一覧表示します。
seo-description: 統合を導入する前に、保証アカウントから提供する必要のある情報を一覧表示します。
seo-title: 保証の前提条件
solution: Analytics
title: 保証の前提条件
uuid: 3a43a1c0-5f51-4bc8- b6b9-0c46aa00ba9f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Prerequisites for Selligent{#prerequisites-for-selligent}

統合を導入する前に、保証アカウントから提供する必要のある情報を一覧表示します。

**有効な保証アカウント**

このData Connectors統合を使用するには、有効な保証アカウントが必要です。

**アカウント情報**

この統合セットアップ中に、保証アカウントに関する次の情報が必要になります。

* **Adobe Service URL**:

   URLは、SELSTマーケティングソリューションへのログオンに使用されるURLから取得できます。URLの"/siweb/login. aspx"部分を"/automation/omniture. asmx"に置き換えます。

   例:http://<client-specific install url>/automation/omniture.asmx

* **クエリ文字列パラメーター:** これらは、メッセージIDおよび受信者ID（訪問者ID）のランディングページのURLに追加されます。メッセージIDおよび受信者IDには、常にMIDとREMOVEがあります。

* **統合トークン** をSimWeb内から起動し、 **[!UICONTROL 設定]** / **[!UICONTROL システム設定]** / **[!UICONTROL 全般]** タブ/ **[!UICONTROL システム]**&#x200B;に移動します。**[!UICONTROL セキュリティ]**&#x200B;の下で、統合トークンを見つけることができます。

   ![](assets/selligent-integration_token.png)

