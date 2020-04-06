---
description: トリガー条件のアクションを設定します。
keywords: Dynamic Tag Management;rule;create rule;new rule;javascript/third party tags;set up actions for condition;add new script;non-sequential javascript;sequential javascript;non-sequential html
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: トリガー条件のアクションの設定
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# トリガー条件のアクションの設定

トリガー条件のアクションを設定します。

条件を設定した後、トリガー条件にするアクションを設定する必要があります。 このアクションには、[!DNL Analytics] イベント、サードパーティタグおよびカスタムスクリプトを含めることができます。この例では、スクリプトまたはサードパーティタグを設定する方法を説明します。

[!DNL Adobe Analytics] や Google Analytics などの統合ツールだけでなく、Dynamic Tag Management は、あらゆる種類の JavaScript をトリガーしたり、サイト、選択したページまたは特定のシナリオに HTML を挿入したりできます。

各ルールは、スクリプトや HTML 挿入をいくつでもトリガーできます。

>[!NOTE]ページ内にカスタムコードを挿入できる DTM の機能によってクロスサイトスクリプティング（XSS）脆弱性が入り込まないよう、十分注意してください（詳しくは、[OWASP のガイド資料](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS))を参照してください）。スクリプト内でデータ要素を使用する場合は、特に注意が必要です。 データ要素の値は、信頼できないソースから取得されたものである可能性が常にあると想定します。

**トリガー条件のアクションを設定するには**

1. をクリック **[!UICONTROL JavaScript / Third Party Tags]** して、新しいスクリプトをルールに追加します。

   ![](assets/scripts-actions.png)

1. クリック **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. スクリプトに名前を付けます。
1. スクリプトのトリガー方法を指定して、目的のコンテンツをテキスト領域に貼り付けます。![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

