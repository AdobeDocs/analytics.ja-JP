---
description: Dynamic Tag Management を使用した導入のために Adobe Analytics ツールを作成します。ここでは、手動（レガシー）導入について説明します。
keywords: Dynamic Tag Management
seo-description: Dynamic Tag Management を使用した導入のために Adobe Analytics ツールを作成します。ここでは、手動（レガシー）導入について説明します。
seo-title: Adobe Analytics の手動導入（レガシー）
solution: Marketing Cloud、Analytics、Target、Dynamic Tag Management
title: Adobe Analytics の手動導入（レガシー）
uuid: d3ad2035-393d-4a77-81f6- e749ee717c09
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Adobe Analytics の手動導入（レガシー）

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. ここでは、手動（レガシー）導入について説明します。

自動導入の管理については、「 [Adobe Analytics ツールの追加](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

If you want to change a manual configuration to automatic, edit a tool and click **[!UICONTROL Enable Automatic Configuration]**.

1. Analytics 測定コードをダウンロードします：
   1. In Analytics, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. **[!UICONTROL "JavaScript（新規）]** 」をクリックして、コードをローカルにダウンロードします。
1. [!UICONTROL Dynamic Tag Management]で、Webプロパティ [を作成](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)します。

   ![](assets/dtm-property.png)

   Web プロパティを作成したら、[!UICONTROL ダッシュボード]の「[!UICONTROL Web プロパティ]」タブで編集できます。Web プロパティのアクティブ化は必要ありません。を参照してください。

1. プロパティに Analytics ツールを追加します：
   1. **[!UICONTROL "Webプロパティ]** 」タブで、プロパティをクリックします。
   1. **[!UICONTROL 「概要]** 」タブで、「ツールを追加」をクリック ****&#x200B;します。
   1. **[!UICONTROL ツールタイプ]** メニューから「 **[!UICONTROL Adobe Analytics]**」を選択します。

      ![](assets/dtm-add-analytics-tool.png)

   1. 次のフィールドを設定します。

      | 要素 | 説明 |
      |---|---|
      | ツールタイプ | Analytics、Target、Social などの Experience Cloud ソリューション。 |
      | ツール名 | このツールの名前。この名前は、[!UICONTROL インストール済みツール]の「[!UICONTROL 概要]」タブに表示されます。 |
      | 実稼動アカウント ID | 実稼動サイトのデータを計測するアカウントの RSID。Dynamic Tag Management は、実稼動およびステージング環境に適切なタグを自動的にインストールします。 |
      | ステージングアカウント ID | 開発またはテスト環境で使用されます。ステージング用のテストデータは実稼動用とは別に保管されます。 |

1. Click **[!UICONTROL Create Tool]**.

   インストールされたツールが「[!UICONTROL 概要]」タブに表示されます。

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   少なくとも、「**[!UICONTROL Cookie]」をクリックしてトラッキングサーバーおよび SSL トラッキングサーバーを設定します。**

1. **[!UICONTROL "General"]** をクリックし、コアのAppMeasurementコード [を挿入](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658)します。
1. Define a [page load rule](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   これで、解析データを収集するためのルールを定義する準備ができました。最初にいくつかのデータ要素を定義するとよいでしょう。データ要素を使用すると、ページから抽出したデータをルールの設定に使用できます。最初はまず、各ページの [!DNL Analytics] データを収集するための条件を持たないページ型ルールを定義するとよいでしょう。
1. [「埋め込み」タブのヘッダーおよびフッターコードを各ページに追加](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5)します。

   ステージングでは、デフォルト設定のままでもよいでしょう。必要に応じて、実稼動サイトへ発行する前までに変更してください。
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >[!UICONTROL Adobe Analytics] ページ（一般、cookieなど）の設定は、ユーザー `s_code`の設定より優先されます。`s_code` にこれらの設定が存在する場合、ここで繰り返す必要はありません。

