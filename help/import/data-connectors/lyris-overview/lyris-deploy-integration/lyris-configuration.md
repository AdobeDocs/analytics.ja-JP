---
description: ウィザードの完了後にLiris内で設定する内容を説明します。
seo-description: ウィザードの完了後にLiris内で設定する内容を説明します。
seo-title: Livris EmailLabs内の設定
solution: Analytics
title: Livris EmailLabs内の設定
uuid: 1276176d- e5e9-451a-9a7b-9f29a340a25b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Livris EmailLabs内の設定{#configuration-within-the-lyris-emaillabs}

ウィザードの完了後にLiris内で設定する内容を説明します。

1. 統合ウィザードの完了後、Lyris Professionalチームと連携してLivris HQアカウントへの統合を完了し、テストを容易にする必要があります。
1. URLクエリ文字列パラメータの追加:URL append文字列が、ユーザーインターフェイスの組織設定領域に正しく入力されていることを確認します。これには、キャンペーンレベルID（hq_ m）および受信者レベルID（hq_ v）を含める必要があります。

   文字列IDの例を次に示します。

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >Lyrisのネイティブ解析ツールを適用する場合、「追跡」 ** をクリックすると、追加された必要なすべての変数が表示されます。

