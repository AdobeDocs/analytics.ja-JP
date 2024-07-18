---
description: 注文の促進を支援するマーケティングチャネルを示す指標の作成方法について説明します。これは、任意のディメンションや興味の成功イベントに適応させることができます。
title: 注文支援指標
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 59%

---

# 「注文支援」指標の作成

次の情報では、注文の促進に役立つマーケティングチャネルを示す指標の作成方法を説明します。 これは、任意のディメンションや興味の成功イベントに適応させることができます。

1. [ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) の説明に従って、計算指標の作成を開始します。

1. 計算指標ビルダーで、指標に「アシスト注文」という名前を付けます。

1. 「定義」キャンバスで、注文件数指標をドラッグします。次に、設定の歯車アイコンの「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」チェックボックスを選択して、アトリビューションモデルを調整します。

   ![](assets/attr-model.png)

1. アトリビューションモデルとして、「**[!UICONTROL カスタム]**」を選択します。重みを 0（スターター）、100（プレイヤー）、0（クローザー）に変更します。

   ![](assets/custom-attr-model.png)

1. [!UICONTROL **適用**]/[!UICONTROL **保存**] を選択します。

1. Analysis Workspaceで、マーケティングチャネル ディメンション、注文、および新しいアシスト注文指標を使用してフリーフォームテーブルを作成します。

   ![](assets/mktg-channel-assists.png)

   これで、どのマーケティングチャネルが注文の促進を支援したかを簡単に示すことができます。または、フリーフォームテーブルで指標を右クリックして、テーブルから直接アトリビューションモデルを調整できます。

1. （任意） [ 計算指標の共有 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) の説明に従って、組織の他のユーザーと指標を共有します。
